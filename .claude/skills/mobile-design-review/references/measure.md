# Measurement snippets for `preview_eval`

Paste these into `preview_eval` (serverId + expression). They return JSON strings. Prefer these over
screenshots for any pixel judgment — the screenshot frame in this preview can be narrower than the
emulated CSS viewport, so screenshots can look clipped when content actually fits.

## 1. Page scanner — gutters, overflow, type

Returns: the true viewport width, main-column left/right gutters and their asymmetry, a list of
elements that genuinely overflow (excluding those inside legit horizontal scrollers), and the
computed font sizes of the key type roles.

```javascript
(function(){
  var cw = document.documentElement.clientWidth;
  function inScroller(el){var n=el.parentElement;while(n&&n!==document.body){var ox=getComputedStyle(n).overflowX;if(ox==='auto'||ox==='scroll')return true;n=n.parentElement;}return false;}

  // genuine horizontal overflow
  var over=[];
  document.querySelectorAll('body *').forEach(function(el){var r=el.getBoundingClientRect();if(r.width>0&&r.right>cw+1&&!inScroller(el)){over.push({cls:(el.className&&el.className.toString?el.className.toString().slice(0,40):''),tag:el.tagName,right:Math.round(r.right)});}});

  // symmetry: pick the most prominent content wrapper we can find
  var candidates = ['.hero-content','.hero-inner','.blog-content-wrap','.content','main','section'];
  var col=null; for(var i=0;i<candidates.length;i++){var c=document.querySelector(candidates[i]); if(c){col=c;break;}}
  var gut=null;
  if(col){var r=col.getBoundingClientRect(); gut={sel: col.className||col.tagName, left:Math.round(r.left), right:Math.round(cw-r.right), diff:Math.round(Math.abs(r.left-(cw-r.right)))};}

  // type sizes
  function fs(sel){var e=document.querySelector(sel); return e?parseFloat(getComputedStyle(e).fontSize):null;}
  function lh(sel){var e=document.querySelector(sel); if(!e)return null; var cs=getComputedStyle(e); return {size:parseFloat(cs.fontSize), lineHeight:cs.lineHeight};}
  var type={
    h1: lh('h1'),
    h2: fs('h2'),
    body: lh('p'),
    eyebrow: fs('.hero-eyebrow, .blog-eyebrow, .journey-eyebrow, .hero-tag, [class*="eyebrow"], [class*="label"]')
  };

  return JSON.stringify({page:location.pathname, clientWidth:cw, gutters:gut, genuineOverflow:over.length, offenders:over.slice(0,10), type:type}, null, 0);
})()
```

Read it like this:
- `gutters.diff` ≤ 4 → symmetric. A large `diff` means the content column is lopsided.
- `genuineOverflow` must be 0.
- `type.h1.size` in px: ~32–42px is the 2rem–2.6rem target (÷16). `h2` ~24–30px. `body.size` ~15–17px.
- `type.body.lineHeight` should be ~1.5–1.65 × the size.

## 2. Words-per-line probe

Too-large type shows up as too few words per line. Point it at a paragraph or heading selector.

```javascript
(function(sel){
  var el=document.querySelector(sel); if(!el) return JSON.stringify({error:'not found'});
  var words=el.innerText.trim().split(/\s+/).length;
  var lineH=parseFloat(getComputedStyle(el).lineHeight)||parseFloat(getComputedStyle(el).fontSize)*1.5;
  var lines=Math.max(1, Math.round(el.getBoundingClientRect().height/lineH));
  return JSON.stringify({sel:sel, words:words, approxLines:lines, wordsPerLine:+(words/lines).toFixed(1)});
})('SELECTOR_HERE')
```

`wordsPerLine` < 5 on body copy, or a heading at `approxLines` ≥ 4 with few words, means scale the
font down.

## 3. Cohesion probe — intra- vs inter-group gap

Pass two selectors that should feel grouped (e.g. a stat number and its label) plus the selector of
the next separate component. If the gap *within* the group isn't clearly smaller than the gap *to*
the next component, proximity isn't encoding the grouping and you should tighten the intra-group gap.

```javascript
(function(aSel,bSel,nextSel){
  function rect(s){var e=document.querySelector(s);return e?e.getBoundingClientRect():null;}
  var a=rect(aSel),b=rect(bSel),n=rect(nextSel);
  function vgap(x,y){if(!x||!y)return null;return Math.round(Math.max(y.top-x.bottom, x.top-y.bottom));}
  return JSON.stringify({intraGroupGap:vgap(a,b), gapToNextComponent:vgap(b,n), ok:(vgap(a,b)!=null&&vgap(b,n)!=null)? vgap(a,b) < vgap(b,n) : 'check-selectors'});
})('A_SELECTOR','B_SELECTOR','NEXT_COMPONENT_SELECTOR')
```

`ok:true` means the group is tighter than the gap to the next thing (good). `ok:false` means the
components look estranged — reduce the intra-group spacing (or increase the inter-group spacing).

## Notes
- Always compare against `document.documentElement.clientWidth`, not `window.innerWidth` — in this
  preview they can differ, and `clientWidth` is the real layout width.
- Re-run the scanner after every CSS edit + reload; track the numbers across iterations so you can
  see a pillar move from NEEDS WORK to PASS.
```

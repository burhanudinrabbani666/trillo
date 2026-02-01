# BUILDING HEADER

**topics:**

- Why to use SVG icons vs font icons
- How to find, generate and use SVG .sprites in HTML.
- How to change of an SVG icon in CSS.
- How to use more advanced felxbox alignment technique, including justify-content, align-items, align-slef and flex.

---

Change the PNG icon to SVG for accessibility. SVG is easier for browsers to read.

```html
<svg class="search__icon">
  <use xlink:href="img/sprite.svg#icon-magnifying-glass"></use>
</svg>
```

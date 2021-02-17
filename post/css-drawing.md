# Drawing with CSS

```html
<div class="box-1"></div>
<div class="box-2"></div>
```

```css
/* position absolute allows us to position anywhere. */
div {
  position: absolute; 
}
div.box-1 {
  border:  1px solid red;
  /* set width, height, background to display shape */
  width: 200px;
  height: 200px;
   background: yellow;
  /* set top and left to set position (top and left works because we set div position to absolute) */
  top: 100px;
  left: 200px;

}
div.box-2 {
  border: 2px dashed teal;
  width: 120px;
  height: 40px;
  top: 80px;
  left: 320px;
}


```

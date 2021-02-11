# CSS Colors

Below is the HTML code we will use to practice using color-related CSS properties.

```html
<div class="container">
  <h1>Let's play with colors.</h1>
</div>
```

## Declared Colors
```css
h1 {
  color: teal;
}
```
You can use named color values such as `lightgray`, `floralwhite`, `bluevioluet`,etc. Check out [the whole list](https://css-tricks.com/snippets/css/named-colors-and-hex-equivalents/). This may be the simplest way to set colors although you may not find the exact color you need.


## RGB
```css
h1 {
  color: rgb(0, 255, 0); /* this will be full green. */
}
```
RGB color system uses three different color chanels &mdash; red, green and blue. Each channel values goes from `0` to `255`. This is how screen-based pixels work. You will find the same color system in Photoshop color picker.

## RGBA
```css
h1 {
  color: rgba(100, 200, 100, 0.5);
}
```
This is almost the same as RGB, but now we can also set the alpha (transparency) value from `0` to `1`. So, `0.5` will have 50% transparency.


## Transparency
```css
h1 {
  color: red;
  opacity: 0.3;
}
```
Use `opacity` property to set the opacity value separately.



## Hexadecimal
```css
h1 {
  color: #FF0000; /* same as red */
  color: #9AD199; /* light green-ish */
}
```
Hexadecimal color uses base-16 numbers. We are used to base-10 numbers(meaning, we use 10 different digits from 0 to 9) but base-16 will have 16 different digits from 0 to 9 *and* A to F. There are three color channels just like RGB, and each channel is made up of two digits. Each channel goes from `00` to `FF` (F is the highest single number) and anything inbetween such as `0F`, `CA`, `9C`, etc.


## HSL
```css
h1 {
  color: hsl(30, 100%, 50%); /* orange */
}
```
HSL stands for hue, saturation and lightness. You can think of a color wheel. Hue goes from `0` to `360`, saturation and lightness go from `0%` to `100%`. Again, look at Photoshop color picker to get a better idea on how this works.

## HSLA
```css
h1 {
  color: hsla(180, 100%, 50%, 0.7);
}
```
HSLA is the same as HSL but with added opacity control.

## Gradients
It may be difficult to create a CSS gradient from scratch. However, you can find [many CSS gradient generators](https://www.google.com/#q=css+gradient+generator) such as [this one](http://angrytools.com/gradient/). Try a few and find the one that works for you. Here is a [good reference](http://www.w3schools.com/css/css3_gradients.asp) on how to use the gradients.

### Linear Gradients
```css
div.container {
  background: -webkit-linear-gradient(left, #FF0000 0%, #FFFF00 50%, #ff0000 100%); 
}
```

### Radial Gradients
```css
div.container {
  background:-webkit-radial-gradient(center, ellipse cover, rgba(145,149,255,1) 0%, rgba(0,128,128,1) 100%); /* safari5.1+,chrome10+ */
}
```

## Further learning
If you want to experiment with different color palettes, try [Adobe Color CC](https://color.adobe.com).

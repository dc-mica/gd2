# CSS Layout: Position

CSS is used to visually style a webpage. It is relatively easy to style individual element such as font size, weight, color, because you can google for the right property name and its values and simply apply rules. But, laying out a page takes more planning as you will have to think about the structure and relationship among multiple elements. _Understanding the relationship among different elements_ is important.

There are multiple ways to design a layout using CSS. Here, we will look at `position` property. 

Below is a code template we will use for this posting:
```html
<div class="box-1">box 1</div>
<div class="box-2">box 2</div>
<div class="box-3">box 3</div>
```
```css
div {
  background-color: grey;
  margin: 20px;
  width: 200px;
  height: 50px;
}
```

## Position property and its values
`position` property takes one of the four values, `static`, `relative`, `fixed` and `absolute`.

## static
This is the default positioning for any element, meaning you don't have to specify it because... it's default. With the position set to `static`, or by *not* specifying it, it will follow the regular document flow - from top to bottom and from left to right.

```css
.box-1 {
  position: static;
}
```
Above will *not* have any effect on your box 1. If you want to move things around, then you will have to *position* with other values. See below for the other values.

  
## relative
If you want to move your elements *relative* to its normal position, use `position: relative;`. 

```css
.box-2 {
  position: relative;
}
```

Setting the position to `relative` alone will not have any impact on the position of your element. After setting the position, you need to set the offset using `top`, `left`, `bottom` and/or `right`. For example, if you want to push your 2nd box 10px from left and 20px from top, you will set it like: 

```css
.box-2 {
  position: relative;
  left: 10px;
  top: 40px;
}
```

Or, if you want to set the reference point from the right/bottom edges, then:

```css
.box-2 {
  position: relative;
  bottom: 40px;
  right: 10px;
}
```

Use whichever method you feel more comfortable. They can also take negative values.

One more important thing to notice here is that, when I positioned the 2nd box, the boxes around it stay the same and they don't try to fill in any gaps. That's because when you set an element `relative`, it keeps its original space so that other elements cannot take it over. This is a big difference between `relative` and `absolute`.

To recap, you have to remember 2 important things about `relative` positioning:
1. Any custom positioning you set with `relative` will be relative to its normal position.
1. Elements with `relative` position will keep its original space and other elements cannot take the space.

## absolute
Let's change just one line from the previous styling:
```css
.box-2 {
  position: absolute;
  bottom: 40px;
  right: 10px;
}
```
What just happened?! The box is now at the bottom-right corner of the page. When you set the position `absolute`, the element is positioned *relative* to its first *positioned* (not static) ancestor element. That's mouthful. To break it down, here is what happens. 

When you set the position absolute, first, your element will look at its parent whether it is *positioned* (any position value other than `static`). If the parent is not positioned, then it will go up the hierarchy and look at the parent of the parent element. It does so until it finds an ancestor that is positioned. Then, it will be relative to that ancestor element's position. What if it cannot find any positioned ancestors just like in our case here? Then, it will position itself relative to the entire document. That's why the box is now placed at the bottom-right corner.

As if this was not enough to make your head spin, there is one more important thing to know. Notice that when you position the box-2 absolute, it is taken out of the regular document flow, so the other elements *can* take up its original space.

### grouping things together
To make the box positioned relative to its positioned ancestor, change the code as below:

```html
<div class="box-parent">
  <div class="box-1">box 1</div>
  <div class="box-2">box 2</div>
  <div class="box-3">box 3</div>
</div>
```

```css
div {
  background-color: grey;
  margin: 20px;
  width: 200px;
  height: 50px;
}

.box-parent {
  position: relative;
  background-color: transparent;
  border: 0;
}

.box-2 {
  position: absolute;
  top: 20px;
  left: 20px;
}



```
In the example above, we have one more level of hierarchy with `.box-parent`. Because `.box-parent` is positioned, `div.box-2`'s absolute position will be relative to its parent, `.box-parent`. If you now move the parent element `.box-parent`, all the children element will move together. This is great when you want to move an entire module.
  
## fixed
To see what `fixed` position does, we will use a different code example.
```html
<div class="box-1">box 1</div>
<div class="box-2">box 2</div>
<div class="box-3">box 3</div>
```

```css
div {
  background-color: grey;
  margin-bottom: 600px;
  width: 400px;
  height: 150px;
}

.box-2 {
  position: fixed;
  top: 100px;
  left: 100px;
}
```

`fixed` position works almost the same as `absolute` except that it does not scroll with other elements. Many websites use `fixed` positioning for the top navigation so that it is always visible, but it can cause some problems for mobile devices.

## Recap
- static: the default setting. don't worry about it.
- relative: relative to its normal position. other elements will still honor the space.
- absolute: relative to the closest positioned ancestor. taken out of the regular document flow.
- fixed: same as absolute except that it does not scroll.


## Practice
See if you can recreate these compositions. What position value would you use?:

<img src="../images/css-position-practice/001.png" width="40%" style="float: left; margin-right: 5%;">
<img src="../images/css-position-practice/002.png" width="40%" style="float: left; margin-right: 5%;">
<img src="../images/css-position-practice/003.png" width="40%" style="float: left; margin-right: 5%;">
<img src="../images/css-position-practice/004.png" width="40%" style="float: left; margin-right: 5%;">

## Further learning
- [Don't Fear the Internet - Layout](https://vimeo.com/137320138)
- http://learn.shayhowe.com/html-css/positioning-content/

# Box Model

Remember this: everything is a rectangular box. Every HTML element - `h1`, `p`, `div` - is a rectangular box even though they don't look like one. A quick way to see this is to add an outline around each element temporarily. Choose an element and add a CSS rule like this:

```css
p {
  outline: 1px solid red; /* width style color */
}
```
Now you will see a thin red outline around your `p` element. Of course, you should have some text in the paragraph. Otherwise, you won't see anything.

So, in positioning and styling the HTML elements, we are working with boxes. And there are a few things to know to handle these boxes. We call this a *box model*.

A box is made up of four parts - content, padding, border and margin. You may enable or disable some of the parts.

![css box model](../images/css-box-model.png)

## Content
Let's first take a look at a content. A content is the text you write between the pair of html tags.

```html
<div>This is my content.</div>
```
The width and height are automatically determined by the length of your content and the size of the browser window. The `<div>` is a block-level element, so by default, the width is the same as the browser window width. Try adding a red outline around the `<div>` and see how far the border stretches:

```css
div {
  outline: 1px solid red;
}
```

If you want to use the custom width for your html element, then add `width` CSS property. Then, your width will always be 200 px regardless of the content length:

```css
div {
  outline: 1px solid red;
  width: 200px;
}
```

You can set the height the same way:

```css
div {
  outline: 1px solid red;
  width: 200px;
  height: 200px;
}
```
*Note: Without contents, the box will not have any width and height. In this case, you will have to manually set the width and height in CSS because it is an empty element.*

## Padding
If you want to add some spㅁcing between your content and the border, then use padding. Remember when you use the padding, that we are adding space inside the box:

```css
div {
  outline: 1px solid red;
  padding: 20px; /* add 20px padding on all sides. */
  width: 200px;
  height: 200px;
}
```

If you want to add a padding only on one side, there are `padding-top`, `padding-right`, `padding-bottom` and `padding-left`.

```css
div {
  outline: 1px solid red;
  padding-left: 20px; /* add 20px padding on the left. */
  width: 200px;
  height: 200px;
}
```

If you want padding values different for each side, there is a shorthand notation.

```css
div {
  padding: 20px 30px 20px 50px; /* the order - top right bottom left */
}
```

## Border
We have been using the outline to temporarily visualize the box. If you want to have a border as the actual visual element, then use `border` property. Let's take a look at this.

```css
div {
  border: 1px solid red;
}
```

If you want the border only on one side, there are `border-top`, `border-right`, `border-bottom` and `border-left`.

```css
div {
  border-left: 5px solid grey;
}
```

If you've been using `<hr>` to add a horizontal line, `border-top` or `border-bottom` combined with some `padding` can replace it and will give you more options for styling. No more awkward `<br>`s!

```html
<h1>Heading 1</h1
```
```css
h1 {
  padding-bottom: 20px;
  border-bottom: 2px dashed grey;
}
```

## Margin
The margin defines the spacing *between* different html elements. This is the spacing outside the box. Let's first draw 2 divs.
```html
<div class="box-1">Box 1</div>
<div class="box-2">Box 2</div>
```

Without any styling, these are just boring boxes. Let's do some basic styling first.

```css
div.box-1 {
  border: 1px solid red;
  width: 200px;
  height: 200px;
}
div.box-2 {
  border: 1px solid red;
  width: 200px;
  height: 200px;
}
```
Then, we will add different margin for each div:
```css
div.box-1 {
  border: 1px solid red;
  width: 200px;
  height: 200px;
  margin: 50px;
}
div.box-2 {
  border: 1px solid red;
  width: 200px;
  height: 200px;
  margin: 20px;
}
```
Now, the boxes are pushed 50px and 20px from all sides, respectively. Play with different values.

The code above should work fine, but it's too many repetitions. CSS is called *cascaded* for a reason. Let's restructure our code:
```css
div {
  border: 1px solid red;
  width: 200px;
  height: 200px;
}
div.box-1 {
  margin: 50px;
}
div.box-2 {
  margin: 20px;
}
```
The code above gives you the same result with less code.


## Box sizing
You might have noticed that anytime you change padding or border, it also affects the oveall width/height of your element. If you want to keep the overall width/height same no matter how much padding you add on top of that, you want to use `box-sizing` property:

```html
<div>Another box</div>
```

```css
div {
  box-sizing: border-box; /* we will consider padding and border part of the overall box width. */
  width: 200px;
  height: 200px;
  border: 50px solid black; /* try changing the border width to 20px, 60px, ... The overal width doesn't change. */
}
```
-----

*Exercise: Create an interesting color composition using CSS. Look for some inspirations such as [De Stijl](https://www.google.com/search?q=Theo+van+Doesburg&espv=2&biw=1597&bih=916&source=lnms&tbm=isch&sa=X&ved=0ahUKEwid4-m8v-_RAhWMOCYKHdSQDEgQ_AUIBigB#tbm=isch&q=de+stijl)([Piet Mondrian](https://www.google.com/search?q=piet+mondrian&source=lnms&tbm=isch&sa=X&ved=0ahUKEwjCkaT_vu_RAhUGyyYKHdFQAysQ_AUICCgB), [Theo van Doesburg](https://www.google.com/search?q=Theo+van+Doesburg&espv=2&biw=1597&bih=916&source=lnms&tbm=isch&sa=X&ved=0ahUKEwid4-m8v-_RAhWMOCYKHdSQDEgQ_AUIBigB)), [Frank Stella](https://www.google.com/search?q=frank+stella&source=lnms&tbm=isch&sa=X&ved=0ahUKEwjK65-Jv-_RAhUGOSYKHZXCCM4Q_AUICCgB&biw=1280&bih=698)*

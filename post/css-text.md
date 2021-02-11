# CSS Text Properties
In this section, we will look at several CSS properties related to typography. We will use the HTML code below:
```html
<div class="section">
  <h2>Web browser</h2>
  <p>
  A web browser (commonly referred to as a browser) is a software application for retrieving, presenting and traversing information resources on the World Wide Web. An information resource is identified by a Uniform Resource Identifier (URI/URL) that may be a web page, image, video or other piece of content.[1] Hyperlinks present in resources enable users easily to navigate their browsers to related resources.
  </p>
</div>
```

## Font family
```css
h2 {
  font-family: Helvetica, Arial, sans-serif;
}
p {
  font-family: "Times New Roman", serif;
}
```
Notice that you can use any fonts you have installed but your audience may not have the same fonts. In that case, we cannot guarantee how it will be displayed. So the example above have a few *fallback* fonts. In the case of `h2`, it will try to show text in Helvetica first, if it doesn't exist, then it will try Arial, and if it also doesn't exist, at least, it will try to use any sans-serif fonts available.

For the font name is longer than one word as in `Times New Roman`, surround the name with double quotes.

## Font size
```css
h2 {
  font-size: 48px;
}
```
There are many different measuring units in CSS. Here, we will use pixels(`px`).

## Font style
```css
h2 {
  font-style: italic;
}
```

## Font weight
```css
h2 {
  font-weight: bold;
}
```
You can set font weight like `normal` or `bold`. Or, you can set it in numbers from `100` to `900` with the increment of 100.

## Text color
```css
h2 {
  color: #cc0000;
}
```

## Text transform
```css
h2 {
  text-transform: uppercase;
}
```
Try `uppercase`, `lowercase` and `capitalize`.

## Letter spacing
```css
h2 {
  letter-spacing: 3px;
}
```
The default value is `0`.

## Word spacing
```css
h2 {
  word-spacing: 20px;
}
```

## Line height
```css
p {
  line-height: 2;
}
```
The value will be multiplied with the current font size to determine the line height.


## Using web fonts
Instead of relying on the system fonts, you canlink to any web fonts. The popular services include [Google Fonts](http://fonts.google.com) and [Adobe Typekit](http://typekit.com). Below is how you can link any web fonts to your webpage.

First, visit the [Google Fonts website](http://fonts.google.com) and choose a font you want to use. I chose Merriweather. You will get the HTML link tag that looks like this:

```html
<link href="https://fonts.googleapis.com/css?family=Merriweather" rel="stylesheet">
```

You can copy the line above and paste it inside the `<head>` tag in your html file. Then, anytime you want to use this font, include it as `font-family` like this:

```css
p {
  font-family: 'Merriweather', serif;
}
```

You can try many fonts with many weights and styles when you practice, but in real situations, loading up multiple web fonts can increase the loading time of your page. So, be conservative and use the ones that you really need.

## Text shadow
```css
h2 {
  text-shadow: 3px 6px 2px grey;
}
```
The text shadow used to be a cool thing in the...80s. What do those four values mean? They are horizontal offset, vertical offset, blur radius and shadow color. You can do some cool trick by overlaying multiple shadows - look at [this example](http://codepen.io/chriscoyier/pen/urkCd).

## Further learning
If you want to know more about CSS typography, here is [a good chapter](http://learn.shayhowe.com/html-css/working-with-typography/) on it.



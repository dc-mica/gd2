# CSS Basics

Cascading Style Sheet or CSS defines the appearance of your web page. Note that it is important to separate the contents (HTML) and the visual presentation (CSS).

## How to add CSS rules
There are three different ways (inline, style tag or external css file) to add CSS style to your webpage. For now, we will place `<style>` tag inside `<head>`.
```html
<html>
  <head>
    ...
    <style>
      /* add your CSS rules here. */
    </style>
  <head>
  <body>
    ...
  </body>
</html>
```

## CSS Selectors
A CSS rule at minimum is made up of a selector, a css property and its value.
```css
selector {
  property: value;
}
```

There are five different types of selectors:
  - element selector: `p` selects `<p>`, `div` selects `<div>`
  - ID selector: `#active` selects `<div id="active">` or `<li id="active">`
  - class selector: `.date` selects `<div class="date">` or `<span class="date">`
  - Attribute selector
  - Pseudo class selector

If you want all your `h1`s to be set in sans-serif, you can set it as below. All the `h1`s on your page will be affected.
```css
h1 {
  font-family: sans-serif;
}
```

If you want to be more specific with your selection, use class instead of element name. For example, you only want to set the background color for sidebars that are using `div`s, you may add a class to your html element as `<div class="sidebar">`and use a class selector in your CSS:
```css
.sidebar {
  background-color: #ccc;
}
```
or, below will be more specific as we use both element selector and class selector:
```css
div.sidebar {
  background-color: #ccc;
}
```

## Specificity
But, what will happen if two different selectors are targeting at the same element? The class selector has a higher specificity, so it will be set in red:
```css
.sidebar {
  background-color: red;
}
div {
  background-color: yellow;
}
```

## The order of the CSS rules
The order of the CSS rules matters. The browser will read your CSS style from top to bottom, line by line. So, even if you set some property at the top, it may be overridden somewhere at the bottom. This behavior can make finding problems very difficult. My advice is to put more generic rules at the top and more specific rules at the bottom.
```html
<div>Hello</div>
<div class="box">there</div>
```
```css
div {
  background-color: yellow;
}
div.box {
  background-color: brown;
}
```

## How to find the right CSS properties and values
There are hundreds of CSS properties and it is just not practical to try to remember all of them. Instead, when you have a question, google with the right keywords, for example, *CSS gradient* and more often than not, the answer you are looking for should be on the first page.

You can also refer to [MDN CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference).

## Further learning
http://learn.shayhowe.com/html-css/getting-to-know-css/


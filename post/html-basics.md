# HTML Basics

HTML(Hypertext Markup Language) and CSS(Cascading Style Sheet) are the two main languages of the web.

As you have seen from the structural analysis exercise, you need to think in terms of system and structure to design for the web. When we work on print design projects, we may also form a mental image of these structures, it is just more explicit on the web that all the content structure is described with HTML and all the visual presentation is done with CSS.

Remember that HTML (Hypertext Markup Language) is all about describing the content structure and it has nothing to do with the visual. All the visual aspect is handled with CSS (Cascading Stylesheet).

Most of the time, you will have to go back and forth between HTML tags and CSS rules. Everytime you add an HTML element or CSS rule, think about how it will work within a system.

## HTML main structure
```html
<!DOCTYPE html>
<html>
  <head>
    <!-- 
      information on the webpage. not part of the main contents. 
    -->
  </head>
  <body>
    <!-- 
      anything you want to display on the webpage. 
    -->
  </body>
</html>
```
The first line `<!DOCTYPE html>` tells a browser that this document is written in HTML5. There are other kinds of doctypes, but this is the only version we need to remember.

Now, we have a pair of html tags, first opening with `<html>` and closing with `</html>`.

Note that the hierarchy of html elements are expressed visually with indentations, usually one tab length. This is not required but it helps us to read the code better and minimize the mistakes.

### Head
```html
<head>
  <meta charset="utf-8">
  <title>Welcome to My Website</title>
</head>
```
Between the `<head></head>`, we could put a lot of information about the page. This part is not displayed on the page. Rather, it contains meta data. 

### Body
```html
<body>
  <h1>Your Heading.</h1>
  <p>a paragraph of text.</p>
</body>
```
All the webpage contents will be placed within `body` element.




## Headings
```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```
The visual representation of each heading is pre-determined by your browser. The default style should be overridden by your own CSS styles. 




## text
```html
<p></p>
<br>
<em></em>
<strong></strong>
<blockquote></blockquote>
```

### p
`p` is for a paragraph of text. Each paragraph should be contained within a `<p></p>` pair.

### br
`br` is for a line break. Each line of a poem or lyrics, for example, is not really a paragraph. So, that will be a good example for using `br`. But, do not use it to create an arbitrary amount of space between *paragraphs*. The spacing between paragraphs should be handled with CSS, using margins and paddings.

### em & strong
`em` and `strong` are two ways to make your text stand out. The browser will render `em` as italics, and `storng` as bolds, but that can always be changed with your own CSS rules. You should use them based on your text's semantic meaning, not because of their visual appearances.

### blockquote
If you want to quote a text phrase or a paragraph, use `blockquote`. Not all quotes are the same. Check out the differences among [different types of quotes](https://www.smashingmagazine.com/2008/06/block-quotes-and-pull-quotes-examples-and-good-practices/).




## Link
```html
Check out my <a href="http://paperdove.com">website</a>.
```
Web pages are linked to each other by hyperlinks. `<a>` or anchor tag is a way to link to other pages (or you could link to a different part of the same page as well). 

If you want to open the link in a new window or a new tab, add `target` attribute as below:
```html
Check out my <a href="http://paperdove.com" target="_blank">website</a>.
```




## Image
```html
<img src="http://mywebsite.com/myimage.jpg" alt="alternative text">
```




## Lists
```html
<h2>Groceries List</h2>
<ul>
  <li>Water</li>
  <li>Bread</li>
  <li>Orange Juice</li>
</ul>

<h2>My Recipe</h2>
<ol>
  <li>Boild the water.</li>
  <li>Cook pasta in boiling water for 10 minutes.</li> 
  <li>Mix with sauce.</li>
</ol>
```




## Generic Containers

```html
<div></div>
<span></span>
```

`div` and `span` do not have any meanings attached to them unlike headings, lists and other elements we saw. They are used to style either a single element or a group of elements together. They are normally used with a *class*.




## Class
```
<div class="article">
  <h2>The article title</h2>
  <p>Some text.</p>
</div>

<div class="bio">
  <p>Hi, my name is John. Nice to meet you.</p>
</div>
```
We use `div`s to style contents. But if we style a `div` directly, every `div` element on the page will be affected. Use a class to target a specific element. (Of course, you can use classes with any other HTML elements.)



## Comments
```html
<!-- This part will not be rendered on a page. -->

<!--
  But! if you look at the source from your browser, it will be seen.
-->
```
You can add notes to yourself using an HTML comment. Or, it can be used to test out a block of code.




## Further Learning
- [Khanacademy Intro to HTML/CSS](https://www.khanacademy.org/computing/computer-programming/html-css)
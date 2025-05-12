# HTML Styles - CSS

### What is CSS?

Cascading Style Sheets (CSS) is used to format the layout of a webpage.

With CSS, you can control the color, font, the size of text, the spacing between elements, how elements are positioned and laid out, what background images or background colors are to be used, different displays for different devices and screen sizes, and much more!

<mark>**Tip**: The word **cascading** means that a style applied to a parent element will also apply to all children elements within the parent. So, if you set the color of the body text to "blue", all headings, paragraphs, and other text elements within the body will also get the same color (unless you specify something else)!</mark>

### Using CSS

CSS can be added to HTML documents in 3 ways:

- **Inline** - by using the `style` attribute inside HTML elements
- **Internal** - by using a `<style>` element in the `<head>` section
- **External** - by using a `<link>` element to link to an external CSS file

The most common way to add CSS, is to keep the styles in external CSS files. However, in this tutorial we will use inline and internal styles, because this is easier to demonstrate, and easier for you to try it yourself.

### Inline CSS

An inline CSS is used to apply a unique style to a single HTML element.

An inline CSS uses the `style` attribute of an HTML element.

### Internal CSS

An internal CSS is used to define a style for a single HTML page.

An internal CSS is defined in the `<head>` section of an HTML page, within a `<style>` element.

```html
<!DOCTYPE html>
<html>
    <head>
        <style>
            body {background-color:powderblue;}
            h1 {color:blue;}
            p {color:red;}
        </style>
    </head>
    <body>
        <h1>
            This is a heading.
        </h1>
        <p>
            This is a paragraph.
        </p>
    </body>
</html>
```



### External CSS

An external style sheet is used to define the style for many HTML pages.

To use an external style sheet, add a line to it in the `<head>` section of each HTML page:

```html
<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" href="styles.css">
    </head>
    <body>
        <h1>
            This is a heading.
        </h1>
        <p>
            This is a paragraph.
        </p>
    </body>
</html>
```

The external style sheet can be written in any text editor. The file must not contain any HTML code, and must be saved with a .css extension.

Here is what the "styles.css" file looks like:

```css
body {
    backfround-color: powderblue;
}
h1 {
    color: blue;
}
p{
    color: red;
}
```



### Some common CSS properties

- **`color`**
- **`font-family`**
- **`font-size`**
- **`border`**
- **`padding`**
- **`margin`**
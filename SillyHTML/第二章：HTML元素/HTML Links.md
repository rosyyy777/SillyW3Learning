# HTML Links

HTML links are hyperlinks. You can click on a link and jump to another document. When you move the mouse over a link, the mouse arrow will turn into a little hand.

<mark><strong>Note: </strong>A link does not have to be text. A link can be an image or any other HTML element!</mark>

## HTML links - Syntax

The HTML `<a>` tag defines a hyperlink. It has the following syntax:

`<a href="url">link text</a>`

- **`href`**
  - The most important attribute of the `<a>` element is the `href` attribute, which indicates the link's destination.
- **`target`**
  - By default, the linked page will be displayed in the current browser window. To change this, you must specify another target for the link.
  - The `target` attribute can have one of the following values:
    - `_self` - Default. Opens the document in the same window/tab as it was clicked.
    - `_blank` - Opens the document in a new window or tab.
    - `_parent` - Opens the document in the parent frame.
    - `_top` - Opens the document in the full body of the window.


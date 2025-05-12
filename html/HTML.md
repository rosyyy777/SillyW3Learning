# HTML Basic

## HTML Styles

Setting the style of an HTML element, can be done with the `style` attribute.

`<tagname style="property:value;">`

The ***property*** is a CSS property. The ***value*** is a CSS value.

CSS property you can set:

- `background-color`
- `color`: the text color
- `font-family`: the font to be used
- `font-size`
- `text-align`

## HTML Text Formatting

- `<b>` - <b>Bold text</b>
- `<strong>` - <strong>Important text</strong>
- `<i>` - <i>Italic text</i>
- `<em>` - <em>Emphasized text</em>
- `<mark>` -  <mark>marked text</mark>
- `<small>` - <small>smaller text</small>
- `<del>` - <del>Deleted text</del>
- `<ins>` - <ins>Inserted text</ins>
- `<sub>` - <sub>Subscript text</sub>
- `<sup>` - <sup>Superscript text</sup>

## HTML Quotation and Citation Elements

- `<blockquote>` 

  - defines a section that is quoted from another source. Browsers usually indent `<blockquote>` elements.

  - <blockquote cite="http://www.worldwildlife.org/who/index.html">
        For 60 years, WWF has worked to help people and nature thrive. As the world's leading conservation organization, WWF works in nearly 100 countries. At every level, we collaborate with people around the world to develop and deliver innovative solutions that protect communities, wildlife, and the places in which they live.
    </blockquote>

- `<q>` 

  -  The HTML `<q>` tag defines a short quotation. 

  - Browsers normally insert quotation marks around the quotation.

  - <p>WWF's goal is to: <q>Build a future where people live in harmony with nature.</q></p>

- `<abbr>` 

  - The HTML `<abbr>` tag defines an abbreviation or an acronym, like "HTML", "CSS", "Mr.", "Dr.", "ASAP", "ATM".

  - Marking abbreviations can give useful information to browsers, translation systems and search-engines.

  - **Tip:** Use the global title attribute to show the description for the abbrevation/acronym when you mouse over the element.

  - <p>The <abbr title="World Health Organization">WHO</abbr> was founded in 1948.</p>

- `<address>`

  - The HTML `<address>` tag defines the contact information for the author/owner of a document or an article.

  - The contact information can be an email address, URL, physical address, phone number, social media handle, etc.

  - The text in the `<address>` element usually renders in italic, and browsers will always add a line break before and after the `<address>` element.

  - <address>
        Written by John Doe.<br>
        Visit us at:<br>
        Example.com<br>
        Box 564, Disneyland<br>
        USA
    </address>

- `<cite>`

  - The HTML `<cite>` tag defines the title of a creative work (e.g. a book, a poem, a song, a movie, a painting, a sculpture, etc).

  - **Note:** A person's name is not the title of a work.

  - The text in the `<cite` element usually renders in italic.

  - <p><cite>The Scream</cite> by Edvard Munch. Painted in 1893.</p>

- `<bdo>`

  - BDO stands for Bi-Directional Override.

  - The HTML `<bdo>` tag is used to override the current text direction:

  - <bdo dir="rtl">This text will be written from right to left.</bdo>

## HTML Comments

HTML comments are not displayed in the browser, but they can help documeny your HTML source code.

- ```html
  <!-- This is a comment -->
  
  <p>
      This is paragraph.
  </p>
  
  <!-- Remeber to add more information here -->
  ```

## HTML Colors

HTML colors are specified with predefined color names, or with RGB, HEX, HSL, RGBA, or HSLA values.

- **color names:** HTML supports 140 standard color names, e.g., tomato, orange, dodgerBlue, mediumseagreen, gray, slateblue, violet, lightgray
- **background color**
- **text color**
- **border color**
- **color values: **
  - In HTML, colors can also be specified using RGB values, HEX values, HSL, values, RGBA values, and HSLA values.
- **RGB color values: **
  - In HTML, a color can be specified as an RGB value, using this formula: `rgb(red, green, blue)`. Each parameter (red, green, blue) defines the intensity of the color with a value between 0 and 255.
  - There are 256 $\times$ 256 $\times$ 256 = 16777216 possible colors!
- **RGBA Color Values: **
  - **Definition:** RGBA color values are an extension of RGB color values with an Alpha channel - which specifies the opacity (不透明度) for a color.
  - ***rgba(red, green, blue, alpha)***
  - The alpha parameter is a number between 0.0 (fully transparent) and 1.0 (not transparent at all).
- **HEX Colors**
  - A hexadecimal color is specified with: #RRGGBB, where the RR(red), GG(green) and BB(blue) hexadecimal integers specify the components of the color.
  - In HTML, a color can be specified using a hexadecimal value in the form: ***#rrggbb***, where rr(red), gg(green) and bb(blue) are hexadecimal values between 00 and ff(same as decimal 0-255).
  - For example, #ff0000 is displayed as red, because red is set to its highest value(ff), and the other two (green and blue) are set to 00.
- **HSL Color Values**
  - HSL stands for hue, saturation and lightness. In HTML, a color can be specified using hue, saturation, and lightness (HSL) in the form: **`hsl(hue, saturation, lightness)`**
  - Hue (色相) is a degree on the color wheel form 0 to 360. 0 is red, 120 is green, and 240 is blue. 
  - Saturation (饱和度) is a percentage value. 0% means a shade of gray, and 100% is the full color.
  - 颜色的亮度意味着有多少光亮，0%意味着没有亮度（黑色）， 50%意味着50%的亮度（既不是暗也不是亮）， 100%意味着完全的亮度（白色）。
  - **Shades of Gray**
    - Shades of gray are often defined by setting the hue and saturation to 0, and adjusting the lightness from 0% to 100% to get darker/lighter shades.
- **HSLA Color Values**
  - HSLA color values are an extension of HSL color values, with an Alpha channel - which specifies the opacity for a color.
  - **form: ** **`hsla(hue, saturation, lightness, alpha)`**








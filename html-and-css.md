# HTML
- HTML stands for Hyper Text Markup Language
- HTML is the standard markup language for creating Web pages
- HTML describes the structure of a Web page
- HTML consists of a series of elements
- HTML elements tell the browser how to display the content
- HTML elements label pieces of content such as "this is a heading", "this is a paragraph", "this is a link", etc.

Example :
```html
<!DOCTYPE html>  
<html>  
<head>  
<title>Page Title</title>  
</head>  
<body>  
  
<h1>My First Heading</h1>  
<p>My first paragraph.</p>  
  
</body>  
</html>
```

Example Explained :
- The `<!DOCTYPE html>` declaration defines that this document is an HTML5 document
- The `<html>` element is the root element of an HTML page
- The `<head>` element contains meta information about the HTML page
- The `<title>` element specifies a title for the HTML page (which is shown in the browser's title bar or in the page's tab)
- The `<body>` element defines the document's body, and is a container for all the visible contents, such as headings, paragraphs, images, hyperlinks, tables, lists, etc.
- The `<h1>` element defines a large heading
- The `<p>` element defines a paragraph

An HTML element is defined by a start tag, some content, and an end tag:
`<tagname> Content goes here... </tagname>

The HTML **element** is everything from the start tag to the end tag:
`<h1>My First Heading</h1>`
`<p>My first paragraph.</p>`

**Note:** Some HTML elements have no content (like the `<br>` element). These elements are called empty elements. Empty elements do not have an end tag!

Web Browsers : The purpose of a web browser (Chrome, Edge, Firefox, Safari) is to read HTML documents and display them correctly. A browser does not display the HTML tags, but uses them to determine how to display the document.

### HTML Attributes
- All HTML elements can have **attributes**
- Attributes provide **additional information** about elements
- Attributes are always specified in **the start tag**
- Attributes usually come in name/value pairs like: **name="value"**

https://www.geeksforgeeks.org/most-commonly-used-tags-in-html/
https://www.geeksforgeeks.org/html-tags-a-to-z-list/


# CSS
- CSS stands for Cascading Style Sheets
- CSS describes how HTML elements are to be displayed on screen, paper, or in other media
- CSS saves a lot of work. It can control the layout of multiple web pages all at once
- External stylesheets are stored in CSS files

CSS is used to define styles for your web pages, including the design, layout and variations in display for different devices and screen sizes.
Example :
```css
body {  background-color: lightblue;
}  
  
h1 {  color: white;  
  text-align: center;
  }  
  
p {  font-family: verdana;  
  font-size: 20px;
  }
```

### CSS solved a big problem
HTML was NEVER intended to contain tags for formatting a web page!
HTML was created to describe the content of a web page, like:
`<h1>This is a heading</h1>`

When tags like `<font>`, and color attributes were added to the HTML 3.2 specification, it started a nightmare for web developers. Development of large websites, where fonts and color information were added to every single page, became a long and expensive process.

To solve this problem, the World Wide Web Consortium (W3C) created CSS.
CSS removed the style formatting from the HTML page!

### Syntax
A CSS rule consists of a selector and a declaration block.

![](attachments/Pasted%20image%2020240906152113.png)

The selector points to the HTML element you want to style.
The declaration block contains one or more declarations separated by semicolons.
Each declaration includes a CSS property name and a value, separated by a colon.
Multiple CSS declarations are separated with semicolons, and declaration blocks are surrounded by curly braces.

## CSS Selectors
A CSS selector selects the HTML element(s) you want to style.
CSS selectors are used to "find" (or select) the HTML elements you want to style.

We can divide CSS selectors into five categories:

- Simple selectors (select elements based on name, id, class)
- Combinator selectors (select elements based on a specific relationship between them)
- Pseudo-class selectors (select elements based on a certain state)
- Pseudo-elements selectors (select and style a part of an element)
- Attribute selectors (select elements based on an attribute or attribute value)

#### CSS Element Selector
The element selector selects HTML elements based on the element name.
#### CSS id Selector
The id selector uses the id attribute of an HTML element to select a specific element.
The id of an element is unique within a page, so the id selector is used to select one unique element!
To select an element with a specific id, write a hash (#) character, followed by the id of the element.
#### CSS class Selector
The class selector selects HTML elements with a specific class attribute.
To select elements with a specific class, write a period (.) character, followed by the class name.

#### CSS universal Selector
The universal selector (`*`) selects all HTML elements on the page.

#### CSS Grouping Selector
The grouping selector selects all the HTML elements with the same style definitions.

## Three Ways to Insert CSS
- External CSS
- Internal CSS
- Inline CSS

## CSS Box Model

In CSS, the term "box model" is used when talking about design and layout.

The CSS box model is essentially a box that wraps around every HTML element. It consists of: content, padding, borders and margins.

![](attachments/Pasted%20image%2020240906153923.png)

Explanation of the different parts:

- **Content** - The content of the box, where text and images appear
- **Padding** - Clears an area around the content. The padding is transparent
- **Border** - A border that goes around the padding and content
- **Margin** - Clears an area outside the border. The margin is transparent

The box model allows us to add a border around elements, and to define space between elements.

## Responsive Web Design
https://www.w3schools.com/css/css_rwd_intro.asp


# XHTML

# XML











## HTML

> What is the HTML ?

- **Stand For**
  - Hyper Text Markup Language
- **Definition**
  - **Text Formatting**
    - Standard text formatting language for creating web content and applications.
  - **Tags / Attributes**
    - Uses tags and attributes to structure information on web pages.

### Semantic

> What is semantic HTML ?

- **Definition:**
  - **Semantic Content**
  - Use of HTML Elements reinforce the semantics or meaning of the content
- **Purpose:**
  - **SEO**
    - Enhances SEO by providing context about the structure and purpose of the content.
- **Examples:**
  - `<header>`: Represents a header section.
  - `<nav>`: Defines a navigation bar.
  - `<main>`: Indicates the main content of the document.
  - `<article>`: Represents a self-contained piece of content.
  - `<footer>`: Defines a footer section of the document.

### Layout

> Explain the layout of HTML?

- **Specific**
  - Every website has a distinct layout designed to present content in a specific manner.
- **Semantic**
  - Different HTML5 elements are used to define various parts of a webpage:
    - `<header>`: Defines a header for a document or a section.
    - `<nav>`: Establishes a container for navigation links.
    - `<section>`: Specifies a section in a document.
    - `<article>`: Identifies an independent, self-contained article.
    - `<aside>`: Designates content aside from the main content, such as a sidebar.
    - `<footer>`: Defines a footer for a document or a section.

### Entities

> What are the entities in HTML?

- **Representing Characters**
  - Special codes representing characters that have a reserved meaning in HTML.
- **Example**
  - `&lt;` represents `<` (less than)
  - `&gt;` represents `>` (greater than)
  - `&amp;` represents `&` (ampersand)
  - `&quot;` represents `"` (double quote)
  - `&apos;` represents `'` (apostrophe)

### Encode

> Why is a URL encoded in HTML?

- Ensures special characters in a URL don't conflict with HTML code.
  - Preserves data integrity by representing reserved characters uniformly.
  - Allows for reliable data exchange in web applications.
- Converts non-ASCII characters into a format suitable for the Internet.
  - URL transmitted over the Internet is restricted to the ASCII character-set.
  - Non-ASCII characters are replaced with "%" followed by hexadecimal digits to maintain compatibility.

### HTML 5

> How are tags migrated from HTML4 to HTML5?

- **Semantic Transition:**
  - Emphasizes semantic tags like `<header>`, `<nav>`, and `<footer>` over generic `<div>` elements.
- **Attribute Updates:**
  - Adjusts attributes; replaces deprecated attributes with CSS, ensuring compatibility.
- **Deprecated Tags:**
  - Eliminates deprecated tags such as `<font>` and `<center>`, promoting modern alternatives.
- **New Features Utilization:**
  - Utilizes new features like `<section>`, `<article>`, and `<canvas>` for enhanced functionality.
- **Validation:**

  - Validates code using HTML5 validators to ensure adherence to the latest standards.

- **Example**

| Typical HTML4        | Typical HTML5                       |
| -------------------- | ----------------------------------- |
| `<div id="header">`  | `<header>`                          |
| `<div id="menu">`    | `<nav>`                             |
| `<div id="content">` | `<section>`                         |
| `<div id="post">`    | `<article>`                         |
| `<div id="footer">`  | `<footer>`                          |
| `<font>`             | `<span>`                            |
| `<center>`           | `<div style="text-align: center;">` |
| `<b>`, `<i>`, `<u>`  | `<strong>`, `<em>`, `<u>`           |

> Will HTML 5 work if I don't include `<!DOCTYPE html>` in the document?

- No, omitting `<!DOCTYPE html>` means the browser won't recognize the document as HTML5.
- Without it, HTML5 tags may not function correctly, leading to potential issues with rendering and functionality.

## Element

> What is the Element in HTML ?

- **Include**
  - An HTML element is defined by a start tag, some content, and an end tag.

### Different

> What is the difference between HTML elements and tags ?

- **Include**
  - **Element**
    - Encompass element name, attributes, and content.
  - **Tag**
    - Consist of opening tags (`<element>`) and closing tags (`</element>`).
- **Aim**
  - **Element**
    - Define the structure and purpose of specific parts of a webpage.
  - **Tag**
    - Indicate the beginning and end of an element.
- **Example**
  - **Element**
    - `<p class="example">This is a paragraph.</p>`
  - **Tag**
    - `<p>` (opening tag), `</p>` (closing tag).

## Tag

> What is the Tag ?

- **Definition:**
  - Tags are fundamental components of HTML elements.
  - Each tag consists of an opening tag, content, and an ending tag.
- **Composition:**
  - **Opening Tag:** Marks the beginning of an element and defines the element's type.
  - **Content:** Information or elements placed within the tags.
  - **Ending Tag:** Marks the closure of the element, ensuring proper structure.
- **Properties:**
  - HTML tags define various properties of elements in web documents.
  - Different tags have distinct properties based on their purpose and usage.
- **Types:**
  - **Closed Tags:** Tags that require no closing tag and stand alone.
  - **Unclosed Tags:** Tags that do not require a closing tag and are self-contained.

> What is the Type Tag ?

- **Open Closed Tag:**
  - **Definition:**
    - These tags consist of an opening tag (which marks the beginning of the content) and a closing tag (which marks the end of the content).
  - **Example:**
    - `<b>`Bold Text`</b>`
- **Closed Tags (Self-closing):**
  - **Definition:**
    - These tags do not require a separate closing tag because they don't contain content.
  - **Example:**
    - `<img src="image.jpg" alt="Description">`
- **Unclosed Tags (Self-contained):**
  - **Definition:**
    - Tags that do not require a closing tag and are self-contained.
  - **Example:**
    - `<br>` (Line break tag)

> Do all HTML tags have an end tag ?

No. There are some HTML tags that don't need a closing tag. For example: image , br tag.

> Does a <!DOCTYPE html> tag is a HTML tag?

- **Definition**
  - Not an HTML tag in the traditional sense.
- **Purpose**
  - **HTML5**
    - Informs the browser that the document is written in HTML5.
  - **Rendering**
    - Essential for proper rendering and parsing of the HTML document.

### List

#### Empty

> What are empty elements?

- **Not Content**
  - HTML elements without content between opening and closing tags.
- **Example**
  - `<br>`, `<hr>`, `<img>`

#### Heading

> How many types of heading does an HTML contain?

- **Six Types**
  - The HTML contains six types of headings which are defined with the h1 to h6 tags.
  - Each type of heading tag displays different text size from another.
  - So, h1 is the largest heading tag and h6 is the smallest one

#### Anchor

> How to create a hyperlink in HTML?

- **Anchor Tag**
  - HTML uses the anchor `<a>` tag to create hyperlinks linking one page to another.
  - Hyperlinks can appear in different styles:
    - **Unvisited link:** Displayed as underlined and blue.
    - **Visited link:** Displayed as underlined and purple.
    - **Active link:** Displayed as underlined and red.
- **Example**

```html
<a href="https://www.example.com">Visit Example Website</a>
```

#### Table

> Which HTML tag is used to display the data in the tabular form?

- **Table Tag**
  - Is used to display data in tabular form (row \* column).
  - It also manages the layout of the page,
  - e.g., header section, navigation bar, body content, footer section.
- **List**
  - A list of tags used while displaying the data in the tabular form:
    - `<table>`: Defines a table.
    - `<tr>`: Defines a row in a table.
    - `<th>`: Defines a header cell in a table.
    - `<td>`: Defines a regular cell in a table.
    - `<caption>`: Defines the table caption.
    - `<colgroup>`: Specifies a group of one or more columns in a table for formatting.
    - `<col>`: Used with `<colgroup>` to specify column properties.
    - `<tbody>`: Groups the body content in a table.
    - `<thead>`: Groups the header content in a table.
    - `<tfoot>`: Groups the footer content in a table.

#### Map

> What is an Image map ?

- **Definition:**
  - An image map is a graphic image with clickable regions that link to different web pages or resources.
- **Types:**
  - **Server-Side Image Maps:**
    - Defined in HTML with server-side processing for redirection.
    - More versatile but requires server-side scripting.
  - **Client-Side Image Maps:**
    - Defined in HTML with client-side scripting for redirection.
    - Easier to set up but relies on user's browser handling redirection.

#### Iframe

> How to create a nested webpage in HTML?

- **Iframe**
  - Creating a webpage within another webpage with using HTML elements like `<iframe>`.
- **Purpose:**
  - Incorporate external content or subpages seamlessly within the main webpage.
- **Example**
  ```html
  <iframe src="subpage.html" width="100%" height="500px" allowfullscreen></iframe>
  ```

> What is the use of an iframe tag?

- **Nested Webpage**
  - Embeds a separate webpage within the current webpage, creating a nested browsing experience.

#### Span

> What is the use of a span ?

- **Usage**
  - Apply specific styles to individual words or letters within a sentence.
  - Target and modify small portions of text without affecting the entire content.
  - Ideal for precise text formatting needs without altering the overall layout.
- **Example**
  - For adding color to text.
  - For adding background to text.
  - Highlighting specific words or phrases.

#### Ul , LI

> How do you keep list elements straight in an HTML file?

- **Best Practices**

  - **Indentation**
    - Indent list elements consistently for readability.
    - Use a standard number of spaces or tabs for indentation, ensuring uniformity across the document.
  - **Clear Separation**
    - Separate list items with a blank line or consistent spacing.
    - Maintain a clear distinction between items to enhance visual clarity.
  - **Proper Tag Structure**
    - Ensure correct usage of `<ul>` (unordered list) or `<ol>` (ordered list) tags for appropriate list types.
    - Nest `<ul>` or `<ol>` inside list items (`<li>`) to create sublists, maintaining a clear hierarchy.

- **Example**

```html
<ul>
  <li>First item</li>
  <li>Second item</li>
  <ul>
    <li>Subitem 1</li>
    <li>Subitem 2</li>
  </ul>
  <li>Third item</li>
</ul>
```

#### BR

> How many tags can be used to separate a section of texts?

- Multiple HTML tags can be used to separate sections of text:
  - `<div>` A generic container that divides content into distinct sections.
  - `<p>`: Defines a paragraph, separating text into meaningful blocks.
  - `<span>`: Used for smaller text sections or inline styling, allowing separation within a paragraph.
  - `<h1>` to `<h6>`: Headings, structuring text into hierarchical sections from most important (`<h1>`) to least important (`<h6>`).
  - `<hr>`: Represents a thematic break, creating a horizontal line to visually separate content.
  - `<br>`: Breaks the current line and moves the text flow to the next line.
  - `<blockquote>`: Defines a large quoted section. If you have a large quotation, put the entire text within `<blockquote>...</blockquote>` tags.

#### figure

> What is the use of figure tag in HTML 5?

**Question:**

> What is the purpose of the `<figure>` tag in HTML5?

- **Definition:**
  - `<figure>` encapsulates referenced content, providing semantic meaning.
- **Usage:**
  - Enhances accessibility and organization of multimedia elements.
- **Example:**
  ```html
  <figure>
    <img src="example.jpg" alt="Example Image" />
    <figcaption>Caption describing the image</figcaption>
  </figure>
  ```

#### figcaption

> What is the purpose of the `<figcaption>` tag in HTML5?

**Question:**

> What is the purpose of the `<figcaption>` tag in HTML5?

- **Definition:**
  - `<figcaption>` provides a descriptive caption for content within a `<figure>` element.
- **Usage:**
  - Enhances accessibility and user experience by adding concise descriptions to images or multimedia.
- **Example**

```html
<figure>
  <img src="example.jpg" alt="Example Image" />
  <figcaption>Caption describing the image</figcaption>
</figure>
```

#### Progress

> What is the difference between progress and meter tag?

- **Progress**
  - Displays completion progress of a task, represented as a percentage.
  - `<progress value="70" max="100"></progress>` (Indicates 70% completion)
- **meter**
  - Represents a scalar measurement within a known range, like disk usage or temperature.
  - `<meter value="30" min="0" max="100">30%</meter>` (Displays 30% within a 0-100 range)

#### SVG

> What is the SVG in html ?

- **Definition**
  - Is used for scalable vector graphics, enabling the creation of resizable shapes and images.
- **Example:**

```html
<svg width="200" height="100">
  <rect x="50" y="20" width="150" height="60" fill="blue" />
</svg>
```

#### Canvas

> What is the Canvas in html ?

- **Definition**
  - provides a drawing area for dynamic graphics, controlled through JavaScript.
- **Example**

```html
<canvas id="myCanvas" width="200" height="100" style="border:1px solid black;"></canvas>
```

## Attribute

### Required

> What is the use of the required attribute in HTML5?

- **Definition:**
  - Specifies that a form field must be filled out before submission.
- **Purpose:**
  - Ensures mandatory information is provided by users.
  - Prevents form submission if the required field is left blank.
  - Enhances user experience by indicating necessary information.
- **Example:**
  - `<input type="text" required>`  
    This input field must be filled out before the form can be submitted.

## Symbol

> How to insert a copyright symbol on a browser page?

- **Insert**
  - Can insert a copyright symbol by using` &copy`
  - When browser renders the HTML, it will display the copyright symbol instead of entity code.
  - **Symbol:** ©
- **Example:**
  ```html
  &copy; 2023 Your Company Name. All Rights Reserved.
  ```

## Style

> What is a style sheet?

- **Definition:**
  - A style sheet is a file or code snippet containing formatting instructions to define the visual presentation of a web document written in HTML, XML, or other markup languages.
- **Purpose:**
  - Provides a centralized way to control the layout, design, and appearance of multiple web pages.
  - Enhances consistency, improves readability, and simplifies maintenance by separating content from presentation.
- **Types:**
  - **CSS (Cascading Style Sheets):**
    - Most common type, used to style HTML documents.
  - **Sass and Less:**
    - CSS preprocessors, offering additional features and improved organization for styles.
  - **Frameworks (Bootstrap, Materialize):**
    - Pre-designed, customizable stylesheets built on top of CSS, simplifying web development.
- **Example (CSS File):**
  ```css
  body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    margin: 0;
    padding: 0;
  }
  h1 {
    color: #007bff;
  }
  .container {
    width: 80%;
    margin: 0 auto;
    padding: 20px;
    background-color: #ffffff;
  }
  ```

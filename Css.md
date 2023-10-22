## CSS

> What are the advantages of using CSS?

- **Separation of Concerns**
  - Separates content from presentation, improving code maintainability.
- **Consistent Styling**
  - Ensures consistent design across multiple pages of a website.
- **Maintenance:**
  - Minor style changes can be globally applied, ensuring consistent design across multiple pages.
- **Bandwidth**
  - Cached stylesheets reduce redundant downloads, optimizing bandwidth usage.
- **Faster Page Loading**
  - Lightweight files reduce loading time, improving user experience.
- **Responsive Design**
  - Allows easy adaptation to various screen sizes and devices.
- **Accessibility**
  - Enables creating accessible designs for users with disabilities.
- **Controlled Layout**
  - Provides precise control over page layouts and element positioning.

> What are the limitations of CSS?

- **Browser Compatibility:**
  - CSS may render differently across various browsers, leading to inconsistent designs.
- **No Support for Parent Selector:**
  - Currently, using CSS, you can’t select a parent tag.
- **Limited Dynamic Capabilities:**
  - CSS lacks robust interactivity and dynamic capabilities, which are better handled by JavaScript.
- **Cross Browser Issues:**
  - Some selectors behave differently in different browsers.

### Import

> How to include CSS in the webpage?

- **Internal CSS:**
  - CSS written within the HTML file, enclosed in `<style>` tags.

```html
<style>
  body {
    background-color: lightblue;
  }
</style>
```

- **External CSS:**
  - CSS in a separate file, linked using `<link>` tag in the HTML `<head>`.

```html
<link rel="stylesheet" href="styles.css" />
```

- **Inline CSS:**
  - CSS applied directly to an HTML element using the "style" attribute.

```html
<p style="color: green;">This is a green paragraph.</p>
```

### Element

#### Inline

#### Inline-Block

#### Block

#### Different

> What is the difference between inline, inline-block, and block Element?

- **Inline Elements**
  - **Definition:**
    - Flow along with text and do not start on a new line.
    - They only take up as much width as necessary.
  - **Behavior:**
    - Elements appear on the same line, allowing content to continue on the same line after the element.
  - **Example:**
    - `<span>`, `<a>`, `<strong>`
- **Inline-Block Elements:**
  - **Definition:**
    - Behave like inline elements but can have set dimensions and padding, similar to block elements.
  - **Behavior:**
    - Elements appear on the same line but can have defined width, height, margins, and padding.
  - **Example:**
    - `<img>`, `<button>`, `<div>` with `display: inline-block;`
- **Block Elements:**
  - **Definition:**
    - Start on a new line and take up the full width available, pushing subsequent elements to the next line.
  - **Behavior:**
    - Elements start on a new line, occupying the entire width, creating a visual block on the web page.
  - **Example:**
    - `<div>`, `<p>`, `<h1>`

### Pseudo

#### Element

> What is the Pseudo Element ?

- **Definition:**
  - A pseudo-element is a CSS feature that allows you to style a specific part of an element's content or generate content that doesn't exist in the HTML document.
- **Syntax:**
  - Pseudo-elements are denoted by double colons (`::`) preceding the name (e.g., `::before`, `::after`).
- **Usage:**
  - Commonly used to insert decorative elements, modify specific parts of text, or style generated content without adding extra HTML markup.
- **Example:**
  - The `::before` pseudo-element can be used to insert content before the actual content of an element.
    ```css
    .element::before {
      content: "→ ";
      color: green;
    }
    ```

#### Class

> What is the Pseudo Class ?

- **Definition:**
  - Define the special state of an element when interacting with the user or document structure.
- **Usage:**
  - Prefixed with `:` in CSS selectors (e.g., `:hover`, `:first-child`).
- **Example:**
  - `:hover` styles an element when the mouse pointer is over it.
- **Purpose:**
  - Enables styling based on user interaction or element position within a document.

#### Different

> What is different between Pseudo elements and Pseudo classes?

- **Pseudo-Elements:**
  - **Definition:**
    - Create virtual elements in the document to style specific parts of an element's content.
  - **Usage:**
    - Prefixed with `::` in CSS selectors (e.g., `::before`, `::after`).
  - **Example:**
    - `::before` creates a pseudo-element before an element's actual content.
  - **Purpose:**
    - Used for decorative elements or additional content without altering the HTML structure.
- **Pseudo-Classes:**
  - **Definition:**
    - Define the special state of an element when interacting with the user or document structure.
  - **Usage:**
    - Prefixed with `:` in CSS selectors (e.g., `:hover`, `:first-child`).
  - **Example:**
    - `:hover` styles an element when the mouse pointer is over it.
  - **Purpose:**
    - Enables styling based on user interaction or element position within a document.

### Position

> What is the CSS Position Property?

- **Definition:**
  - Determines the positioning method of an element within its containing element.
- **Values:**
  - **`static`:**
    - Default value; elements are positioned according to the normal document flow.
  - **`relative`:**
    - Positioned relative to its normal position in the document flow.
  - **`absolute`:**
    - Positioned absolute to its nearest positioned ancestor or the containing block.
  - **`fixed`:**
    - Positioned relative to the viewport, remains fixed even when scrolling.
  - **`sticky`:**
    - Acts like `relative` until it reaches a specified point during scrolling, then becomes `fixed`.

### Hidden

> What are the different ways to hide the element using CSS?

- **`display: none;`:**
  - Removes element from layout and document flow.
- **`visibility: hidden;`:**
  - Hides element, preserves layout space.
- **`opacity: 0;`:**
  - Renders element transparent, preserves space.
- **`position: absolute;` or `fixed;` with `top: -9999px;` or `left: -9999px;`:**
  - Moves element out of visible area.
- **`clip-path: polygon(0 0, 0 0, 0 0, 0 0);`:**
  - Clips element rendering, effectively hides.
- **`width: 0; height: 0; overflow: hidden;`:**
  - Reduces element size to zero, hides overflow.

### Import

> What Does `!important` Mean in CSS?

- **Definition:**
  - A CSS declaration used to give a style rule the highest precedence.
  - Overrides other styles, regardless of declaration order.
- **Usage:**
  - Enforces specific styles, even if other conflicting styles exist.
- **Example**

```css
p {
  color: red !important;
}

#thing {
  color: green;
}
```

## Unit

> How do you specify units in the CSS?.

- **Definition:**
  - Indicate the measurement for CSS properties, defining the size or length of elements.
- **Types of Units:**
  - **Pixels (`px`):**
    - Represents a fixed length, ensuring consistent sizing across different devices and screens.
    - Example: `width: 200px;`
  - **Percentages (`%`):**
    - Specifies a percentage of the parent element's size.
    - Example: `width: 50%;`
  - **Em (`em`):**
    - Relative to the font-size of the nearest parent element.
    - Example: `font-size: 1.2em;`
  - **Rem (`rem`):**
    - Relative to the font-size of the root element (`<html>`), ensuring consistent scaling.
    - Example: `margin: 2rem;`
  - **Viewport Width (`vw`) and Height (`vh`):**
    - Relative to the viewport's width and height, useful for responsive design.
    - Example: `width: 50vw;`
  - **Inch (`in`), Centimeter (`cm`), Millimeter (`mm`):**
    - Absolute length units based on physical measurements.
    - Example: `width: 2in;`

## Selector

### combinators

> What do the following CSS selectors mean?
> div, p | div p | div ~ p | div + p | div > p

- **`div, p`:**
  - Selects all `<div>` and `<p>` elements on the page.
- **`div p`:**
  - Selects all `<p>` elements that are descendants of a `<div>` element.
- **`div ~ p`:**
  - Selects all `<p>` elements that are siblings following a `<div>` element.
- **`div + p`:**
  - Selects the first `<p>` element that is immediately preceded by a `<div>` element.
- **`div > p`:**
  - Selects all `<p>` elements that are direct children of a `<div>` element.

### Different

> What are the different types of Selectors in CSS?

- **Element Selectors:**
  - **Def:** Selects HTML elements based on their name.
  - **e.g.:** `p { color: blue; }` targets all `<p>` elements and sets their text color to blue.
- **Class Selectors:**
  - **Def:** Selects elements with a specific class attribute.
  - **e.g.:** `.highlight { background-color: yellow; }` selects elements with class "highlight" and gives them a yellow background.
- **ID Selectors:**
  - **Def:** Selects a single element with a specific id attribute.
  - **e.g.:** `#main-content { font-size: 18px; }` targets the element with id "main-content" and sets its font size to 18 pixels.
- **Universal Selector:**
  - **Def:** Selects all elements on the page.
  - **e.g.:** `* { margin: 0; padding: 0; }` resets margins and paddings for all elements.
- **Descendant Selector:**
  - **Def:** Selects an element that is a descendant of another specific element.
  - **e.g.:** `div p { font-style: italic; }` targets `<p>` elements inside `<div>` elements and italicizes their text.
- **Child Selector:**
  - **Def:** Selects an element that is a direct child of another specific element.
  - **e.g.:** `ul > li { list-style-type: square; }` selects direct `<li>` children of `<ul>` and styles them with square bullets.
- **Attribute Selectors:**
  - **Def:** Selects elements based on their attribute values.
  - **e.g.:** `input[type="text"] { width: 200px; }` targets `<input>` elements with type "text" and sets their width to 200 pixels.
- **Pseudo-class Selectors:**
  - **Def:** Selects elements based on their state or position.
  - **e.g.:** `a:hover { color: red; }` changes the text color of `<a>` elements when hovered over.
- **Pseudo-element Selectors:**
  - **Def:** Selects specific parts of an element, like the first line or first letter.
  - **e.g.:** `p::first-line { font-weight: bold; }` makes the first line of `<p>` elements bold.

## Box Model

> What is the Box Mode in CSS ?

- **Definition:**
  - A fundamental concept that defines the layout and structure of elements on a web page.
- **Components:**
  - **Content:**
    - Actual content or text within the element, where the information is displayed.
  - **Padding:**
    - Clear space between the content and the element's border, providing internal spacing.
  - **Border:**
    - A line surrounding the padding (if any) and content, demarcating the element's edges.
  - **Margin:**
    - Clear space outside the border, creating separation between adjacent elements.
- **Calculation:**
  - **Total Element Width:**
    - Calculated as: `Width + Left Padding + Right Padding + Left Border + Right Border + Left Margin + Right Margin`
  - **Total Element Height:**
    - Calculated as: `Height + Top Padding + Bottom Padding + Top Border + Bottom Border + Top Margin + Bottom Margin`
- **Usage:**
  - Determines the space an element occupies on the web page, influencing its layout and positioning in relation to other elements.

### Border

### Content

### Different

> What is different between border-box and content-box ?

- **`Box-Sizing`:**
  - **`content-box`:**
    - The default box-sizing behavior in CSS.
  - **`border-box`:**
    - Alters the box-sizing behavior.
- **Calculation:**
  - **`content-box`:**
    - Width and height values include only the content area, excluding padding and border.
  - **`border-box`:**
    - Width and height values include content, padding, and border, providing a more intuitive sizing model.
- **Flexibility:**
  - **`content-box`:**
    - Offers precise control over content dimensions.
  - **`border-box`:**
    - Provides a more predictable and intuitive way to size elements, especially in complex layouts.
- **Use Cases:**
  - **`content-box`:**
    - Suitable for situations where precise control over content dimensions is crucial.
  - **`border-box`:**
    - Preferred in most cases, especially in responsive or dynamic layouts, for simplified and consistent sizing logic.

## Framework

### Bootstrap

> What is the Bootstrap ?

- **Definition:**
  - A popular front-end framework for building responsive and mobile-first websites and web applications.
- **Purpose:**
  - Facilitates rapid development by providing a set of pre-designed components, layouts, and CSS styles, ensuring consistency and responsiveness across different devices.
- **Pros:**
  - **Efficiency:**
    - Accelerates development with ready-made components and styles.
  - **Responsiveness:**
    - Ensures seamless user experience across various screen sizes and devices.
  - **Customizability:**
    - Allows customization to match specific design requirements.
  - **Community Support:**
    - Large community and extensive documentation for guidance and problem-solving.
- **Cons:**
  - **Learning Curve:**
    - Initial learning required to fully utilize the framework's features.
  - **Dependency:**
    - Projects may become dependent on Bootstrap's specific structure.
  - **File Size:**
    - Including all Bootstrap components can increase the overall file size.
- **Example:**
  - Creating a responsive navigation bar using Bootstrap classes:

```html
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Logo</a>
  <button
    class="navbar-toggler"
    type="button"
    data-toggle="collapse"
    data-target="#navbarNav"
    aria-controls="navbarNav"
    aria-expanded="false"
    aria-label="Toggle navigation"
  >
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarNav">
    <ul class="navbar-nav ml-auto">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">About</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Services</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Contact</a>
      </li>
    </ul>
  </div>
</nav>
```

### TailwindCss

> What is the Tailwind Css ?

- **Definition:**
  - A utility-first CSS framework that provides low-level utility classes to build custom designs without leaving your HTML file.
- **Purpose:**
  - Facilitates rapid UI development by streamlining the styling process through pre-defined classes.
- **Pros:**
  - Simplifies CSS development and speeds up prototyping.
  - Offers consistent and responsive designs with minimal effort.
  - Extensive customization options for tailoring the framework to specific project needs.
  - Supports dark mode out-of-the-box.
- **Cons:**
  - Learning curve for developers unfamiliar with utility-first approaches.
  - Larger file sizes due to the extensive use of utility classes.
- **Example:**
  - HTML using Tailwind CSS classes:
    ```html
    <div class="bg-blue-500 text-white p-4">This is a blue box with white text and padding.</div>
    ```

## Library

### Material UI

### Ant Design

## Preprocessor

### Definition

> What is the Css preprocessor ?

- **Definition**
  - **Scripting Language**
    - A CSS preprocessor is a scripting language
  - **Feature for Streamlined**
    - Enhances CSS by adding variables, functions for streamlined and more maintainable stylesheets.
- **Examples:**
  - Common CSS preprocessors include Sass, LESS, and Stylus

> Why use a CSS preprocessor?

- **Efficiency**
  - **Modular Code**
    - Enables modular and reusable CSS components.
  - **Advanced Features**
    - Provides advanced programming features not available in standard CSS.
- **Organization**
  - **Structured Styles**
    - Facilitates a structured and organized approach to writing styles.
- **Productivity**
  - **Code Reusability**
    - Allows reuse of code snippets, saving development time.
  - **Error Reduction**
    - Reduces errors through variables and functions, ensuring consistency.

### Type

#### SASS

> What is the SASS ?

- **Definition:**
  - A CSS preprocessor that extends standard CSS with variables, nesting, functions, and more.
- **Purpose:**
  - Improves code maintainability and reusability in CSS development.
- **Syntax:**
  - Uses indentation and nested rules instead of braces and semicolons in CSS.
- **Example**

```scss
$primary-color: #3498db;
body
  background-color: $primary-color;
```

#### SCSS

> What is the SCSS ?

- **Definition:**
  - Superset of CSS3, known as Sassy CSS, providing enhanced features and organization.
- **Purpose:**
  - Offers variables, nesting, and mixins, enhancing maintainability and reusability.
- **Syntax:**
  - Structured with indentation and curly braces, allowing clear hierarchies.
- **Example:**

```scss
$primary-color: #3498db;

.button {
  background-color: $primary-color;
  &:hover {
    background-color: darken($primary-color, 10%);
  }
}
```

#### LESS

> What is the LESS ?

- **Definition:**
  - CSS preprocessor scripting language.
- **Purpose:**
  - Enhances CSS with variables, functions, and dynamic behavior.
- **Syntax:**
  - Similar to CSS but with added features like variables and nesting.
- **Example:**
  -
  ```less
  @primary-color: #3498db;
  .button {
    color: @primary-color;
    &:hover {
      background-color: lighten(@primary-color, 10%);
    }
  }
  ```

### Different

> What is the difference between Sass and Scss ?

- **Syntax:**
  - **Sass:**
    - Uses indentation to define blocks and lacks semicolons and braces.
  - **SCSS:**
    - Adopts CSS-like syntax with semicolons and braces for defining blocks.
- **Readability:**
  - **Sass:**
    - Often considered more readable due to its concise syntax.
  - **SCSS:**
    - Closer to traditional CSS, making it more familiar and readable for developers transitioning from CSS.
- **Compatibility:**
  - **Sass:**
    - Requires strict indentation, which might cause issues for developers not accustomed to it.
  - **SCSS:**
    - Resembles CSS closely, making it easier to adopt for developers already familiar with CSS.
- **Usage:**
  - **Sass:**
    - Preferred by developers who appreciate its clean, indentation-based syntax.
  - **SCSS:**
    - Widely adopted, especially in larger projects, due to its CSS-like familiarity and ease of use.

> What is the difference between CSS variables and preprocessor variables?

- **Definition:**
  - **CSS**
    - Defined in CSS files using the `--variable-name` syntax.
  - **Preprocessor**
    - Defined in preprocessor files using `$variable-name` syntax.
- **Usage:**
  - **CSS**
    - Directly usable in CSS without requiring a preprocessor.
  - **Preprocessor**
    - Need a preprocessor (SASS, LESS, Stylus) to interpret and compile into CSS.
- **Cascade Behavior:**
  - **CSS**
    - Follow the cascade, allowing inheritance and overriding.
  - **Preprocessor**
    - Do not cascade; their scope is limited to where they are defined.
- **Accessibility:**
  - **CSS Variables:**
    - Accessible and manipulable via JavaScript.
  - **Preprocessor**
    - Not directly accessible or manipulable via JavaScript; limited to preprocessor functionality.

## Design

### Adaptive

### Responsive

### Different

> What are the differences between adaptive design and responsive design?

- **Approach:**
  - **Adaptive**
    - Offers fixed layouts for specific devices.
  - **Responsive**
    - Uses fluid grids and media queries for adaptable layouts.
- **Handling**
  - **Adaptive**
    - Server determines and delivers specific layouts based on device detection.
  - **Responsive**
    - Devices interpret CSS and adjust layouts locally, providing flexibility in client-side rendering.
- **Layout Structure:**
  - \*\*Adaptive
    - Predetermined layouts with fixed dimensions.
  - **Responsive**
    - Adaptable layouts using relative units.
- **Media Queries:**
  - \*\*Adaptive
    - Uses separate stylesheets or server-side detection.
  - **Responsive**
    - Employs CSS media queries for targeted styling.

> Is it important to test the webpage in different browsers?

Periodic Testing Necessity :

- **Initial Development and Major Changes:**
  - **Reason:**
    - Crucial to ensure the website's fundamental functionality and appearance across diverse browsers.
  - **Benefit:**
    - Identifies and resolves issues early, preventing widespread user dissatisfaction upon launch or major updates.
- **Ongoing Updates and Changes:**
  - **Reason:**
    - Browsers frequently update rendering engines, affecting how websites are displayed.
  - **Benefit:**
    - Regular testing maintains consistent user experience, adapting the site to evolving browser standards and user expectations.
- **Security and Performance Optimization:**
  - **Reason:**
    - Security vulnerabilities and performance optimizations can impact browser compatibility.
  - **Benefit:**
    - Regular testing ensures the website remains secure, responsive, and functional across varying browser versions.

## Flex Box

> What is the Flex Box ?

- **Definition:**
  - A layout model in CSS that allows design elements to distribute space and align content dynamically within a container, even when the size of the elements is unknown or dynamic.
- **Key Concepts:**
  - **Flex Container:**
    - The parent element containing the flex items.
    - Property: `display: flex;` or `display: inline-flex;` for inline-level flexibility.
  - **Flex Items:**
    - The child elements within the flex container.
    - Automatically adjust to fill the available space in the flex container.
  - **Main Axis and Cross Axis:**
    - **Main Axis:**
      - The primary axis along which flex items are placed.
      - Can be horizontal (default) or vertical, based on the flex direction.
    - **Cross Axis:**
      - Perpendicular to the main axis.
      - Aligns flex items when there's extra space in the container.

## Grid

> What is the Grid System ?

- **Definition:**
  - A layout technique in web design that organizes content into rows and columns.
- **Key Components:**
  - **Rows:**
    - Horizontal divisions in a grid layout.
    - Contain columns and provide structure to the layout.
  - **Columns:**
    - Vertical divisions in a grid layout.
    - Content elements are placed within columns to create the desired layout.
  - **Gutters:**
    - Spacing between columns and rows.
    - Adds separation between content elements for readability and aesthetics.
- **Usage:**
  - **Responsive Layouts:**
    - Adaptable to various screen sizes, ensuring consistency across devices.
  - **Alignment and Positioning:**
    - Facilitates precise alignment of elements.
    - Helps create balanced and visually appealing designs.
  - **Modular Design:**
    - Encourages a modular approach to content placement.
    - Allows for easy rearrangement of elements without disrupting the entire layout.

> What is different between Flex Box and Grid ?

- **Alignment:**
  - **Grid:**
    - Offers both horizontal and vertical alignment control.
  - **Flexbox:**
    - Primarily designed for one-dimensional layouts (either horizontal or vertical).
- **Complexity and Nesting:**
  - **Grid:**
    - Suitable for complex layouts and nested structures.
  - **Flexbox:**
    - Simpler for one-dimensional layouts, may require nested flex containers for complex structures.
- **Main Use Cases:**
  - **Grid:**
    - Ideal for overall page layout and alignment of multiple elements.
  - **Flexbox:**
    - Best suited for aligning items within a single row or column, such as navigation menus or lists.

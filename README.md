# CSS Study Guide for Complete Beginners

## Introduction

CSS stands for **Cascading Style Sheets**. While HTML creates the structure of a webpage (like building the walls and rooms of a house), CSS makes everything look nice (like painting the walls, choosing furniture, and decorating). Without CSS, websites would look very plain - just black text on a white background with blue links.

## What CSS Can Do

CSS can control:
- Colors (text color, background color)
- Sizes (how big text and images are)
- Spacing (margins and padding around elements)
- Fonts (what type of text to use)
- Layout (where things are positioned on the page)
- Animations (making things move)
- And much more!

## Three Ways to Add CSS to Your Webpage

There are three different ways to add CSS to your HTML. Let's look at each one:

### 1. Inline CSS

Inline CSS is added directly to HTML elements using the `style` attribute. It's like giving instructions to just one specific thing.

**Example:**
```html
<p style="color: blue; font-size: 18px;">This paragraph is blue and larger than normal text.</p>
```

In this example:
- We added CSS directly to a paragraph using the `style` attribute
- `color: blue;` makes the text blue
- `font-size: 18px;` makes the text 18 pixels tall
- Each style rule ends with a semicolon (;)

**Pros of inline CSS:**
- Easy to see what styles are applied to an element
- Good for quick testing or one-time styles

**Cons of inline CSS:**
- Has to be repeated for every element
- Makes HTML messy and hard to read
- Hard to maintain for larger websites

### 2. Internal CSS (Using `<style>` tag)

Internal CSS is added inside a `<style>` tag in the `<head>` section of your HTML document. It's like having a list of instructions that apply to the current page only.

**Example:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My Styled Page</title>
    <style>
        p {
            color: blue;
            font-size: 18px;
        }
        
        h1 {
            color: red;
            text-align: center;
        }
    </style>
</head>
<body>
    <h1>This is a Red Centered Heading</h1>
    <p>This paragraph is blue and larger than normal text.</p>
    <p>This paragraph is also blue and larger, without having to repeat the style!</p>
</body>
</html>
```

In this example:
- We added CSS inside a `<style>` tag in the `<head>` section
- `p { }` targets all paragraph elements on the page
- `h1 { }` targets all level 1 headings on the page
- Each style rule goes inside curly braces { }
- Each property and value is separated by a colon (:)
- Each declaration ends with a semicolon (;)

**Pros of internal CSS:**
- Styles apply to multiple elements without repeating code
- Keeps HTML cleaner than inline styles
- All styles are in one place

**Cons of internal CSS:**
- Only applies to one page (not good for multi-page websites)
- Still mixes HTML and CSS together

### 3. External CSS (Using a separate .css file)

External CSS is stored in a separate file with a .css extension and linked to your HTML document. It's like having a separate instruction manual that can be used for multiple pages.

**Step 1:** Create a file named `styles.css` with this content:
```css
p {
    color: blue;
    font-size: 18px;
}

h1 {
    color: red;
    text-align: center;
}

body {
    background-color: #f0f0f0;
    font-family: Arial, sans-serif;
}
```

**Step 2:** Link to the CSS file from your HTML file:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My Styled Page</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>This is a Red Centered Heading</h1>
    <p>This paragraph is blue and larger than normal text.</p>
    <p>This paragraph is also blue and larger, without having to repeat the style!</p>
</body>
</html>
```

In this example:
- We created a separate file for our CSS
- We linked to it using the `<link>` tag in the `<head>` section
- `rel="stylesheet"` tells the browser this link is to a stylesheet
- `href="styles.css"` tells the browser where to find the file

**Pros of external CSS:**
- One CSS file can be used for multiple HTML pages
- Complete separation of HTML (content) and CSS (style)
- Browsers can cache the CSS file so pages load faster
- Easiest to maintain for larger websites

**Cons of external CSS:**
- Requires managing multiple files
- An extra file for the browser to download

**Most professional websites use external CSS because it's easier to maintain and more efficient.**

## CSS Syntax

CSS has a simple structure:

```css
selector {
    property: value;
    another-property: another-value;
}
```

- **Selector:** Chooses which HTML elements to style
- **Property:** What aspect you want to change (like color, size, etc.)
- **Value:** How you want to change it (like blue, 18px, etc.)
- **Declaration:** A property and value together (like `color: blue;`)
- **Declaration block:** All the declarations inside the curly braces

## CSS Selectors

Selectors are how you choose which HTML elements to style. Here are the most common types:

### Element Selector

Targets all elements of a specific type.

```css
p {
    color: blue;
}
```

This will make **all** paragraphs blue.

### Class Selector

A class is like a name tag you can put on any HTML element. You can use the same class on multiple elements, and one element can have multiple classes.

**First, add a class to your HTML elements:**
```html
<p class="highlight">This paragraph has the highlight class.</p>
<p>This is a normal paragraph.</p>
<h2 class="highlight">This heading also has the highlight class.</h2>
```

**Then, style that class in your CSS:**
```css
.highlight {
    background-color: yellow;
    font-weight: bold;
}
```

In this example:
- The class name in HTML starts with `class="`
- The class selector in CSS starts with a dot (`.`)
- Only elements with the "highlight" class will get a yellow background and bold text

### ID Selector

An ID is like a unique name for one specific element. Each ID can only be used once per page.

**First, add an ID to your HTML element:**
```html
<h1 id="main-title">Welcome to My Website</h1>
```

**Then, style that ID in your CSS:**
```css
#main-title {
    color: purple;
    font-size: 36px;
    text-shadow: 2px 2px 4px #888888;
}
```

In this example:
- The ID in HTML starts with `id="`
- The ID selector in CSS starts with a hash/pound sign (`#`)
- Only the element with the "main-title" ID will get these styles

### Classes vs. IDs: When to Use Each

- **Use classes when:**
  - You want to style multiple elements the same way
  - You want to apply multiple styles to one element

- **Use IDs when:**
  - You need to target exactly one unique element
  - You need to link directly to a section of your page

**Example combining both:**
```html
<div id="header" class="dark-theme">
    <h1 class="title">My Website</h1>
    <p class="subtitle">Welcome to my first CSS website</p>
</div>
```

```css
#header {
    background-color: #333;
    padding: 20px;
}

.dark-theme {
    color: white;
}

.title {
    font-size: 32px;
}

.subtitle {
    font-style: italic;
}
```

In this example:
- Only one element can have `id="header"`
- Multiple elements can have `class="dark-theme"`
- Elements can have both IDs and classes

## Changing Fonts in CSS

Text is a big part of most websites, and changing fonts can make your website look much better. Here's how to work with fonts:

### Font Family

The `font-family` property sets what type of font to use. You can specify multiple fonts in case the user's computer doesn't have your first choice.

```css
body {
    font-family: Arial, Helvetica, sans-serif;
}
```

In this example:
- First, the browser will try to use Arial
- If Arial isn't available, it will try Helvetica
- If neither is available, it will use the default sans-serif font

### Common Font Types

There are 5 generic font families:
- `serif` - Fonts with small lines at the ends of characters (like Times New Roman)
- `sans-serif` - Fonts without those small lines (like Arial)
- `monospace` - Fonts where each character takes the same width (like Courier)
- `cursive` - Fonts that look like handwriting
- `fantasy` - Decorative fonts

### Web Safe Fonts

These fonts are commonly available on most computers:
- Arial
- Verdana
- Helvetica
- Tahoma
- Times New Roman
- Georgia
- Courier New
- Trebuchet MS

### Google Fonts (Web Fonts)

You can use many more fonts by linking to Google Fonts or other web font services. This lets you use fonts that might not be installed on the user's computer.

**Step 1:** Add a link to the Google Font in your HTML `<head>`:
```html
<link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">
```

**Step 2:** Use the font in your CSS:
```css
body {
    font-family: 'Roboto', sans-serif;
}
```

### Font Properties

You can change other aspects of fonts too:

```css
p {
    font-family: Georgia, serif;
    font-size: 18px;
    font-weight: bold;   /* normal, bold, 100-900 */
    font-style: italic;  /* normal, italic */
    line-height: 1.6;    /* space between lines */
    text-align: center;  /* left, right, center, justify */
    text-transform: capitalize; /* uppercase, lowercase, capitalize */
    text-decoration: underline; /* underline, overline, line-through */
    color: #0066cc;      /* text color */
}
```

## CSS Colors

There are several ways to specify colors in CSS:

### Named Colors

CSS has 140+ named colors like `red`, `blue`, `green`, `yellow`, etc.

```css
h1 {
    color: red;
    background-color: yellow;
}
```

### Hex Colors

Hex colors start with # followed by 6 characters (0-9 and A-F) representing RGB values.

```css
h1 {
    color: #FF0000;    /* red */
    background-color: #FFFF00;  /* yellow */
}
```

In hex colors:
- First 2 digits: Amount of red (00-FF)
- Middle 2 digits: Amount of green (00-FF)
- Last 2 digits: Amount of blue (00-FF)

### RGB Colors

RGB colors specify the amount of red, green, and blue (0-255).

```css
h1 {
    color: rgb(255, 0, 0);         /* red */
    background-color: rgb(255, 255, 0);  /* yellow */
}
```

### RGBA Colors

RGBA is like RGB but adds transparency (alpha) from 0.0 (fully transparent) to 1.0 (fully opaque).

```css
h1 {
    background-color: rgba(255, 0, 0, 0.5);  /* semi-transparent red */
}
```

## The Box Model

Every HTML element is a box with these layers (from inside to outside):

1. **Content** - The actual text, image, etc.
2. **Padding** - Space between the content and the border
3. **Border** - A line around the padding
4. **Margin** - Space outside the border, between this element and others

```css
div {
    /* Content size */
    width: 300px;
    height: 200px;
    
    /* Padding (inner space) */
    padding-top: 10px;
    padding-right: 20px;
    padding-bottom: 10px;
    padding-left: 20px;
    /* Or all at once: padding: 10px 20px 10px 20px; */
    
    /* Border */
    border-width: 2px;
    border-style: solid;
    border-color: black;
    /* Or all at once: border: 2px solid black; */
    
    /* Margin (outer space) */
    margin-top: 20px;
    margin-right: 10px;
    margin-bottom: 20px;
    margin-left: 10px;
    /* Or all at once: margin: 20px 10px 20px 10px; */
}
```

## Basic Layout with CSS

### Display Property

The `display` property controls how an element behaves in the layout.

```css
div {
    display: block;             /* Takes up full width */
}

span {
    display: inline;            /* Only takes space it needs */
}

nav a {
    display: inline-block;      /* Mix of inline and block */
}

.hidden {
    display: none;              /* Element is hidden completely */
}
```

### Common Layout Techniques

**Centering an element:**
```css
.center-me {
    width: 80%;                /* Must have a width */
    margin-left: auto;         /* Auto margins */
    margin-right: auto;        /* on left and right */
    /* Or just: margin: 0 auto; */
}
```

**Creating a simple navigation menu:**
```html
<nav>
    <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Contact</a></li>
    </ul>
</nav>
```

```css
nav {
    background-color: #333;
}

nav ul {
    list-style-type: none;  /* Removes bullet points */
    padding: 0;
    margin: 0;
}

nav li {
    display: inline-block;  /* Makes list items appear side by side */
}

nav a {
    display: block;
    color: white;
    text-decoration: none;  /* Removes underline from links */
    padding: 15px 20px;     /* Creates clickable area */
}

nav a:hover {
    background-color: #555; /* Changes background when mouse hovers */
}
```

## Complete Example

Here's a complete example putting everything together:

**HTML (index.html):**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Styled Website</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header id="main-header" class="dark-section">
        <h1>My First CSS Website</h1>
        <p class="subtitle">Learning how to style with CSS</p>
    </header>
    
    <nav>
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Services</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    </nav>
    
    <main>
        <section class="intro">
            <h2>Welcome to My Website</h2>
            <p>This is a paragraph with <span class="highlight">highlighted text</span> in the middle of it.</p>
            <p>I'm learning how to style websites with CSS!</p>
        </section>
        
        <section class="features dark-section">
            <h2>What I've Learned</h2>
            <div class="feature-box">
                <h3>HTML Structure</h3>
                <p>Creating the skeleton of webpages.</p>
            </div>
            <div class="feature-box">
                <h3>CSS Styling</h3>
                <p>Making websites look beautiful.</p>
            </div>
        </section>
    </main>
    
    <footer class="dark-section">
        <p>&copy; 2025 My First CSS Website</p>
    </footer>
</body>
</html>
```

**CSS (styles.css):**
```css
/* Basic reset to make things consistent */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Main styles */
body {
    font-family: 'Roboto', sans-serif;
    line-height: 1.6;
    color: #333;
    background-color: #f4f4f4;
}

/* Headings */
h1, h2, h3 {
    font-family: 'Playfair Display', serif;
    margin-bottom: 15px;
}

/* Layout containers */
header, nav, main, footer {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
}

/* Dark sections */
.dark-section {
    background-color: #333;
    color: white;
    padding: 20px;
}

/* Header specific styles */
#main-header {
    text-align: center;
    padding: 40px 20px;
}

.subtitle {
    font-style: italic;
    color: #ccc;
}

/* Navigation */
nav {
    background-color: #444;
    padding: 0;
}

nav ul {
    list-style-type: none;
    display: flex;
    justify-content: center;
}

nav li {
    margin: 0 5px;
}

nav a {
    display: block;
    color: white;
    text-decoration: none;
    padding: 15px 20px;
}

nav a:hover {
    background-color: #555;
}

/* Main content */
main {
    background-color: white;
    padding: 20px;
}

.intro {
    border-bottom: 1px solid #ddd;
    padding-bottom: 20px;
    margin-bottom: 20px;
}

.highlight {
    background-color: yellow;
    font-weight: bold;
    padding: 2px 5px;
}

/* Feature boxes */
.features {
    margin: 30px 0;
}

.feature-box {
    background-color: #444;
    border-radius: 5px;
    padding: 20px;
    margin-bottom: 20px;
}

.feature-box h3 {
    color: #ffcc00;
}

/* Footer */
footer {
    text-align: center;
    font-size: 14px;
    padding: 15px;
}
```

## Next Steps in Learning CSS

After you understand these basics, you can explore:

1. **Flexbox** - For more advanced layouts
2. **CSS Grid** - For complex grid-based layouts
3. **Responsive design** - Making websites look good on all devices
4. **Transitions and animations** - Adding movement to your website
5. **CSS frameworks** like Bootstrap - Pre-made CSS for faster development

## CSS Tips for Beginners

1. **Start simple** - Don't try to style everything at once
2. **Use a CSS reset** - Makes browsers display things more consistently
3. **Use meaningful class names** - Like `.main-navigation` instead of `.mn`
4. **Group related styles** - Keep all navigation styles together, etc.
5. **Add comments** - Use `/* Comment here */` to explain complex code
6. **Test in different browsers** - Chrome, Firefox, Edge, etc.
7. **Use browser developer tools** - Right-click and "Inspect" to see and test CSS live
8. **Be consistent** - Pick either kebab-case (like `main-title`) or camelCase (like `mainTitle`) for class names
9. **Use shorthand properties** when possible - Like `margin: 10px 20px;` instead of setting each side separately
10. **Learn from other websites** - Use browser dev tools to see how others style their sites

Remember, CSS takes practice! Don't worry if things don't look perfect right away. Keep experimenting and you'll improve quickly.

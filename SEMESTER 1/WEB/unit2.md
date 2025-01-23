# CSS Fundamentals - Unit 2 Notes

## **What are Cascading Style Sheets (CSS)?**
- **Definition**: Rules for controlling the look and feel of HTML documents.
  - Organized and efficient styling method.
  - Defined by the **W3C** (World Wide Web Consortium).
- **Structure**:
  - **Selector**: HTML element to style.
  - **Declaration**: Contains **property** and **value**.

### **Example**:
```css
p {
  color: blue;
  font-size: 20px;
}
```

---

## **Types of Stylesheets**
### 1. **Inline CSS**
- Applied directly to an HTML element via the `style` attribute.
  ```html
  <p style="color: red; margin-left: 20px;">This is a paragraph.</p>
  ```
### 2. **Internal CSS**
- Defined within a `<style>` tag in the `<head>` section.
  ```html
  <head>
    <style>
      body { background-color: lightblue; }
    </style>
  </head>
  ```
### 3. **External CSS**
- Linked using the `<link>` tag to a `.css` file.
  ```html
  <head>
    <link rel="stylesheet" type="text/css" href="styles.css">
  </head>
  ```

---

## **CSS Cascade and Specificity**
### Cascading Order
- **Priority levels** (highest to lowest):
  1. Inline styles.
  2. Internal styles (in `<style>` tags).
  3. External stylesheets.
  4. Browser default styles.
- **Example**:
  ```html
  <h1 style="color: red;">Inline style takes precedence.</h1>
  ```

### Selector Specificity
- **Ranking of selectors** (highest to lowest):
  1. **ID Selector** (`#id`).
  2. **Class Selector** (`.class`).
  3. **Element Selector** (`element`).

---

## **CSS Selectors**
### Types of Selectors
1. **Simple Selectors**:
   - **Element Selector**: Targets specific elements (e.g., `p`).
   - **ID Selector**: Targets a unique element (e.g., `#header`).
   - **Class Selector**: Targets multiple elements (e.g., `.container`).
2. **Combinator Selectors**:
   - **Descendant Selector**: Selects elements inside another element.
     ```css
     div p { color: green; }
     ```
   - **Child Selector**: Selects direct children only.
     ```css
     div > p { color: green; }
     ```
3. **Pseudo-Classes**:
   - Define states (e.g., `:hover`, `:focus`).
   - Example:
     ```css
     a:hover { color: red; }
     ```
4. **Pseudo-Elements**:
   - Style parts of an element (e.g., `::before`, `::after`).
   - Example:
     ```css
     p::first-line { font-weight: bold; }
     ```

---

## **CSS Properties**
### **Color and Text Properties**
- **color**: Sets text color.
  ```css
  h1 { color: blue; }
  ```
- **font-size**: Sets text size.
  ```css
  p { font-size: 16px; }
  ```
- **text-align**: Aligns text.
  ```css
  p { text-align: center; }
  ```
- **text-decoration**: Adds or removes text decorations (e.g., `underline`).
  ```css
  a { text-decoration: none; }
  ```

### **Background Properties**
- **background-color**: Sets background color.
- **background-image**: Adds a background image.
  ```css
  body {
    background-color: lightgray;
    background-image: url('bg.jpg');
  }
  ```

### **Box Model Properties**
1. **Padding**: Space inside an element.
2. **Margin**: Space outside an element.
3. **Border**: Defines element borders.
  ```css
  div {
    padding: 10px;
    margin: 20px;
    border: 2px solid black;
  }
  ```

---

## **Example HTML with CSS**
```html
<!DOCTYPE html>
<html>
  <head>
    <title>CSS Fundamentals Example</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        background-color: #f0f0f0;
      }

      header {
        background-color: #333;
        color: white;
        padding: 10px 20px;
      }

      .container {
        margin: 20px;
      }

      h1 {
        color: #007bff;
      }

      p {
        font-size: 16px;
        line-height: 1.5;
      }

      .highlight {
        color: red;
        font-weight: bold;
      }

      footer {
        background-color: #333;
        color: white;
        text-align: center;
        padding: 10px;
      }
    </style>
  </head>
  <body>
    <header>
      <h1>Welcome to CSS Fundamentals</h1>
    </header>

    <div class="container">
      <p>This is a basic example of how <span class="highlight">CSS</span> works with HTML.</p>
    </div>

    <footer>
      &copy; 2025 CSS Fundamentals
    </footer>
  </body>
</html>
```

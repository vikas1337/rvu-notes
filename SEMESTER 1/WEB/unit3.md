# CSS, Links, and Images - Unit 3 Notes

## **Styling Links with CSS**
- Links can be styled using any CSS property (e.g., color, font-family, background).
- **Link States**:
  1. `a:link` - Normal, unvisited link.
  2. `a:visited` - Link the user has visited.
  3. `a:hover` - Link when the user mouses over it.
  4. `a:active` - Link the moment it is clicked.

### Example:
```css
a {
  text-decoration: none;
}
a:hover {
  color: red;
}
```

---

## **Styling HTML Tables**
- Styles that can be applied:
  - Border
  - Background color
  - Alignment
  - Size
  - Padding
  - Layout
  - Hover effects

### Example:
```css
table {
  border: 1px solid black;
  border-collapse: collapse;
  width: 100%;
}
tr:hover {
  background-color: grey;
}
```

---

## **Styling HTML Forms**
- Styles applicable to input fields:
  - Width, Padding, Margin
  - Border, Border-radius
  - Box-shadow, Fonts
  - Colored or Focused inputs

### Example:
```css
input[type="text"] {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}
input[type="text"]:focus {
  border-color: blue;
}
```

---

## **CSS Box Model**
- Wraps around every HTML element:
  1. **Content**: Text/images inside the box.
  2. **Padding**: Clears area around content.
  3. **Border**: Surrounds padding and content.
  4. **Margin**: Clears area outside the border.

### Example:
```css
div {
  padding: 20px;
  border: 2px solid black;
  margin: 10px;
}
```

---

## **Styling Images**
- **Methods**:
  - Change size using `width` and `height`.
  - Add rounded corners with `border-radius`.
  - Center images using `margin: auto;` and `display: block;`.
  - Make images responsive with `max-width: 100%`.

### Example:
```css
img {
  max-width: 100%;
  height: auto;
  border-radius: 10px;
}
```

---

## **CSS Layouts and Positioning**
### Floating Elements
- **Float Property**:
  - Floats elements to the left or right.
  - Text flows around floated elements.

### Positioning Methods
1. **Static**: Default positioning.
2. **Relative**: Positioned relative to normal position.
3. **Absolute**: Positioned relative to the nearest positioned ancestor.
4. **Fixed**: Positioned relative to the viewport.
5. **Sticky**: Toggles between relative and fixed based on scroll position.

### Example:
```css
div {
  position: absolute;
  top: 50px;
  left: 100px;
}
```

---

## **CSS Dropdown Menu**
- HTML Structure:
  ```html
  <div class="dropdown">
    <button>Menu</button>
    <div class="dropdown-content">
      <a href="#">Link 1</a>
      <a href="#">Link 2</a>
    </div>
  </div>
  ```
- CSS:
  ```css
  .dropdown {
    position: relative;
    display: inline-block;
  }
  .dropdown-content {
    display: none;
    position: absolute;
    background-color: white;
    box-shadow: 0px 8px 16px rgba(0, 0, 0, 0.2);
  }
  .dropdown:hover .dropdown-content {
    display: block;
  }
  ```

---

## **CSS Units**
1. **Absolute Units**:
   - `px` (pixels): Fixed-size unit.
2. **Relative Units**:
   - `%`: Relative to parent element.
   - `em`: Relative to the font size of the parent.
   - `rem`: Relative to the root element’s font size.

### Example:
```css
div {
  width: 50%;
  font-size: 1.5rem;
}
```

---

## **Example: CSS-Enhanced Web Page**
```html
<!DOCTYPE html>
<html>
  <head>
    <title>CSS Links and Images</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        margin: 0;
        padding: 0;
      }

      header {
        background-color: #4CAF50;
        color: white;
        padding: 15px;
        text-align: center;
      }

      nav a {
        margin: 0 15px;
        text-decoration: none;
        color: white;
      }

      nav a:hover {
        text-decoration: underline;
      }

      img {
        max-width: 100%;
        border-radius: 10px;
      }

      table {
        width: 100%;
        border-collapse: collapse;
      }

      th, td {
        padding: 10px;
        text-align: left;
        border: 1px solid #ddd;
      }

      footer {
        text-align: center;
        padding: 10px;
        background-color: #4CAF50;
        color: white;
        position: fixed;
        width: 100%;
        bottom: 0;
      }
    </style>
  </head>
  <body>
    <header>
      <h1>Welcome to CSS Styling</h1>
      <nav>
        <a href="#links">Links</a>
        <a href="#tables">Tables</a>
        <a href="#images">Images</a>
      </nav>
    </header>

    <section id="links">
      <h2>Styling Links</h2>
      <p><a href="#">This is a styled link</a>.</p>
    </section>

    <section id="tables">
      <h2>Styling Tables</h2>
      <table>
        <tr>
          <th>Name</th>
          <th>Age</th>
        </tr>
        <tr>
          <td>John Doe</td>
          <td>30</td>
        </tr>
      </table>
    </section>

    <section id="images">
      <h2>Styling Images</h2>
      <img src="example.jpg" alt="Example image">
    </section>

    <footer>
      &copy; 2025 CSS Styling
    </footer>
  </body>
</html>
```

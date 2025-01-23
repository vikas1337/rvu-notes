# JavaScript: Functions, DOM, Forms, and Event Handlers

## Introduction to JavaScript
JavaScript is a high-level, interpreted programming language used primarily for building interactive and dynamic web pages. It is widely used for client-side scripting, enabling developers to create features that respond to user actions without reloading the page.

### Common Applications:
- Client-side validation
- Dynamic drop-down menus
- Displaying date and time
- Pop-up windows and dialog boxes
- Interactive clocks

### Example: Displaying Current Date
```html
<!DOCTYPE html>
<html>
<body>
  <p id="date"></p>
  <script>
    document.getElementById("date").innerHTML = new Date();
  </script>
</body>
</html>
```

---

## JavaScript Basics
### Variables and Data Types
JavaScript variables are defined using `var`, `let`, or `const`.

#### Example:
```javascript
var name = "John"; // String
typeof name; // "string"
let age = 25;       // Number
typeof age; // "number"
const isStudent = true; // Boolean
typeof isStudent; // "boolean"
```

### Operators
#### Arithmetic Operators:
`+`, `-`, `*`, `/`, `%`

#### Comparison:
`==` (type conversion), `===` (strict comparison)

#### Example:
```javascript
let x = "5";
let y = 5;
console.log(x == y);  // true
console.log(x === y); // false
```

---

## Control Structures
### If-Else and Conditional Operators
Control structures guide the flow of a program.

#### Example:
```javascript
let score = 85;
if (score > 90) {
  console.log("Excellent");
} else if (score > 70) {
  console.log("Good");
} else {
  console.log("Needs Improvement");
}
```

---

## Functions
Functions encapsulate reusable code. They can be named or anonymous.

#### Example:
```javascript
function greet(name) {
  return `Hello, ${name}!`;
}
console.log(greet("Alice"));
```

#### Scope Example:
```javascript
var x = 10;
function testScope() {
  var x = 20;
  console.log(x); // 20
}
testScope();
console.log(x); // 10
```

---

## Document Object Model (DOM)
JavaScript can manipulate HTML and CSS dynamically using the DOM.

### Accessing Elements
#### By ID:
```javascript
document.getElementById("example").innerHTML = "Updated Content";
```
#### By Class:
```javascript
var elements = document.getElementsByClassName("example");
elements[0].style.color = "blue";
```

#### Example: Change Text
```html
<!DOCTYPE html>
<html>
<body>
  <h1 id="title">Original Text</h1>
  <button onclick="changeText()">Click Me</button>
  <script>
    function changeText() {
      document.getElementById("title").innerHTML = "Text Changed!";
    }
  </script>
</body>
</html>
```

---

## Event Handling
Events allow interactivity in web pages.

### Inline Event Example:
```html
<button onclick="alert('Button clicked!')">Click Me</button>
```

### Event Listener Example:
```javascript
const button = document.getElementById("myButton");
button.addEventListener("click", () => {
  alert("Event Listener Triggered!");
});
```

---

## Form Validation
JavaScript can validate form inputs before submission.

#### Example: Validate Email
```html
<!DOCTYPE html>
<html>
<body>
  <form onsubmit="return validateForm()">
    Email: <input type="text" id="email">
    <button type="submit">Submit</button>
  </form>
  <script>
    function validateForm() {
      const email = document.getElementById("email").value;
      const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      if (!regex.test(email)) {
        alert("Invalid email address!");
        return false;
      }
      return true;
    }
  </script>
</body>
</html>
```

---

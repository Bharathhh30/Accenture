# Accenture Recruitment Exam: HTML, CSS & JavaScript MCQs

This document contains a complete list of Multiple Choice Questions (MCQs) covering HTML, CSS, and JavaScript as asked in Accenture recruitment exams, complete with questions, code snippets, options, correct answers, and detailed explanations.

---

## **Section 1: JavaScript Questions**

### **Question 1: Definition of JavaScript**
Which of the following statements best describes JavaScript?

* **A)** JavaScript is a scripting language used to make web pages interactive.
* **B)** JavaScript is a compiled programming language used exclusively for operating systems.
* **C)** JavaScript is a markup language used to structure web pages.
* **D)** JavaScript is a database query language.

**Correct Answer:** **Option A**

**Explanation:**  
JavaScript is a single-threaded, lightweight, dynamic scripting language designed primarily for web browsers to manipulate the Document Object Model (DOM), handle dynamic user interactions, and execute logic on the client (and server) side.

---

### **Question 2: JavaScript Closures**
Which statement best defines a **Closure** in JavaScript?

* **A)** A private variable inside a loop structure.
* **B)** A function bundled together with references to its surrounding lexical environment.
* **C)** A method that closes the browser window automatically.
* **D)** A syntax error caused by unclosed curly braces.

**Correct Answer:** **Option B**

**Explanation:**  
A closure is formed when an inner function retains access to its outer (enclosing) function's scope (lexical environment) even after the outer function has finished executing and returned.

---

### **Question 3: DOM Manipulation Output**
What will be the output rendered in the HTML paragraph tag?

```html
<p id="demo"></p>

<script>
  var txt1 = "Accenture";
  var txt2 = "JavaScript MCQs";
  document.getElementById("demo").innerHTML = txt1 + " " + txt2;
</script>
```

* **A)** `AccentureJavaScript MCQs`
* **B)** `Accenture JavaScript MCQs`
* **C)** `undefined undefined`
* **D)** `Error: innerHTML is read-only`

**Correct Answer:** **Option B**

**Explanation:**  
`document.getElementById("demo")` selects the DOM element with `id="demo"`. The string concatenation `txt1 + " " + txt2` evaluates to `"Accenture JavaScript MCQs"`, which is assigned to the `innerHTML` property of the element.

---

### **Question 4: Loose Equality Operator (`==`)**
What will be logged to the console?

```javascript
let a = 2;
let b = 2.0;
console.log(a == b);
```

* **A)** `true`
* **B)** `false`
* **C)** `TypeError`
* **D)** `undefined`

**Correct Answer:** **Option A**

**Explanation:**  
In JavaScript, all numbers are double-precision 64-bit binary format IEEE 754 values (type `Number`). Since `2` and `2.0` represent the exact same numeric value, `2 == 2.0` evaluates to `true`.

---

### **Question 5: Strict Equality Operator (`===`)**
What will be logged to the console?

```javascript
let num = 2;
console.log(num === "2");
```

* **A)** `true`
* **B)** `false`
* **C)** `NaN`
* **D)** `SyntaxError`

**Correct Answer:** **Option B**

**Explanation:**  
The strict equality operator (`===`) checks both **value** and **data type** without implicit type coercion. Since `num` is of type `Number` and `"2"` is of type `String`, `num === "2"` evaluates to `false`.

---

### **Question 6: `undefined` vs `null`**
What will be printed by the following code?

```javascript
let a = 1;
if (a != null) {
    console.log(1);
}
```

* **A)** `null`
* **B)** `undefined`
* **C)** `1`
* **D)** No output

**Correct Answer:** **Option C**

**Explanation:**  
* `undefined` means a variable has been declared but not assigned a value.
* `null` is an explicit assignment value representing "no value".
Since `a = 1`, the condition `a != null` evaluates to `true`, and `1` is logged to the console.

---

### **Question 7: Global Entry Object**
Which object serves as the main entry point to client-side JavaScript host environment APIs?

* **A)** `document`
* **B)** `window`
* **C)** `location`
* **D)** `navigator`

**Correct Answer:** **Option B**

**Explanation:**  
The `window` object represents the browser window containing the DOM document. It is the global object in client-side JavaScript, and all global variables, functions, and browser APIs (`document`, `localStorage`, `fetch`, `setTimeout`) belong to it.

---

### **Question 8: Execution Invocation**
How do you execute reusable code blocks in JavaScript?

* **A)** Functions and Methods
* **B)** Comments and Variables
* **C)** Tags and Selectors
* **D)** Selectors and Attributes

**Correct Answer:** **Option A**

**Explanation:**  
Functions and methods enclose statements that perform tasks or compute values and execute when called/invoked.

---

## **Section 2: HTML Questions**

### **Question 9: HTML Purpose**
What does HTML stand for and what is its purpose?

* **A)** HyperText Markup Language, used to structure content on web pages.
* **B)** HighTech Markup Language, used to styling web elements.
* **C)** Hyperlink Text Management Language, used to store database tables.
* **D)** All of the mentioned.

**Correct Answer:** **Option D**

**Explanation:**  
HTML (HyperText Markup Language) provides the fundamental structural blueprint for web pages using markup tags.

---

### **Question 10: Creator of HTML**
Who created the HTML specification?

* **A)** Brendan Eich
* **B)** Tim Berners-Lee
* **C)** James Gosling
* **D)** Dennis Ritchie

**Correct Answer:** **Option B**

**Explanation:**  
Tim Berners-Lee invented HTML and established the World Wide Web in 1989.

---

### **Question 11: HTML5 Doctype Declaration**
Which tag represents the correct HTML5 document type declaration?

* **A)** `<!DOCTYPE html>`
* **B)** `<DOCTYPE html5>`
* **C)** `<?xml version="1.0"?>`
* **D)** `<html doctype="standard">`

**Correct Answer:** **Option A**

**Explanation:**  
`<!DOCTYPE html>` is the case-insensitive HTML5 declaration that tells web browsers to render the page in standards mode.

---

### **Question 12: Heading Elements**
Which HTML tag defines the largest heading level?

* **A)** `<heading>`
* **B)** `<h6>`
* **C)** `<h1>`
* **D)** `<head>`

**Correct Answer:** **Option C**

**Explanation:**  
HTML hierarchy ranges from `<h1>` (most significant/largest heading) to `<h6>` (least significant/smallest heading).

---

### **Question 13: What is DOM?**
What is the full form and function of the DOM in web development?

* **A)** Direct Object Mode
* **B)** Document Object Method
* **C)** Dynamic Object Management
* **D)** Document Object Model: A standard programming API interface that represents HTML documents as nodes and objects.

**Correct Answer:** **Option D**

**Explanation:**  
The DOM (Document Object Model) models an HTML document as a logical tree structure, enabling scripts like JavaScript to access, modify, and delete content, structure, and styles dynamically.

---

### **Question 14: Document Metadata Tag**
Where is metadata (such as character set, viewport, page title, and stylesheets) stored in an HTML document?

* **A)** Inside the `<body>` element
* **B)** Inside the `<head>` element
* **C)** Inside the `<footer>` element
* **D)** Inside the `<section>` element

**Correct Answer:** **Option B**

**Explanation:**  
The `<head>` section contains document metadata that is not directly displayed in the main viewport area, such as `<meta>`, `<title>`, `<link>`, and `<script>`.

---

### **Question 15: Text Highlighting in HTML5**
Which HTML5 element is used to highlight text with default styling?

* **A)** `<mark>`
* **B)** `<highlight>`
* **C)** `<b>`
* **D)** `<yellow>`

**Correct Answer:** **Option A**

**Explanation:**  
The `<mark>` tag highlights text by applying a default yellow background color to indicate relevance or reference.

---

## **Section 3: CSS Questions**

### **Question 16: Internal Stylesheet Tag**
Which tag embeds internal CSS styling directly inside an HTML file?

* **A)** `<css>`
* **B)** `<script>`
* **C)** `<style>`
* **D)** `<link>`

**Correct Answer:** **Option C**

**Explanation:**  
Internal CSS is written inside `<style>...</style>` tags, placed within the `<head>` block of the HTML document.

---

### **Question 17: Class Selector**
Which selector applies CSS styles to multiple elements on a web page?

* **A)** ID Selector (`#`)
* **B)** Class Selector (`.`)
* **C)** Attribute Selector
* **D)** Universal Selector (`*`)

**Correct Answer:** **Option B**

**Explanation:**  
Classes can be assigned to multiple elements across an HTML document, allowing shared style rules to be applied via the `.` syntax (e.g., `.button-style`).

---

### **Question 18: ID Selector**
Which selector targets a single unique element on a web page?

* **A)** Class Selector
* **B)** Tag Selector
* **C)** ID Selector (`#`)
* **D)** Pseudo-class Selector

**Correct Answer:** **Option C**

**Explanation:**  
In HTML, an `id` must be unique within a document. The ID selector targets that single element using the `#` prefix (e.g., `#main-header`).

---

### **Question 19: Bold Text in CSS**
Which CSS property is used to set the font weight to bold?

* **A)** `font-style: bold;`
* **B)** `text-weight: bold;`
* **C)** `font-weight: bold;`
* **D)** `text-transform: bold;`

**Correct Answer:** **Option C**

**Explanation:**  
The `font-weight` property sets how thick or thin characters in text are displayed (e.g., `normal`, `bold`, `bolder`, or numerical weights like `400`, `700`).

---

### **Question 20: Missing Semicolon Parsing in CSS**
Consider the following CSS snippet with a missing semicolon on line 2:

```css
h1 {
    color: red
    text-decoration: underline;
    font-style: italic;
}
```

What styling rule(s) will be applied to the `h1` element?

* **A)** All styles (`color: red`, `text-decoration: underline`, and `font-style: italic`) will be applied.
* **B)** None of the styles will be applied.
* **C)** Only `font-style: italic` will be applied.
* **D)** `color: red` and `text-decoration: underline` will be applied.

**Correct Answer:** **Option C**

**Explanation:**  
CSS parsers use semicolons to separate property declarations. Because the semicolon after `red` is missing, the parser reads `color: red text-decoration: underline;` as a single declaration. Since `red text-decoration: underline` is an invalid value for `color`, the entire property rule is discarded. The parser recovers at the next semicolon, successfully applying `font-style: italic;`.
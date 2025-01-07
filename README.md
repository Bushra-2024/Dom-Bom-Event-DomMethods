# Dom-Bom-Event-DomMethods

![image](https://github.com/user-attachments/assets/449e6603-158c-427d-acc5-ef7c98e7ed9f)


## BOM (Browser Object Model) in JavaScript


The ***BOM (Browser Object Model)*** allows JavaScript to interact with the browser. It provides objects to manage the browser window, perform actions like navigation, alerts, and manage the URL.


![image](https://github.com/user-attachments/assets/4c2719af-1c08-43f6-88bb-05affdda6f80)


### Key Components of BOM:

- `window`: Represents the browser window and acts as the global object.
- `document`: Part of the BOM, used to access and manipulate the webpage content (DOM).
- `navigator`: Provides information about the browser.
- `screen`: Gives details about the user's screen.
- `location`: Handles the current URL.
- `history`: Lets you navigate through the browser history.
- `alert()`: Displays a simple pop-up message to the user.

### Example of `alert()` in BOM:

```javascript
// Simple alert example
alert("Hello, welcome to the page!");
```


##  DOM (Document Object Model) in JavaScript

The DOM (Document Object Model) is a way for your browser to **represent a webpage** so that programming languages like JavaScript can interact with it. It’s essentially a structured version of your HTML that JavaScript can read and modify.

Think of it as a **tree structure**:


![image](https://github.com/user-attachments/assets/4da278ec-0a9a-4721-9ded-a28439904584)



### Explanation:
1. **Root Node**:
   - The `<html>` tag is the root of the tree.

2. **Branches**:
   - `<head>` and `<body>` are the first-level branches from `<html>`.
   - Inside `<head>`, there’s a `<title>` tag.
   - Inside `<body>`, there are:
     - `<h1>` (heading)
     - Two `<p>` (paragraphs)
     - `<img>` (an image element).

3. **Leaves**:
   - The text content ("DOM Tutorial", "This is a heading", etc.) are the leaves.
   - Attributes like `src="smiley.gif"` and `alt="Smiley face"` are properties of the `<img>` element.


With the DOM, you can do things like:
- Change content: Replace the text in a `<p>` tag.
- Change styles: Add or modify CSS properties.
- Add or remove elements: Dynamically create new buttons, images, etc.
- Handle events: Respond to clicks, keyboard presses, or mouse movements.

For example:

If your HTML looks like this:
```html
<!DOCTYPE html>
<html>
  <body>
    <p id="example">Hello, world!</p>
  </body>
</html>
```

Using JavaScript and the DOM, you can interact with the `<p>` element:
```javascript
// Select the element using querySelector
const paragraph = document.querySelector('#example');

// Change its text
paragraph.textContent = 'Hello, DOM with querySelector!';

```

### What is `querySelector`?

`querySelector` is a method that allows you to select an element using **CSS selectors**. It is very flexible and can target elements based on:
- **IDs** (use `#` like `#example`)
- **Classes** (use `.` like `.example-class`)
- **Tag names** (use just the tag name like `p`, `div`)
- **Attributes** (use `[attribute]` like `[type="text"]`)

### Why use `querySelector`?

- **Flexible**: Unlike `getElementById`, which only works for IDs, `querySelector` can find elements by ID, class, tag, or any combination of CSS selectors.
- **Consistent**: It uses the same syntax as CSS, which makes it easy if you’re already familiar with styling.
- **Modern**: It’s widely used in modern JavaScript for its versatility.

### More Info:
1. **First Match**: `querySelector` will return **only the first matching element** in the DOM. If there are multiple elements that match the selector, it picks the first one.
2. **For Multiple Matches**: If you want to select **all matching elements**, use `querySelectorAll`.


### Example with Multiple Selectors:
Let’s say your HTML looks like this:
```html
<!DOCTYPE html>
<html>
  <body>
    <p class="example">First Paragraph</p>
    <p class="example">Second Paragraph</p>
  </body>
</html>
```

Using `querySelector`:
```javascript
const firstParagraph = document.querySelector('.example');
firstParagraph.textContent = 'Only the first paragraph is selected!';
```

Using `querySelectorAll` to target all:
```javascript
const allParagraphs = document.querySelectorAll('.example');
allParagraphs.forEach((p, index) => {
  p.textContent = `Paragraph ${index + 1} updated!`;
});
```

### Dom Features
The **Document Object Model (DOM)** represents every HTML tag as an object. These objects include the tags themselves (like `<div>`, `<p>`, etc.), their **children** (subtags), and the **text** inside the tags.

You can manipulate these objects using JavaScript to modify the webpage.

### Key Methods and Properties:
1. **`querySelector()`**: Returns the first element that matches a specified CSS selector.
   - Example: `document.querySelector('p')` selects the first `<p>` element.

2. **`querySelectorAll()`**: Returns all elements that match the specified CSS selector.
   - Example: `document.querySelectorAll('p')` selects all `<p>` elements.

### Key Properties:
1. **`innerHTML`**: Allows you to get or set the content inside an HTML element. It can completely replace the content of an element.
   - Example:
    ``` javascript
    <div id="example">Old Content</div>
    <script>
    document.getElementById('example').innerHTML = 'New Content';
    </script>
   ```

2. **`style` Object**: Represents the CSS styles applied to an element. You can use it to modify individual style properties.
     - Example:
    ``` javascript
    <p id="text">This is a text</p>
   <script>
   document.getElementById('text').style.color = 'blue';  // Changes text color to blue
   document.getElementById('text').style.fontSize = '20px';  // Changes font size to 20px
   </script>
   ```

Both `innerHTML` and `style` allow you to dynamically modify an element's content and appearance.

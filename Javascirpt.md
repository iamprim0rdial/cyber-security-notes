# Introduction
- JavaScript is a programming language used to create dynamic content for websites. It can be used for both client-side and server-side scripting.
- JavaScript on the client side is directly executed in the user's browser. Almost all browsers have JavaScript Interpreter and do not need to install any software. There is also a browser console where you    can test your JavaScript code.
- JavaScript is also used on the Server side (on Web Servers) to access databases, file handling and security features to send responses, to browsers.
---

## Variables and Datatypes in JavaScript
- **Variables :** A variable is like a container that store data which can be reused later in the program. In JavaScript, variables are declared using following keywords
  **`1. var`**:  `var` is function-scoped or globally-scoped (if declared outside a function).
- **Example**:
    
    ```jsx
    var x = 10;
    x = 20; // This is allowed
    console.log(x); // 20
    
    ```

  **`2. let`**: `let` is block-scoped (limited to the block in which it is defined, like inside loops or conditionals).
- **Example**:
    
    ```jsx
    let x = 10;
    x = 20; // This is allowed
    console.log(x); // 20
    
    ```   

 **`3. const`**: `const` is also block-scoped (like `let`). But you **cannot reassign** a `const` variable. Once a value is assigned, it cannot be changed.
- **Example**:
    
    ```jsx
    const x = 10;
    x = 20; // This will throw an error:
    
    ```
 ### Datatypes
 **JavaScript has 8 Datatypes**  
- String
- Number
- Bigint
- Boolean
- Undefined
- Null
- Symbol
- Object
  
**The Object Datatype**  
The object data type can contain both built-in objects, and user defined objects:
Built-in object types can be: objects, arrays, dates, maps, sets, intarrays, floatarrays, promises, and more. 

```jsx
// Numbers:
let length = 16;
let weight = 7.5;

// Strings:
let color = "Yellow";
let lastName = "Johnson";

// Booleans
let x = true;
let y = false;

// Object:
const person = {firstName:"John", lastName:"Doe"};

// Array object:
const cars = ["Saab", "Volvo", "BMW"];

// Date object:
const date = new Date("2022-03-25");

```


---

## Function 
Functions are reusable blocks of code designed to perform specific tasks. They allow you to organize, reuse, and modularize code. Modularizer code means breaking down a large codelines into smaller, manageable, and reusable units or "modules.  

**syntax**

```jsx
function function_name(para1, para2, para3, ...) {
// your_code_here
}
```
**The code inside the function will execute when "something" invokes (calls) the function:**    
   - When an event occurs (when a user clicks a button or any error)
   - When it is invoked (called) from JavaScript code
   - Automatically (self invoked)


**Example to change html object with help of innerHTML:**

```jsx
<html>
<body>
<h1>Hello World</h1>
<h3 id="Testing"></h3>

<script> // js block start from here
function myfoo() // declare function with name foo() {
document.getElementById("Testing").innerHTML="I have learned";
}
// JavaScript HTML methods getElementById(). It "finds" an HTML element (with id="testing"), and changes the element content (innerHTML) to "I have learned"
</script>
<img src=you.jpeg onerror=myfoo()>
</body>
</html>
```

**Note:** Learn about **[JavaScript Events](https://www.w3schools.com/js/js_events.asp)** and than **[HTML DOM Events](https://www.w3schools.com/jsref/dom_obj_event.asp)**


## Reference and Idea ...  
**[Javascript course](https://www.w3schools.com/js/)**

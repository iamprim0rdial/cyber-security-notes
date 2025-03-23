# Introduction
- JavaScript is a programming language used to create dynamic content for websites. It can be used for both client-side and server-side scripting.
- JavaScript on the client side is directly executed in the user's browser. Almost all browsers have JavaScript Interpreter and do not need to install any software. There is also a browser console where you    can test your JavaScript code.
- JavaScript is also used on the Server side (on Web Servers) to access databases, file handling and security features to send responses, to browsers.
---

## Variables and Datatypes in JavaScript
- **Variables :** A variable is like a container that store data which can be reused later in the program. In JavaScript, variables are declared using following keywords
### 1. **`var`**:

- **Scope**: `var` is function-scoped or globally-scoped (if declared outside a function).
- **Example**:
    
    ```jsx
    var x = 10;
    x = 20; // This is allowed
    console.log(x); // 20
    
    ```
    

### 2. **`let`**:

- **Scope**: `let` is block-scoped (limited to the block in which it is defined, like inside loops or conditionals).
- **Example**:
    
    ```jsx
    let x = 10;
    x = 20; // This is allowed
    console.log(x); // 20
    
    ```
    

### 3. **`const`**:

- **Scope**: `const` is also block-scoped (like `let`). You **cannot reassign** a `const` variable. Once a value is assigned, it cannot be changed.
- **Example**:
    
    ```jsx
    const x = 10;
    x = 20; // This will throw an error:
    
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


## Reference and Idea ...  
**[Javascript course](https://www.w3schools.com/js/)**

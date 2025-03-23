# Introduction
- JavaScript is a programming language used to create dynamic content for websites. It can be used for both client-side and server-side scripting.
- JavaScript on the client side is directly executed in the user's browser. Almost all browsers have JavaScript Interpreter and do not need to install any software. There is also a browser console where you    can test your JavaScript code.
- JavaScript is also used on the Server side (on Web Servers) to access databases, file handling and security features to send responses, to browsers.

---
## Function  
**syntax**
```javascript
<script>
function function_name() {
#your_code_here
}
</script>
```
**Example to change html object with help of innerHTML:**
```javascript
<html>
<body>
<h1>Hello World</h1>
<h3 id="dom-testing"></h3>
<script>
function myfoo() {
document.getElementById("dom-testing").innerHTML="I have learned";
}
</script>
<img src=you.jpeg onerror=myfoo()>
</body>
</html>
```

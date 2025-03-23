JavaScript is a programming language used to create dynamic content for websites. It can be used for both client-side and server-side scripting.

## function:
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

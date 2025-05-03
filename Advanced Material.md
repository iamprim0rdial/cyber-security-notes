## Obfuscation is a technique that makes code or data more difficult to understand or analyze. It's often used by malware writers to evade detection. 
### Here are some obfuscation methods:

- **Control flow obfuscation:** This technique modifies the control flow of a program to make it harder to understand how each function works. For example, control flow flattening replaces the normal control flow with a state machine.
- **Arithmetic obfuscation:** This technique replaces arithmetic calculations with mathematical equivalents that are harder to understand.
- **Debug obfuscation:** This technique removes or masks redundant debug details from code.
- **Data obfuscation:** This technique modifies sensitive data to make it less valuable to unauthorized intruders. Techniques include encryption, tokenization, or masking.
- **Layout obfuscation:** This technique rearranges operations in software to make it difficult to follow the software's flow.
- **Code transposition:** This technique transforms code while maintaining its practicality, making it difficult to reverse engineer.
- **Runtime polymorphism:** This technique changes the appearance of malware in run-time to avoid detection.

**Example of obfuscation in python**
```bash
1. Python introspection and bytecode manipulation

2. Construct a payload using Python bytecode (with `types.CodeType`) or use marshaled code.

3. base64-encoded serialized function or manipulate `func.__code__` attributes directly.

4. generate a lambda function that imports and runs arbitrary code

5. encoding or dynamic construction to bypass restrictions

6. marshalled or serialized bytecode object

getattr(builtins, eval)("import(os).system(id)")
```
---

**Serialization:**  
Serialization is the process of converting an object (like a function) into a format that can be stored or transmitted. Different programming languages have their own serialization mechanisms.
Let's say you have a Python function

```
def my_function()
```

. You might:

1. **Serialize:** Convert `my_function` into a Python pickle file. 
2. **Base64 Encode:** Convert the pickle file data into a Base64-encoded string. 
3. **Store/Transmit:** Store the Base64 string, send it over a network, or embed it in a JSON object. 
4. **Decode/Deserialize:** When you need to use the function again, you would: 
    ◦ Base64 decode the string to get the original pickle data. 
    ◦ Deserialize the pickle data to recreate the `my_function`.

1. 1. **Serialize:** Convert `my_function` into a Python pickle file.
2. 2. **Base64 Encode:** Convert the pickle file data into a Base64-encoded string.
3. 3. **Store/Transmit:** Store the Base64 string, send it over a network, or embed it in a JSON object.
4. 4. **Decode/Deserialize:** When you need to use the function again, you would:
    - ◦ Base64 decode the string to get the original pickle data.
    - ◦ Deserialize the pickle data to recreate the `my_function`

---

## Web application firewall
Knowing the application firewall behind the web is very crucial thing to know . because WAF (Web application firewall ) block some of your request if it is not meet the policies . WAF work on set of rules known as policies . If you know the firewall behind your testing web application your are going to save your time .

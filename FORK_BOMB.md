# Fork bomb 
```bash

:(){ :|:& };:

```

- **`()`** defines a function.
- **`{ :|:& };`** is the body of the function:
    - **`:`** is the function calling itself (recursively).
    - `|` pipes the output of one instance to another (creating a chain of processes).
    - `&` causes the processes to run in the background.
- **`;:`** ends the function definition and then calls the function.

### what is fork:  

**FORK** refers to a system call that creates a new process (a child process) which is an exact copy of the calling process (the parent process). This allows for parallel execution and can be used for tasks like running multiple instances of a program or handling concurrent client requests. 

### What it does:

When executed in a Unix-like shell (such as Bash), this code continuously spawns new processes. Each process calls the function again, creating a massive number of processes very quickly. This causes the system to run out of resources, making it slow or unresponsive, and potentially requiring a reboot to fix.

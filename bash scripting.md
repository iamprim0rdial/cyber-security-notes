# Bash Scripting
Bash scripting is very useful for automate the everyday task in Linux. It has little bit complex syntax. It start with a shebang.   
Wait what is Shebang 😲 ?  
lemme tell you 😌, Some Blah Blah stuff! Shebang is a combination of bash # and bang ! followed by the bash shell path. This is the first line of the script. Shebang tells the shell to execute it via bash shell. 

**#!/bin/bash** <-- shebang line

Every script name end with **.sh** extension, example: **filename.sh** . it is considered as good practice to write a simple name of script according to the work. **Note:** Don’t forget to give executable permission to user simply by typing chmod u+x filename.sh

to execute the script we will use this command  ./filename.sh . let's do postmortem dot forward-slash your-filename 

--- 

## Bash Scripting Keywords:

1. **`echo`**
    - **Usage**: Displays a message or value to the screen.
    - **Example**: `echo "Hello, World!"`
    - **Explanation**: `echo` is used to print the output to the terminal.
2. **`read`**
    - **Usage**: Accepts input from the user and stores it in a variable.
    - **Example**: `read name`
    - **Explanation**: `read` takes input from the user and assigns it to the variable `name`.
3. **`$`**
    - **Usage**: Used to access the value of a variable or argument.
    - **Example**: `echo $HOME`
    - **Explanation**: `$` is used to replace a variable with its value, such as `$1` for the first argument passed to the script.
4. **`$1`, `$2`, ..., `$n`**
    - **Usage**: Positional parameters used to refer to the arguments passed to a script.
    - **Example**: `echo $1`
    - **Explanation**: `$1` refers to the first argument passed to the script or function, `$2` to the second, and so on.
5. **`$@`**
    - **Usage**: Refers to all arguments passed to the script or function.
    - **Example**: `echo $@`
    - **Explanation**: `$@` expands to all arguments as individual words.
6. **`$#`**
    - **Usage**: Represents the number of arguments passed to the script.
    - **Example**: `echo "Number of arguments: $#"`
    - **Explanation**: `$#` gives the count of arguments provided to the script.
7. **`$?`**
    - **Usage**: Returns the exit status of the last executed command.
    - **Example**: `echo $?`
    - **Explanation**: `$?` is used to retrieve the exit status of the last command. A value of `0` means success, while any other value indicates an error.
8. **`$()`**
    - **Usage**: Used for command substitution, where the output of a command is captured and used as part of a variable or expression.
    - **Example**: `var=$(ls)`
    - **Explanation**: `$()` captures the output of the command `ls` and stores it in the variable `var`.
9. **`declare`**
    - **Usage**: Used to define variables and assign specific attributes (like types) to them.
    - **Example**: `declare -i num=5`
    - **Explanation**: `declare` can be used to declare an integer variable (`i`), ensuring only integer values are assigned.
10. **`export`**
- **Usage**: Used to make a variable available to child processes or other scripts.
- **Example**: `export VAR=value`
- **Explanation**: `export` makes a variable (like `VAR`) available to subshells and scripts launched from the current shell.

## If-else 

**if else is use when we have some specific condition to apply on**

```bash
if [ condition ]; then 

echo “Display message”

elif [ condition ]; then 

echo “Display message”

else

echo “Display message”

fi

```

**condition could be like:**  

```bash

if (${1,,} = “vishal”) then 

echo “Hello $1” ;;

else

echo “Sorry I don’t know!  bye” ;;

```

## Case-statement 

Case - statement is use to run code according to their input .

case expression in 

 pattern)

code 1 to be executed if pattern match

;;

pattern)

code 2 to be executed if pattern match 

;;

*)

code 3 run if none of the pattern match the expression 

;;

esac

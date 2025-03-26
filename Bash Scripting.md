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
5. **`$?`**
    - **Usage**: Returns the exit status of the last executed command.
    - **Example**: `echo $?`
    - **Explanation**: `$?` is used to retrieve the exit status of the last command. A value of `0` means success, while any other value indicates an error.
6. **`$()`**
    - **Usage**: Used for command substitution, where the output of a command is captured and used as part of a variable or expression.
    - **Example**: `var=$(ls)`
    - **Explanation**: `$()` captures the output of the command `ls` and stores it in the variable `var`.
7. **`declare`**
    - **Usage**: Used to define variables and assign specific attributes (like types) to them.
    - **Example**: `declare -i num=5`
    - **Explanation**: `declare` can be used to declare an integer variable (`i`), ensuring only integer values are assigned.
8. **`export`**
- **Usage**: Used to make a variable available to child processes or other scripts.
- **Example**: `export VAR=value`
- **Explanation**: `export` makes a variable (like `VAR`) available to subshells and scripts launched from the current shell.

## Basic shell script:

![Nano tutorial](https://github.com/user-attachments/assets/3c93e882-9156-46fb-81f2-8e374aa8f1f2)



---

## If-else statement 

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

---

## Case-statement 

**Case - statement is use to run code according to their input.**

```bash

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

```

**example:**

```bash
#!/bin/bash

# Prompt the user for input
echo "Enter a number (1-3):"
read number

# Case statement to match different patterns
case $number in
    1)
        echo "You entered one."
        ;;
    2)
        echo "You entered two."
        ;;
    3)
        echo "You entered three."
        ;;
    *)
        echo "Invalid input. Please enter a number between 1 and 3."
        ;;
esac

```
# Case statement:

![case_statment](https://github.com/user-attachments/assets/f60de030-9a40-4ebe-a686-ce71c3a6576e)

---

## for-loop
1. **Basic `for` loop (Iterating over a sequence of numbers)**
```bash
for (( i=1; i<=5; i++ ))
do
echo "Iteration number: $i"
done
```

2. **for loop with a list of items**
```bash
for item in apple banana cherry
do
echo "I like $item"
done
```

3.`for` **loop with a range using** `{start..end}`

```bash
for i in {1..5}
do
echo "Number: $i"
done
```

4. **`for` loop with `seq` command**
```bash
for i in $(seq 1 5)
do
echo "Counting: $i"
done
```
---

## Conditional

### Conditions
Note that `[[` is actually a command/program that returns either `0` (true) or `1` (false). Any program that obeys the same logic (like all base utils, such as `grep(1)` or `ping(1)`) can be used as condition, see examples.

| `[[ -z STRING ]]` | Empty string |
|               --- |          --- |
| `[[ -n STRING ]]` | Not empty string |
| `[[ STRING == STRING ]]` | Equal |
| `[[ STRING != STRING ]]` | Not Equal |
| `[[ NUM -eq NUM ]]` | Equal |
| `[[ NUM -ne NUM ]]` | Not equal |
| `[[ NUM -lt NUM ]]` | Less than |
| `[[ NUM -le NUM ]]` | Less than or equal |
| `[[ NUM -gt NUM ]]` | Greater than |
| `[[ NUM -ge NUM ]]` | Greater than or equal |
| `[[ STRING =~ STRING ]]` | Regexp |
| `(( NUM < NUM ))`   | Numeric conditions |
| `[[ X && Y ]]` | And |


### File Conditions

|`[[ -e FILE ]]` | Exists |
| --- | --- |
|`[[ -r FILE ]]` | Readable |
| `[[ -h FILE ]]` | Symlink |
| `[[ -d FILE ]]` | Directory |
| `[[ -w FILE ]]` | Writable |
| `[[ -s FILE ]]` | Size is > 0 bytes |
| `[[ -f FILE ]]` | File |
| `[[ -x FILE ]]` | Executable |
| `[[ FILE1 -nt FILE2 ]]` | 1 is more recent than 2 |
| `[[ FILE1 -ot FILE2 ]]` | 2 is more recent than 1 |
| `[[ FILE1 -ef FILE2 ]]` | Same files |


---

## Functions

```bash
function_name () {
    # code to be executed
}
```

**example:**

```bash
#!/bin/bash

# Define the function
greet() {
    echo "Hello, $1!"  # $1 is the first argument passed to the function
}

# Call the function
greet "Vishal"
greet "Trevor"
```

# Bash Scripting
Bash scripting is very useful for automate the everyday task in Linux. It has little bit complex syntax. It start with a shebang.   
Wait what is Shebang 😲 ?  
lemme tell you 😌, Some Blah Blah stuff! Shebang is a combination of bash # and bang ! followed by the bash shell path. This is the first line of the script. Shebang tells the shell to execute it via bash shell. 

**#!/bin/bash** <-- shebang line

Every script name end with **.sh** extension, example: **filename.sh** . it is considered as good practice to write a simple name of script according to the work. **Note:** Don’t forget to give executable permission to user simply by typing chmod u+x filename.sh

to execute the script we will use this command  ./filename.sh . let's do postmortem dot forward-slash your-filename 


## Keywords  
- **echo** keyword is use to display the message   
- **read** keyword is use to read data/input from user 
- **$** It is a replacement variable . It is use to replace the current variable with argument  for example $1 replace with first argument given with shell call ****  
- **Array:** array is sequence of same data type so for example : ARRAY_NUM = (1 2 3 4 5) or ARRAY_STR = (ONE TWO THREE FOUR) ... etc. to access the array we use for loop: **for value in $ARRAY_VAR_NAME;**
- **for value in $ARRAY_NUM;** —> This line will fetch the value in ARRAY_NUM variable one by one  then assign in into value variable   ,
- **do echo $value —>**  This line will take value from above value variable and display the values/element . 
- **done —>**  Don’t forget to use this keyword in the end else the program will not gonna work .This keyword will tell the shell that ok! this line of code is done here you can print the output .

**Note:** User can also print the length of string or number of character in value by simply add one line which is |—

- **do echo -n $value —>** This Line of will print the array without newline and space like ONETWOTHREEFOUR 
- **wc -c; done  —>**  wc means word count . -c is flag to extend the output and done .


### If-else — Bash Scripting

if else is use when we have some specific condition to apply on 

if [ condition ]; then 

echo “Display message”

elif [ condition ]; then 

echo “Display message”

else

echo “Display message”

fi

condition could be like - 

if (${1,,} = “vishal”) then 

echo “Hello $1” ;;

else

echo “Sorry I don’t know!  bye” ;;

### Case-statement — Bash Scripting

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

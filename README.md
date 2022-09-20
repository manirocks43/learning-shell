# learning-shell
 ### List of Shell scripting topics

1. Shebang & Comments    (Scripting and Concepts)
2. Print                 (Command)
3. Redirectors & Quotes  (Linex Concept)
4. Variables             (Scripting and Concepts) 
5. Functions             (Scripting and Concepts)
6. Exit Status           (Command)
7. Conditions            (Scripting and Concepts)
8. Loops                 (Scripting and Concepts)
9. SED Editor            (Command)


1. Shebang:
best method is <shell> <script>.
# is used for comments
If you want to print something we use "echo command".
echo Hello world

2. Redirectors
   (>,<) >Stdout) (<Stdin)
> redirect output to select locatiom
< redirect input to your desired script (Ex: mongo < catalogue.js)
> output is over ridden, using(>> append) the output content in desired location.
>, 1> only output, 2> for error andd &> for both output and error.
Ex: ls -ld /boot/ /boot1/ 1>/tmp/out 2>/tmp/err

3. Exit Status
0 = Successful
1-255 = Not successful
$? holds the exit status value, so use echo $?

4. Variables (Constants):
If we assign a name to a certain set of data, then its called a variable.
In bash shell we declare Variables as Var=Data
In bash shell we access variable as $VAR or ${VAR}
VAR=$(command), this is a command substitution,cmd output will go to VAR.
Example:DATE=$(date)  ;  Output: DATE=$(date)
VAR=$((expression)), this is a arithematic susbtitution, expression output will go to variable.
Example: VAR=$((2+3))  ; Value of 2+3 is $VAR

5. Inputs[(During execution: Least used); (Before Execution: Frequently used)]
   During execution: 
read -p 'Enter Name: ' name 
echo Your name- $name
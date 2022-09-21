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

## Print colours:
Syntax: echo -e "\e[COLmMESSAGE\e[0m"
# EXAMPLE: echo -e "\e[31mHELLO\e[om"
# \e[31m -> To enable colour code 31
# \e[0m -> To disable the enabled colour code we use 0
# -e -> Enable escape sequence, \e is one escape sequence
# "" -> Quotes are mandatory if we use escape sequence
## Colours and their codes:
1. Red  -> 31
2. Green -> 32
3. Yellow -> 33
4. Blue -> 34
5. Maganta -> 35
6. Cyan -> 36


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

## Special variables.sh??
echo $0 - Script name
echo $1 - 1st argument
echo $2 - 2nd argument
echo $@ - All arguments
echo $* - All arguments
echo $# - Number of Arguments

6. SED Editor (Stream line editor)
a. Delete line
b. Substitute a word
c. Add a line
## SED works in 2 ways:
1. sed will not change the file and print change in the terminal, this is default SED behaviour.
2. By using -i, we can edit the file rather than just printing.
## Delete lines Examples:
sed -i '/root/ d' /tmp/passwd
sed -i -e '/root/ d' /tmp/passwd
sed -i -e '/root/ d' -e '/nologin/ d' /tmp/passwd
sed -i -e '1 d' /tmp/passwd
## Substitute lines Examples:
   sed -e 's/root/ROOT/' /tmp/passwd
   sed -i -e 's/root/ROOT/' /tmp/passwd
   sed -i -e 's/root/ROOT/gi' /tmp/passwd
## Add lines Examples:
sed -e '1 i Hello' /tmp/passwd
sed -i -e '1 i Hello' /tmp/passwd (inside)
sed -i -e '1 a Hello' /tmp/passwd (append)
sed -i -e '1 c Hello' /tmp/passwd (change)
sed -i -e '/shutdown/ c Hello' /tmp/passwd

## Conditions (case and if{majorly used}):
1. Simple IF:
if [expression]
then 
   command
fi

2.If else:
if [expression]
then 
   command
else 
   command
fi

3. Else if:
if [expression]
then 
   command1
elif [expression2]
then
   command2
elif [expression3]
then 
   command3
else 
   command4
fi

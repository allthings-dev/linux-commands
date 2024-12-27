# Bash Shell Scripting

## Overview
* Reference: https://www.freecodecamp.org/news/bash-scripting-tutorial-linux-shell-script-and-command-line-for-beginners/#heading-bash-scripting-basics


## Shebang
* It specified which interpreter will be used to run teh script
* This is the first line of any script like #!/bin/bash
```
#!/bin/bash

```

## Make script executable
```
chmod 700 abc.sh
```

## Comments in script
* Comments start with a hash (#)
```
# This is an example comment
# Both of these lines will be ignored by the interpreter
```

## Variables and data types
* There are no data types in Bash and can store strings, integers, or real numbers
* In Bash, a variable is capable of storing numeric values, individual characters, or strings of characters.

### Assign the value directly
* Notice that doubel quotes are required if value contains space or special characters
* There should not be any space between variable name, equal sign, and the value assigned. 
```
car=sedan
greeting="good morning"
```
* Assign the value based on the output obtained from a program or command, using command substitution
* Note that $ is required to access an existing variable's value
```
another_car=$car
```

### Access value of a variable
* To access the variable value, append $ to the variable name
```
echo $car
or,
echo ${car}
or,
echo "${car}"
```
* This works even inside double quotes. Interpolation does not work is single quotes.
```
echo "Hello, $car"
```
### Length of a value of a variable
* Length of teh value in a variable can be found using: ${#car}
```
car=bugati
car_length=${#car}
```

## String maniplulation
* ${string:position}  --> returns a substring starting from $position till end. The first index is 0
* ${string:position:length} --> returns a substring of $length characters starting from $position.
```
car=mercedes
echo ${car:0} // this prints mercedes
echo ${car:1} // this prints ercedes

echo ${car:0:2} // this prints me
```
* To cehck if a string has a substring, you can use either == or =~.
* In case of ==, space in teh subsctring has to be enclosed in bracket
```
string='My long string'
if [[ $string == *"My long"* ]]; then
  echo "It's there!"
fi
```
* Alternatively, use =~ like below
```
string='My string';

if [[ $string =~ " str" ]]; then
   echo "It's there!"
fi
```

# Split a string and iterate over elements
* This uses IFS which is Internal Field Separator
```
#/bin/bash

IFS=':'
arr=($PATH)
unset IFS

for dirx in ${arr[@]}; do
	echo $dirx
done

```

## Numerical operations
* There are 2 syntax for this. One uses brackets and anotehr uses teh legacy utility "expr"
* Type 1. Note that theer should be no spaces in between dollar and the brackets. Spaces in actual experssion is fine
```
echo $((2+3))
c=$((2+3))
c=$(( 2 - 3 ))
c=$((2*3))
c=$((2/3)) // this will return just quotient
```
* Type 2. Note that asterisk had to be escaped else file/folder names were substituted
```
expr 3 + 4
expr 3 - 4
expr 3 \* 4
expr 4 / 3
c=$(expr 2 + 6)
c=`expr 2 + 6`
```

## Array
* Values of different types or the same type can be stored in an array
* You can get full array using ${my_data[@]}
* You can get element at a specific index using ${my_data[0]}. Note that index starts from 0
* The lebgth of the array can be got using ${#my_data[@]}
* Length of any element can eb found using ${#my_data[1]}
```
my_data=(Learning "Bash variables" from GFG)
arr=("value1" value2 $value3)
arr2([0]="Baeldung" [1]="is" [2]="cool")
arr3[0]="Baeldung"
arr3[1]="is"
arr3[2]="cool"


echo $my_data

echo length of array is ${#my_data[@]}
echo array is ${my_data[@]}
echo elem1 is ${my_data[0]}
echo elem2 is ${my_data[1]}
echo elem2 length is ${#my_data[1]}

```

## Map or Associative Array
* To create map, the "declare" keyword hs to be sued. Note that "declare" can also be be used for normal numeric, string, arrays variabels aslo, but is usuallu omitted
```
declare -A map1=(["one"]="bash" ["two"]="is" ["three"]="cool")
echo values are ${map1[@]}
echo keys are ${!map1[@]}
echo map length is ${#map1[@]}
for key in ${!map1[@]}; do echo $key:${map1[$key]}; done
```

## Read user input
* The command for this is "read"
```
#!/bin/bash

echo -n "What's your name: "
read yourname
echo "Hello $yourname"


What's your name: Saturn
Hello Saturn
```

## Read a file line by line
```
while read line
do
  echo $line
done < data/poem.txt
```

## Arguments in a script or function
* In a bash script or function, $1 denotes the initial argument passed, $2 denotes the second argument passed, and so forth.

## if-else
* Supports if, if-else, if-elif-else, and nested conditionals
* Supports logical operators such as AND -a and OR -o
* Note that the space between text and opening/closing square brackets is mandatory, else a syntax error occurs
```
echo "Please enter a number: "
read num

if [ $num -gt 10 ]; then
  echo "$num is greater than 10"
elif [ $num -gt 0 -a $num -lt 10 ]; then
  echo "$num is a small positive num"
else
  echo "$num is negative"
fi
```
* Example of equals and not equals
```
if [ $a == $b ] 
then 
    echo "a is equal to b"
fi 
  
#Check whether they are not equal 
if [ $a != $b ] 
then 
    echo "a is not equal to b"
fi 
```
* Check if a variable is unset or set to empty variab;e
```
if [ -z "${VAR}" ];
```
* Check if a variable has non-null/non-zero string value
```
if [ -n "$1" ]
```

## Looping - while
* Example 1
```
i=1
while [[ $i -le 10 ]] ; do
   echo "$i"
  (( i += 1 ))
done
```
* Example 2: Infinite loop with sleeping
```
count=0
while true
do
  count=$(( count + 1))
  echo $count.“Hi, I am infinity loop”
  sleep 1
done
```

## Looping - for
* Example 1
```
for i in {1..5}
do
    echo $i
done
```
* Example 2. break/continue sattement is supported
```
for a in 1 2 3 4 5 6 7 8 9 10
do

    # if a is equal to 5 break the loop
    if [ $a == 5 ]
    then
        break
    fi

    # Print the value
    echo “Iteration no $a”
done
```
* Example 3: This will print red, green and blue in 3 separate lines
```
COLORS=”red green blue”

# the for loop continues until it reads all the values from the COLORS  

for COLOR in $COLORS
do
    echo “COLOR: $COLOR”
done
```
* Example 4: using start, end and increment
```
for i in {0..10..2}
do
  echo "Welcome $i times"
done
```
* Example 5: 3-parameter loop
```
for (( c=1; c<=5; c++ ))
do 
   echo "Welcome $c times"
done
```
* Example 6: loop over command output
```
for OUTPUT in $(Linux-Or-Unix-Command-Here)
do
    command1 on $OUTPUT
    command2 on $OUTPUT
    commandN
done
```
  
## Debugging
* set the set -x option at the beginning of the script
* This option enables debugging mode, which causes Bash to print each command that it executes to the terminal, preceded by a + sign
```
#!/bin/bash

set -x
```

## Exit Code
* When Bash encounters an error, it sets an exit code that indicates the nature of the error
* You can check the exit code of the most recent command using the $? variable
* A value of 0 indicates success, while any other value indicates an error
```
if [ $? -ne 0 ]; then
    echo "Error occurred."
fi
```

## Special variables
```
$0 : Displays the filename of the current script
$1-$11 : Store data of the first 11 argument names
$? : Displays the exit status code for the latest executed command
$! : Shows the ID of the last background job (didn't work)
$$ : 	Displays the process ID of the current shell
$@ : Stores arguments as an array
$* : Groups all given arguments by connecting them together
$# : Show the number of arguments supplied in a given script
```

## Exporting variables
* Exporting variables in bash allows users to use such variables between different child shell instances
```
export greeting="good morning"
hello=world
export hello
bash
exho $hello
```

## Command substitution or Variable substitution
* This allows assigning the output of a particular command to a variable. 
* This can be done in 2 ways as shown below
```
timestamp=$(date +%s)
echo $timestamp

files=`ls`
echo $files
```

## Functions in script
* Basic structure of a function
```
function_name(){
    // body of the function
}
```
* Functions can return a value to the caller which teh caller accesses using the status special variable $?
* The functions that terminate the shell entirely using the ‘exit’ keyword.


## Progress Bar in shell
* Over-writing of curernt is done by using the "\r" char
* To run it, source teh file and then execute "progress-bar 100"
```
progress-bar() {
  local duration=${1}


    already_done() { for ((done=0; done<$elapsed; done++)); do printf "▇"; done }
    remaining() { for ((remain=$elapsed; remain<$duration; remain++)); do printf " "; done }
    percentage() { printf "| %s%%" $(( (($elapsed)*100)/($duration)*100/100 )); }
    clean_line() { printf "\r"; }

  for (( elapsed=1; elapsed<=$duration; elapsed++ )); do
      already_done; remaining; percentage
      sleep 1
      clean_line
  done
  clean_line
}

```







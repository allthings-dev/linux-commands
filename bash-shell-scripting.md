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
* There are no data types in Bash.
* In Bash, a variable is capable of storing numeric values, individual characters, or strings of characters.

### Assign the value directly
* 
```
car=sedan
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
```
* 














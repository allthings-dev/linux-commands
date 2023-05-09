# vi

### vi is basic editor. vim is VI iMproved 

### vi has 2 modes
* By default, one lands up in comamnd mode
* To enter insert mode, press i
* To exit insert mode, press Esc key

### Save the file when in command mode using
* :w

### Quit the file when in command mode using
* :q

### Save and quit the file when in command mode using
* :wq

### Quit the file without saving when in command mode using
* :q!



### Open an existing file 
* vi [existing file name]

### Craete a new file 
* vi [new file name]
and now save with :wq


### Line editing
* Delete the line or delete 3 lines starting from current line
```
dd
3dd
```

* Copy current line or 3 lines starting from current line
```
yy
3yy
```

* Paste
```
P (uppercase): Paste before your cursor
p (lowercase): Paste after your cursor
```


### Search file and find more occurences

* Searh a file using / or ?
```
/pattern - this searches forwards
?pattern - this searches backwards
Starting with ‘def’: /^def
Ending with ‘return': /return$
```

* Go to next or previous occurence
```
n: next 
N: previous 
```
* To make search case insensitive
```
:set ignorecase
```



### Show and hide line numbers
```
:set number or set nu will show or turn on line numbers
:set nonumber or set nonu will hide the line numbers
```


### Page up and down
```
ctrl + b to move a page screen back or “up”
ctrl + f to move a page screen front or “down”
```

### Go to specific line
* First line :0
* Last line Shift + g
* Specific line :n

### Character delete, cut, copy and paste
* x key - to delete the character under the cursor. 
* v key - to start copy or cut
* Move your cursor to select text, and then press y to copy the selected text or x to cut it. 
* Position your cursor at the desired location and press the p key to paste the text you copied or cut.

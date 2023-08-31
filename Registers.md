### General
Source: https://www.brianstorti.com/vim-registers/
- Registers are spaces in memory which vim uses to store some text
- Each of these spaces have a identifier, so it can be accessed later. 
- It’s no different than when you copy some text to your clipboard, except you usually have just one clipboard to copy to, while `vim` allows you to have multiple places to store different texts.


### Accessing Registers
- You can copy to a register by hitting `"<reg-letter>` before a command that copies or deletes
- **Normal Paste**: You can paste from a register by hitting `"<reg-letter>`  before `p` or `P`
- **Insert Paste/Command Paster**: You can paste from a register in insert mode or command mode using `Ctrl + r` followed by register letter


### View Registers
- You can view all registers using `:reg`
- You can view particular registers using `:reg a b c`

### Unnamed Register
- The unnamed or default register is `""` , it contains any text that is yanked or deleted by default
- The regular paste `p` is the same as `""p`

### Numbered Registers
- Even if you only use the default register you don't have to worry about losing the previous value saved in the register when you do say delete
- VIM automatically populates the numbered registers from `"0` to `"9` 
- `"0` contains the latest content , `"1` the yank before that, and so on
- `"9` is the oldest, after which it will be expelled


### Small Delete Register
- This register contains text from commands that delete less than one line, except when the command specifies a register with "x.
```
"-
```
### Read-Only Registers
- There are four read-only registers
```
". "% ": "#
```
- The last inserted text is stored in `".`
- The current file path is in `"%` starting from the directory where VIM was opened
- `"+` register is the clipboard register
	- On a windows system there is no difference between `"*` and `"+` but there is on a Unix system
 - `":` register stores the most recently executed command
	- A neat way to use this is to re-run a command just by doing `@:`
- `"#` is the name of the alternate file, which you can think of as last edited file
	- Read `:h alternate-file` for more
	- It's what VIM uses when you use `Ctrl-^`

### Expression Register
- The expression register `"=` is used to deal with result of expressions
- In insert mode if you type `Ctrl+r` followed by `=` you'll see a `=` sign in the command line
	- If you then type `2 + 2`  you'll get 4 printed 
	- If you type `system('ls')` then the output of `ls` would be printed

### Search Register
- The search register is where the  latest text that you searched with `/`, `?`, `*`, `#` are stored
- Say you searched for "Nietzsche" and want to now replace every occurrence of it, don't type the name again instead do this
```
:%s/<ctrl-r />/mustache/g
```

### Black Hole Register
- Used when we want to delete, yank, change without changing any register including the default register
- Represented by 
```
"_
```
- 
### Macros
- To read more about macros go to `:h recording`
- Macros are also recorded into a registers as text, you can fix an error in a macro by just editing the text in the register
- For example to append a semicolon the the end of a macro use
	- `:let @w ='i;'`, the capital letter means append, you're entering insert mode `i` and entering the `;`
- To edit something in the middle of a register use
	- `:let @w='<Ctrl-r w>'`
- No need to record a macro 10 times before you get it right
- 
### Writing to A Register
- `let` keyword is used to write to a register
- Example to copy the current file to system clipboard you can run `:let @+=@%` 

### Using Registers For Computation
- You can if you’re clever enough use registers to do math
- Say you created a table with two columns and the third column is to be the product of the first two
- You can use a macro to repeat the operation explained below
- Put the number in the first col in register a
- The second number in register b
- Go to the third column go to insert mode hit `<Ctrl-R> =` to open up the expression register
	- Type `<Ctrl-R> a` to get value from first col
	- Type the operation `*`
	- Type `<Ctrl-R> b` to get value from second col
	- Hit enter
- Repeat this for all and voila! You populate the entire table
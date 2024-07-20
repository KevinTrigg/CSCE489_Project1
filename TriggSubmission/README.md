# AFIT-CSCE489-PROJ1 Trigg

myshell is a simple shell built for linux that can take input in order to:

### create a file

### append to a file

### list the contents of a file to console

### print the current directory to console



# available functions, brackets signify user input:

## create [file name]
* make a new file in the shells directory with the input name
* checks for existance of file before creation to prevent duplicates 
#### filename is a string of characters representing the name of the file created

## update [file name] [number of times text will be written] "[text block]"  [&]
* append a block of text to the end of the referenced file a specified amount of times
* the & symbol is added to the end of the command to run it in the background and allow user input for the next command immediately. While many of the other functions implement some version of this capability it should only be used with the update command.
  #### filename is a string of characters representing the name of the file created
  #### number of times text will be written is an integer counting the number of lines that will be appended to the file
  #### text block is a string inclusive of white space that will be appended
  #### & is a character flag that can be added to the end of the command to make it run in the background

## list [file name]
* print the contents of the selected file to the console
 #### filename is a string of characters representing the name of the file created

## dir
* print out the contents of the current directory

## halt
* exit the shell and kill all processes associated with the shell



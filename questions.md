## Question1: why is it necessary to fork before calling exec()?
when exec() is called, it REPLACES the current process with the process described within the function call. 
essentially overwriting the code for the current process. If it wasn't called from a child, it would replace the entire
shell, terminating execution at the end of that call.

## Question2:how does fprintf work?
fprintf is composed of three blocks, the file stream it prints into, a format specified block of text to be written, and any values formatted into said block of text.
The file stream is where the text is printed to, this could be a file or standard output. The function calls the lowerlevel function write() to send the data to this 
source. The formatted text is then sent to that file while several characters are specified for formatting purposes.
"%" marks the begining of a format specified variable that would be taken from the next parameter passed into the call.
different characters refer to different data types that can be entered to specify how they would be printed to the file stream to keep their intended type 
in their new location or else they would all become 1's and 0's in the memory. 



learned from:
https://www.scaler.com/topics/fprintf-in-c/ 
https://stackoverflow.com/questions/2457656/understanding-the-hardware-of-printf

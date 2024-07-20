## Question1: why is it necessary to fork before calling exec()?
when exec() is called, it REPLACES the current process with the process described within the function call. 
essentially overwriting the code for the current process. If it wasn't called from a child, it would replace the entire
shell, terminating execution at the end of that call.

## Question2:how does fprintf work?
fprintf is composed of three blocks, the file stream it prints into, a format specified block of text to be written, and any arguments formatted into said block of text.

the function calls the vfprintf function with the arguments added to an array for use.

in vfprintf The file stream is where the text is printed to, this could be a file or standard output (STDOUT). this stream is responsible for where the buffered text (from the next argument) is put at the end of the functions run. 

For the text being printed to that buffer, each character is read one by one and put into the buffer. Special characters such as % of \ result in different behavior depending on the following character(s). This is where the formatted in fprintf comes from. these characters represent either format specifiers %(s,c,d, etc...) or escape characters to use in the string without compilation erros \(n, t, ", etc). Once buffered these characters are written to the file through system calls like fwrite() to select the exact file to write to and the contents of that write. 

the arguments provided after the text are to fill the format specifiers used within the text. These need to be added in this way to add modularity to the function and specified individually  since they need to be flagged apropriately for what they need to be written as to the write() call. 

Once the end of the text is reached (EOF character), the function closes the file stream 



learned from:
https://stackoverflow.com/questions/2457656/understanding-the-hardware-of-printf
https://github.com/lattera/glibc/blob/master/stdio-common/fprintf.c
https://github.com/lattera/glibc/blob/master/stdio-common/vfprintf.c

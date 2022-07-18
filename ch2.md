# Chapter 2 - Basic Commands and Directory Hierarchy

`bash` (is just a link to `/bin/sh`) is normally the default shell in a Linux distrobution and it is a programming environment where commands are given, they can be other programs or inbuilt features within the shell.

The `terminal` is a shell window and displays a prompt showing `name@host:path$` (is slightly different on other distros). `name` is the username, `host` is the name of the machine, `path` is the current working directory.

`I/O Streams` are used to read and write data. There are 3 streams: 
* Standard Input (stdin)
* Standard Output (stdout)
* Standard Error (stderr)

Some commands depend on input (like `cat`), if none is given then the command receives it's input from `standard input`. CTRL-D stops standard input which sends an EOF message to the program and terminates it.

| Command | Description | Example |
| --- | --- | --- |
| echo | Prints arguments to standout output  | `echo howdy` | 
| cat | Outputs one or more files or another source of input | `cat /etc/passwd` |
| ls | Lists the contents of a directory | `ls -l /` |
| cp | Copies from *file1* to *file2* or copies files to a directory | `cp file1 file2` |
| mv | Renames *file1* to *file2* | `mv file1 file2` |
| touch | Creates a file, if already created, it updates the modification timestamp | `touch file` |
| rm | Removes a file | `rm file` |

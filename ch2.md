# Chapter 2 - Basic Commands and Directory Hierarchy

`bash` (is just a link to `/bin/sh`) is normally the default shell in a Linux distrobution and it is a programming environment where commands are given, they can be other programs or inbuilt features within the shell.

The `terminal` is a shell window and displays a prompt showing `name@host:path$` (is slightly different on other distros). `name` is the username, `host` is the name of the machine, `path` is the current working directory.

`I/O Streams` are used to read and write data. There are 3 streams: 
* Standard Input (stdin)
* Standard Output (stdout)
* Standard Error (stderr)

Some commands depend on input (like `cat`), if none is given then the command receives it's input from `standard input`. CTRL-D stops standard input which sends an EOF message to the program and terminates it.

#### Basic Commands
| Command | Description | Example |
| --- | --- | --- |
| echo | Prints arguments to standout output  | `echo howdy` | 
| cat | Outputs one or more files or another source of input | `cat /etc/passwd` |
| ls | Lists the contents of a directory | `ls -l /` |
| cp | Copies from *file1* to *file2* or copies files to a directory | `cp file1 file2` |
| mv | Renames *file1* to *file2* | `mv file1 file2` |
| touch | Creates a file, if already created, it updates the modification timestamp | `touch file` |
| rm | Removes a file | `rm file` |

#### Navigation/Directories
| Command | Description | Example |
| --- | --- | --- |
| cd | Change to a specific directory, if no path is specified then go to home directory | `cd /` |
| mkdir | Creates a new directory | `mkdir dir` |
| rmdir | Removes an empty directory, fails if the directory is not empty | `rmdir dir` |


Shell globbing, characters that are processed before running the command, if nothing matches then the characters are parsed as any other, these include:
* `*` - on it's own, it matches everything in the current directory (`echo *`), otherwise it acts as 'match anything' character (`ls a*` - anything starting with 'a').
* `?` - match only one character (`ls ch?.md`).

#### Intermediate Commands
| Command | Description | Example |
| --- | --- | --- |
| grep | Prints lines from a file/input stream that match an expression. The options `-i` (case-insensitive) and `-v` (invert search) are the most important. `.*` matches anything, `.+` matches one or more characters, `.` matches only one character | `grep root /etc/*` |
| less | Pages through a file/input and has vim shortcuts (moving and searching) | `grep ie /usr/share/dict/words \| less` |
| pwd | Prints the current working directory (where the shell is currently at) | `pwd` |
| diff | Prints the differences between *file1* and *file2* | `diff file1 file2` |
| file | Prints what the format of a given file is | `file /etc/adduser.conf` |
| find | Locates a file in a directory, to use characters like `*`, `?`, `.`, enclose them in single quotes. An alternative is `locate` which searches a file index maintained by the system.| `find / -name passwd -print` |
| head/tail | View a specific amount of a given file, default is 10 lines, use `-n` for a specific amount | `head -n 5 /etc/passwd` |
| sort | Sorts the lines of a file/input in alphanumeric order, use `-n` for numbers and `-r` to reverse the order. | `cat /usr/share/dict/words \| sort -n` |

#### Changing Password and Shell
`passwd` is used to change the password for the user that it was ran on.

`chsh` is used to change the shell.

#### Dot Files
Dot files/folders are files/folders that start with a dot (*.bashrc*, *.login*, *.ssh*). Some programs don't show dot files/folders like `ls`, `ls -a` shows all files/folders and dot files/folders.

#### Shell and Environment Variables
* **Shell variables** are temporary variables containing text strings, to set a shell variable do:
```bash
$ STUFF=blah
```
To use the shell variable, do `$STUFF`, an example is `echo $STUFF`, which would complete to `echo blah`. Shell variables cannot be accessed in commands you run.
* **Environment variables** are variables that are passed onto programs that the shell runs, to set an environment variable, do:
```bash
$ STUFF=blah
export STUFF
```
Note that many programs accept an environment variable with opens that will run automatically when the program is ran, like the `LESS` variable, it contains the `-R -Q` options.

#### The Command Path
`PATH` is an environment variable that contains a list of directories to locate a command.
Each directory is separated with a colon (:).
```bash
$ echo $PATH
/usr/local/bin:/usr/bin:/bin
```
When a matching command is found, it uses the first matching one.
A directory can be added before the `PATH` to be searched first or last to be searched after the `PATH`:
```bash
$ PATH=dir:$PATH
```
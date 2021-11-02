# CLI Tools

## Finding Information

It's all about information!

### Commands

Replace `COMMAND` accordingly:

- `which COMMAND` - show the full path (use `-a` to show all locations) 
- `type COMMAND` - show type information (use `-a` to show all locations)
- `man COMMAND` - show the manual page
- `info COMMAND` - show the info page
- `help COMMAND` - show the help menu
 
You can use `help -m COMMAND | less` to show the help page in the typicall `man` style.
On <https://askubuntu.com/a/439411/478654> is a nice solution for a function to show either the man page or if there is no man page to show the help page instead.

### Files

To find files, information about them, and information in them, use the following commands:

- `dirname PATH` - output the directory name 
- `find . -type f -name "FILENAME"` - search files by their name
- `grep -E -i 'REGEX-SEARCH-TERM' FILE` - search content with regex interpolation and case insensetive 

## Processes Management

Show running processes:

```sh
top
htop
ps -A
```

Directly grep a PID or kill a process:

```sh
kill PID
pgrep
pkill
```

### How to kill a process

Use `pgrep <name>` or `pkill <name>`:

```sh
kill $(pgrep firefox)
pkill firefox
```

## Handling Output

### Using the null device


Use `/dev/null` (the "null device") to discard data and/or output, for example:

```sh
grep -Fx "search string" input_file > /dev/null
```

(`-F` to interpret the given search string as a so called "fixed string", meaning no regex interpration. `-x` to match whole lines. Instead of `> /dev/null` it would also be possible to use `-x` to tell grep to search quietly.)

### Checking the last exit status

To check the exit status of the last command use bashes `$?` like so:

```sh
echo $?
```

### Pipeing into file and still showing console output

To pipe some command output into a file and still be able to follow all the output in the console, use `tee` like so:

```sh
command |& tee output.txt     # to create a new file
command |& tee -a output.txt  # to append to the file
```

If `|&` is used, command1’s standard error, in addition to its standard output, is connected to command2’s standard input through the pipe;
it is shorthand for `2>&1 |`.
This implicit redirection of the standard error to the standard output is performed after any redirections specified by the command.

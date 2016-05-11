# Commands

## Exit Status

When a process terminates it returns an exit status. A status of 0 means that
the process executed successfully while a non-zero status signals an error. Each
command can use a more fine grained definition of the status codes, e.g., if
`curl` finishes with status 6 it means that it could not resolve the host.

```bash
# run curl and print exit status
curl http://www.google.c/; echo $?
```

### Exercise

1. What happens if you immediately run `echo $?` again after the command above?
2. Correct the url above and run again. What is the status now?


## Command Lists

In Bash, a (command) list is a sequence of one or more commands (or
[pipelines](pipelines.md)) separated by one of the operators `;`, `&&`, or `||`.

```bash

# Execute the commands in sequence and wait for each command to terminate.
command1; command2

# command2 is executed if and only if command1 is successful (zero status)
command1 && command2

# command2 is executed if and only if command1 is not successful (non-zero status)
command1 || command2
```

### Exercise

1. Execute curl and `echo 'OK'` if and only if command terminates successfully.
2. Execute curl and `echo 'Not OK'` if and only if command terminates unsuccessfully.
3. Check the exit status of 1 and 2 in all possible cases. Explain.




## man -- display manual pages

Use the `man` command to get the manual page for a specific command. The man
command itself normally uses, the `less` to display the manual. Basic short cuts in
`less`:

* `space` - forward one page
* `b` - backward one page
* `q` - quit
* `?` - help

### Exercise

1. Open the manual page for the command `grep` by running `man grep`.
- What does the command do?
- What does the `-c` flag do?

2. Open the manual page for the `man` command itself.
- What does the `-k` flag do? Try it on `man -k chown`. The `chown` command is
used to change owner of a file.
- What is the difference between `man chown` and `man -s 2 chown`?


## cat -- concatenate and print files

`cat` prints the file contents to the screen.

### Exercise

1. Create a text file and show its content by `cat file.txt`.
2. What does the `-e` flag do?
3. What does the `-n` flag do?


## less -- a file viewer

While `cat` simple prints the whole file to the screen, `less` prints one page
at a time. Short cuts:


* `space` - forward one page
* `b` - backward one page
* `q` - quit
* `?` - help
* `/` + text - search forward for text (regexp)
* `n` + text - find next search match
* `N` + text - find next previous match
* `-i` - toggle case sensitivity for search


### Exercise

1. Try the above commands on a file, e.g. `less file.txt`.






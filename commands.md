# Commands

## man - manual
Use the `man` command to get the manual for a specific command. Normally, the
`less` command is used to display the manual. Short cuts in `less`:

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


## cat - show file contents

`cat` dumps the file contents on the screen.

### Exercise

1. Create a text file and show its content.
2. What does the `-e` flag do?
3. What does the `-n` flag do?


## less - a pager


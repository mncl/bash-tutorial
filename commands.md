# Commands

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






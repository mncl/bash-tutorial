# Introduction

Bash is one of many so called command shell, i.e. a command line interface to the
operating system on which it runs. Some commands the you write are built in to
Bash and some are part of the operating system.

If you are unsure where a command comes from you use the `type` command to get
some quick information. Below I execute `type grep`. On my machine grep is
aliased in order to add color output.


```bash
$ type grep
grep is aliased to `grep --color=auto'
$ type -a grep
grep is aliased to `grep --color=auto'
grep is /usr/local/bin/grep
grep is /usr/bin/grep
```

With the `-a` flag we see all types of grep command installed. As you can see
I've got not only the alias, but also two files. The last one in `/usr/bin` is
the default that comes with Mac OS X (BSD grep). The first one in `/usr/local/bin` is the
GNU version of grep which I installed using Homebrew.

It is important to note that different Unixes may have different implementations
of the operating system commands like `grep`. The GNU versions are what's
default on Linux, while Mac OS X is derived from BSD. Often the differences are minor but
, but sometimes, for example BSD grep does not have a `--perl-regexp` flag.

If you are on a Mac I recommend that you install [Homebrew](http://brew.sh/),
the missing package manager for OS X. With Homebrew you can easily install the
GNU versions of your favorite commands.

```bash
# Install GNU grep as 'grep' and not 'ggrep'
brew install grep --with-default-names
```

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


## Editing Files with vi

When you edit files on your local machine you can use your favorite editor, but
when on a remote server it is good to know how to edit a file with `vi`.

Note that nowadays `vi` is often come to mean `vim` which is an improved
successor. Should you compare them the first difference you'll notice is that
arrow keys works properly in `vim`. On most systems `vi` is just a symbolic link
to `vim`.

```bash
$ type vi
vi is hashed (/usr/bin/vi)
$ ls -l /usr/bin/vi
lrwxr-xr-x  1 root  wheel  3  1 Okt  2015 /usr/bin/vi -> vim
```


1. Start `vi`. Read `:help`. Navigate `|tags|` with `Ctrl-5` on international
keyboards. Use `:q` to quit.

1. Create or modify a file using `vi myfile.txt`.
    - Navigate to the position you want to change.
    - Press `i` to enter insertion mode. Update text.
    - Press `ESC` or `Ctrl-C` to go back to view mode.
    - Save and quit `:wq`.
    - Quite without saving `:q!`





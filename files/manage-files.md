# Manage Files

Run the below to setup some initial files.
```bash
#/bin/bash
cd
mkdir -p cool-proj cool-proj/src                 # What does -p do?
cd cool-proj
echo 'This is a README file.' > README
echo "console.log('Hello.')" > src/hello.js
echo "console.log('Goodbye.')" > src/goodbye.js
```


1. What does `mkdir -p` do?

1. What is your current working directory? Use `pwd`.

1. Backup the file to `README.bak` with `cp`. Try with and without the `-a`
flag. Differences?

1. You could use `cat` to copy the file. Hint: similar to how the file was
created. Warning: this is not suitable for backups.

1. Use `mv` to rename the file to `README.md`. What does the `-i` and `-v` flags
do?

1. Use `rm` to remove the backup file `README.bak`. Try `-i` flag.

1. Read the manual on `rm -rf` and then run `rm -rf src` to remove `src` folder
and all its files without asking!


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

1. Modify the text using `vi README.md`.
    - Navigate to the position you want to change.
    - Press `i` to enter insertion mode. Update text.
    - Press `ESC` or `Ctrl-C` to go back to view mode.
    - Save and quit `:wq`.
    - Quite without saving `:q!`

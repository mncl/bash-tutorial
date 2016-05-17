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



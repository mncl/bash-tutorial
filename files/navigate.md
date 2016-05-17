# Navigate the File System

The Unix File System is like a tree with a root directory denoted by `/`. A
directory can contain other files and directories (folders).

Every user has a `HOME` folder. Usually this is where the all new terminals
start. Use `cd dir` to navigate to a new directory `dir`. Use `cd ..` to change
to the parent directory.


```bash
$ pwd                               # print working dir
/Users/alice
$ cd ..                             # Go to parent dir
$ pwd
/Users
$ ls                                # list files
Guest          alice          bob
$ cd alice
$ pwd
/Users/alice
```

## Exercise
1. Go to the directory `/etc`. See if there is a file `ntp.conf`. Use `cat` to
print its contents.
2. Go to `/var/log`. What files are there? Cat `system.log`.
3. Go back to your home folder by executing `cd` without arguments.
4. Read `man ls` and try
    - `ls -1`
    - `ls -F`
    - `ls -l`
    - `ls -a`. Do you see `..`? What is `.`?
    - `ls -laFh`. What does `-h` do?



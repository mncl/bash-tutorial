# Permissions

Basic Unix file permissions can be controlled by three commands:
- chmod: change read/write/execute permission modes for user/group/other. See below
- chown: change the owner of a file.
- chgrp: change the group of a file.

Use `ls -l` to view permissions on a file or directory.

```bash
$ ls -l /Users/alice/cool-proj
total 8
-rw-r--r--  1 alice  staff   23 17 Maj 13:32 README.md
drwxr-xr-x  4 alice  staff  136 17 Maj 13:32 src
```

The first column shows the file mode in as a formatted string on the form
`drwxrwxrwx`. The third and fourth shows the owner and group.

| d         | rxw  | rxw   | rxw   |
| --------- | ---- | ----- |-----  |
| file type | owner| group | other |


File types are note part of the actual unix permissions but rather a convenience
of `ls`.

| File Type | Meaning                 |
| --------- | ----------------------- |
| b         | Block special file.     |
| c         | Character special file. |
| d         | Directory.              |
| l         | Symbolic link.          |
| s         | Socket link.            |
| p         | FIFO.                   |
| -         | Regular file.           |


The user/owner/group modes each show three characters where:
- `r` readable by user/owner/group
- `w` readable by user/owner/group
- `x` executable by user/owner/group


The `chmod` command can be used to change file permissions. Permission can be
given in symbolic mode or octal mode.

Check `man chmod` and change the file mode of the README to match the below listing. Try both octal
and symbolic mode.

```bash
-rw-rw----   1 jon  staff    23B 17 Maj 13:32 README.md
-rwxr-xr-x   1 jon  staff    23B 17 Maj 13:32 README.md*
-rw-------   1 jon  staff    23B 17 Maj 13:32 README.md
----------   1 jon  staff    23B 17 Maj 13:32 README.md
```


## Exercise

1. Change permission of the `README` file in the [Mangage
files](manage-files.md) section so it is only readable by the owner.




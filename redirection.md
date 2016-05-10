# Redirection

In the Unix world there are three standard file descriptors stdin, stdout and
stderr. Normally, when a command executes it reads its input from stdin and
writes its normal output to stdout. Stderr is used for error output.

Name   | Descriptor    | File          | Default        |
-----  | ------------- | ------------- | -------------- |
stdin  | 0             | /dev/stdin    | keyboard       |
stdout | 1             | /dev/stdout   | screen         |
stderr | 2             | /dev/stderr   | screen         |

The `echo` command, for example, writes its arguments to the standard output
which is the screen under normal circumstances.

```bash
# Writes a message to the screen
echo 'Hello, world!'

# Prompts for name and prints a message
read -p 'Enter name: ' name && echo "Hi $name!"
```

A common use case is to change the default location for for output and input. This is called redirect.
input from a file. Use the `cmd > file.txt` to make the command `cmd` write to a
file and `cmd < file.txt` to read from a file.

```bash
# The output from echo is sent to hello.txt
echo 'Hello, world!' > hello.txt

# The output from echo is appended to hello.txt
echo 'This is appended!' >> hello.txt

# The stderr output is written to file
grep ello hello.txt hej.txt 2> grep-errors.txt

# The stderr output is written to the same destination as stdout
# the & is needed so that bash doesn't write to the file called '1'.
grep ello hello.txt hej.txt 1> grep.txt 2>&1

# Write name to file.
echo "Jon" > name.txt

# Read name from file (what happen to the prompt?)
read -p 'Enter name: ' name < name.txt && echo "Hi $name!"
```

## Exercises


# Redirection
In the Unix world there are three standard file descriptors stdin, stdout and
stderr. Normally, when a command executes it reads its input from stdin and
writes its normal output to stdout. Stderr is used for error output.

Name   | Descriptor    | File          | Default        |
-----  | ------------- | ------------- | -------------- |
stdin  | 0             | /dev/stdin    | keyboard       |
stdout | 1             | /dev/stdout   | screen         |
stderr | 2             | /dev/stderr   | screen         |

Use the `cmd > file.txt` to make the command `cmd` write to a file and
`cmd < file.txt` to read from a file.

## Examples

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

# Read first line from hello.txt
read line < hello.txt; echo $line
```

## Exercises


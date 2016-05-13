# Pipelines

A pipeline (or simply pipe) is a sequence of commands connected so that the output of
one command is the input of the other. E.g.

```
# the number of files in current dir contain 'js'
ls | grep 'js' | wc -l
```

The pipe character between each command connects the stdout of the first command
to the stdin of the next command. Thus, `ls` produces a list of files on stdout, which is connected to
the stdin of grep which in turn prints only lines containing
`js` on its stdout, which is connected to the stdin of `wc` which prints the
number of input lines.


## Exercise

1. Compare the output of `ls`, `ls -1` and `ls | cat`. What do you see? Why?

2. Investigate what happens to the stderr of each command. For example, start
with `echo 'hello' >&2 | wc -l`. Use what you've learned in
[Redirection](redirection.md).



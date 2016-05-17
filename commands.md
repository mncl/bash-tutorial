# Processes

Every commands executed from bash runs in its own process. When a process
terminates it returns an exit status. A status of 0 means that the process
executed successfully while a non-zero status signals an error. Each command can
use a more fine grained definition of the status codes, e.g., if `curl` finishes
with status 6 it means that it could not resolve the host.

```bash
# run curl and print exit status
curl http://www.google.c/; echo $?
```

### Exercise

1. What happens if you immediately run `echo $?` again after the command above?
2. Correct the url above and run again. What is the status now?


## Command Lists

In Bash, a (command) list is a sequence of one or more commands (or
[pipelines](pipelines.md)) separated by one of the operators `;`, `&&`, or `||`.

```bash

# Execute the commands in sequence and wait for each command to terminate.
command1; command2

# command2 is executed if and only if command1 is successful (zero status)
command1 && command2

# command2 is executed if and only if command1 is not successful (non-zero status)
command1 || command2
```

### Exercise

1. Execute curl and `echo 'OK'` if and only if command terminates successfully.
2. Execute curl and `echo 'Not OK'` if and only if command terminates unsuccessfully.
3. Check the exit status of 1 and 2 in all possible cases. Explain.


## Subshells

If you delimit a command with parenthesis it executes in its own subshell. E.g.
changing directory or setting enviroment variables in a subshell does not affect
the parent shell.


```bash
$ (cd /var/log/; ls sys*); pwd
(cd /var/log/; ls sys*); pwd
system.log      system.log.1.gz system.log.3.gz system.log.5.gz
system.log.0.gz system.log.2.gz system.log.4.gz system.log.6.gz
/Users/alice
```

# Scopes



Bash comes with a few different scopes:

0. Inital
1. Block,  `{}`
2. Subshell, `()`
3. Function, `name() {}`
4. source, `source`
5. Pipeline, `|`
6. External commands

Each scope has
* a set of built in special variables
* a environment that contains variables
* its own stdin, stdout and stderr
* a exit code or return value. 0-255 where 0 is success and 1-255 is failed

### Initial
This is the environment that the script starts with.
When running commands from the terminal each command acts as if it has block scope unless specified.

### Block
Blockscope keeps the same special variables and environment as the surrounding.
If no stdin is specified the surrounding scopes stdin is used.
If no redirection is specified for stdout or stderr they are connected to the surrounding scopes equivialents.
The exit code is that of the last command executed.

```bash
{ echo -n ' World' | rev ;  echo -n 'Hello,' | rev ; } | tr -d '\n' | rev
{ true; false;} ;  echo $?
{ echo -n Hello ; false } || {echo World }
```

### Subshell
Each subshells gets a new environment that inherits the surrounding. Changes to variables are lost after the subshell ends.
Follows the same rules on redirection and exit codes as Blockscope.
Subshells are more expensive to invoke than block scopes.
Special variables like `"$@"`, current directory and options(`set -o pipefail`) are reset after leaving a subshell.
```bash
(HOME="garbage"; echo "$HOME"; cd ..; set -x; pwd; ) ; pwd ; echo "$HOME"
(set -o pipefail ; false | true ; ) ; echo on $? ; false | true ; echo off $?
(source <(echo '( shift ; echo "$@";); echo "$@";') hello world)
```

### Function
Functions works as blocks with the exception that some special variables update.
This includes `$@`.
When exiting the function special variables that where updated are set to what they where before entering the function.
To get function invocation scope variables use `local`, remeber that local is a command and it has its own return value.
```bash
printArgs() {
  g=$(false)
  echo $?
  local thing=$(false)
  echo $?
  for arg in "$@"
    do echo "$arg"
  done
}

printArgs A B C

```
### source
Source scope works the same way as functions and it is posible to pass arguments or place it on a pipeline (see pipeline for more information).
Source targets a bash source file that is parsed in the current environment.
The key feature over functions is that source can re/define functions and variables that will be avalible in the environment.
```bash
echo "World!" | source <(echo 'echo -n "$1 " ; read someText; echo $someText') "Hello"
(source <(echo 'echo "Loading function" ;printHello() { echo hello;}; echo "loaded function"') ; printHello ;)

```

### Pipeline
When commands are chained with pipeline the environment behave rather differently than you might expect.
Compare the following examples.

... More pipe examples
```bash
A="foo"; echo "$A" ; { A="bar"; echo "$A" ;} | cat - ; echo "$A"
```
```bash
A="foo"; echo "$A"; { A="bar"; echo "$A" ;};  echo "$A"
```

### External commands
Commands that are not shell built ins see the environment variables that are exported.
This is inially the same as your inital environment.
`export foo` marks the variable foo to the list of variables to be exported.
`export foo="some value"` sets the variable foo to 'some value' and marks it to be exported.
The exported variables use the current values, not what was originally exported.
Variables presented before the command also gets exported. 

```bash
A="Hello!" ; env | grep Hello
A="Hello!" env | grep Hello
(export A="Hello!" ; env | grep Hello)
(export A="Hello!" ; A="World!" ; env | grep World)
(export A="Hello!" ; A="World!" ; A="fantastic" env | grep fantastic
```



# Simple_Shell

## Simple Shell > In this project, we coded from scratch a simple Unix Shell
A shell does three main things in its lifetime.
1. Initialize: In this step, a typical shell would read and execute its configuration files. These change aspects of the shell’s behavior.
2. Interpret: Next, the shell reads commands from stdin (which could be interactive, or a file) and executes them.
3. Terminate: After its commands are executed, the shell executes any shutdown commands, frees up any memory, and terminates.
 
## Custom Builtins
* `exit` exits shell (Usage: `exit [status]`)
* `env` prints environmental variables (Usage: `env`)
* `setenv` creates or modifies an environmental variable (Usage: `setenv name value`)
* `unsetenv` removes an envrionmental variable (Usage: `unsetenv name value`)
* `cd` changes directories (Usage: `cd [-][~][path]`)

## Functions and system calls used from C standard libraries
`isatty`, `perror`, `fork`, `signal`, `malloc`, `free`, `getcwd`, `chdir`, `execve`, `write`, `wait`, `exit`

## Description of what each file shows:
| File Name | Description |
|-----------|-------------|
| shell.h | holds prototypes of functions spread across all files |
| shell.c | holds entrance into the Simple Shell program |
| man_1_simple_shell | custom manual page for our simple shell |

### Helper files
| File Name | Description |
|-----------|-------------|
| env_control.c | custom functions for built-in commands, replica of env, setenv, unsetenv |
| built_in.c | custom functions for built-in commands, replica of exit, cd, ctrl_c, ctrl_d |
|string_func1.c | handle strings including comparing, duplicating, concatenatingand length of a string |
| string_func2.c | handle strings including getting string's length, copying the string, and printing out  each char of string |
## Mode
The simple shell work like this in interactive mode:
```C
$ ./hsh
($) /bin/ls
hsh main.c shell.c
($)
($) exit
$
```
but also in non-interactive mode:
```C
$ echo "/bin/ls" | ./hsh
hsh main.c shell.c test_ls_2
$
$ cat test_ls_2
/bin/ls
/bin/ls
$
$ cat test_ls_2 | ./hsh
hsh main.c shell.c test_ls_2
hsh main.c shell.c test_ls_2
$
```
## Environment
* Language: C
* OS: Ubuntu 14.04 LTS
* Compiler: gcc 4.8.4
* Style guidelines: Betty style

## How To Install, Compile, and Use

Install and Compile
``` C
(your_terminal)$ git clone https://github.com/egl-cypher/Simple_Shell.git
(yourRRRR_terminal)$ cd simple_shell
(your_terminal)$ gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c -o hsh
```
Run the C Shell
```C
./hsh
```

Type in command
```C
echo hello
```

Sample Usage
```C
#cisfun$ echo hello
hello
```
Stop and return to your original shell
```C
#cisfun$ exit
(your_terminal)$
```
## To Do
More functionality can still be added (e.g. handle aliases, pipelines)
***
## Authors

* Ransom Quaye 




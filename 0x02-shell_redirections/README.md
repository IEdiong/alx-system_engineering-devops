# 0x02. Shell, I/O Redirections and filters

## 0. Hello World
A bash script that prints "Hello, World", followed by a new line to the standard output.
```
#!/bin/bash
echo "Hello, World"
```
> The "echo" command is used to print to standard output the string passed to it.

Actual solution in [0-hello_world](./0-hello_world)

## 1. Confused smiley
A bash script that displays a confused smiley.
```
#!/bin/bash
echo "\"(Ôo)'"
```
> The "\\" (backward slash) is used to escape the following character, in this case the following double quote.

Actual solution in [1-confused_smiley](./1-confused_smiley)

## 2. Let's display a file 
A bash script that displays the content of the `/etc/passwd` file.
```
#!/bin/bash
cat /etc/passwd
```
> The cat command is used to print to standard output the content of the file passed to it. 

Actual solution in [2-hellofile](./2-hellofile)

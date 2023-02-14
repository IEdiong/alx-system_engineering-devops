# 0x02. Shell, I/O Redirections and filters

## 0. Hello World
A bash script that prints `"Hello, World"`, followed by a new line to the standard output.
```
#!/bin/bash
echo "Hello, World"
```
> The `echo` command is used to print to standard output the string passed to it.

Actual solution in [0-hello_world](./0-hello_world)

## 1. Confused smiley
A bash script that displays a confused smiley.
```
#!/bin/bash
echo "\"(Ôo)'"
```
> The `\` (backward slash) is used to escape the following character, in this case the double quote preceding the `\`.

Actual solution in [1-confused_smiley](./1-confused_smiley)

## 2. Let's display a file 
A bash script that displays the content of the `/etc/passwd` file.
```
#!/bin/bash
cat /etc/passwd
```
> The `cat` command is used to print to standard output the content of the file passed to it. 

Actual solution in [2-hellofile](./2-hellofile)

## 3. What about 2? 
A bash script that displays the content of two files, `/etc/passwd` and `/etc/hosts`.
```
#!/bin/bash
cat /etc/passwd /etc/hosts
```
> The `cat` command can take in multiple files as arguments.

Actual solution in [3-twofiles](./3-twofiles)

## 4. Last lines of a file 
A bash script that displays the last 10 lines of `/etc/passwd`.
```
#!/bin/bash
cat /etc/passwd | tail
```
> The standard output of one command can be fed into the standard input of another command using the `"|"`. In the solution above, the output of the `cat /etc/passwd` command is fed into the `tail`.
> The `tail` command by default prints to standard output the last `10` lines of the input passed into it. 

Actual solution in [4-lastlines](./4-lastlines)

## 5. I'd prefer the first ones actually 
A bash script that displays the first 10 lines of `/etc/passwd`.
```
#!/bin/bash
cat /etc/passwd | head
```
> The `head` command by default prints to standard output the first `10` lines of the input passed into it. 

Actual solution in [5-firstlines](./5-firstlines)

## 6. Line #2 
A bash script that displays the third line of the file `iacta`, which is in the working directory.
```
#!/bin/bash
cat iacta | head -n 3 | tail -n +3
```
OR
```
#!/bin/bash
cat iacta | head -n 3 | tail -n 1
```
OR
```
#!/bin/bash
head -n 3 iacta | tail -n +3
```
OR
```
#!/bin/bash
head -n 3 iacta | tail -n 1
```
> When the `-n NUM` option is passed to the `head` command it prints to standard output the first `NUM` lines instead of the first `10`. If `NUM` has a leading `'-'`, it will print all but the last `NUM` lines of each file.

> When the `-n NUM` option is passsed to the `tail` command it prints to standard output the last `NUM` lines instead of the last `10`. If `NUM` has a leading `'+'` as in `tail -n +3`, it will output starting from the line `NUM`.

> If you choose to omit the `-n` flag, then the `NUM` must have a leading `-` as in `tail -2` and `head -3`. 

Actual solution in [6-third_line](./6-third_line)

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

> If you choose to omit the `-n` flag, then the `NUM` must have a leading `-` as in `tail -2` and `head -3`. The `tail -n +3` command would now be `tail +3`. 

Actual solution in [6-third_line](./6-third_line)

## 7. It is a good file that cuts iron without making a noise 
A bash script that creates a file named exactly `\*\\'"Best School"\'\\*$\?\*\*\*\*\*:)` containing the text `Best School` ending by a new line.

```
#!/bin/bash
echo "Best School" > \\\*\\\\"'\"Best School\"\\'"\\\\\*\$\\\?\\\*\\\*\\\*\\\*\\\*\:\) 
```
> We can redirect the output of the `echo` command from standard output to the file named above using the `>` operator.

> We also use `\` to escape special characters.

Actual solution in [7-file](./7-file)

## 8. Save current state of directory 
A bash script that writes into the file `ls_cwd_content` the result of the command `ls -la`. It creates the file, `ls_cwd_content`, if it doesn't exists but if it does exist it should be overwritten.

```
#!/bin/bash
ls -la > ls_cwd_content
```

> We can use the `>` operator to redirect the output to the file `ls_cwd_content`.

> The `>` operator overrides the content of the file if the file already exists else it would create the file anew.

Actual solution in [8-cwd_state](./8-cwd_state)

## 9. Duplicate last line 
A bash script that duplicates the last line of the file `iacta`, which will be in the working directory.

```
#!/bin/bash
tail -n 1 iacta >> iacta
```

> The `tail` command can be used to output the last `n` lines then,

> We can use the `>>` operator to append the output to the end of the file `iacta`.

Actual solution in [9-duplicate_last_line](./9-duplicate_last_line)

## 10. No more javascript 
A bash script that deletes all the regular files with a `.js` extension that are present in the current directory and all its subfolders.

```
#!/bin/bash
find . -type f -name "*.js" -delete
```

> The `find` command is used in the syntax

```
find [where to start searching from] [expressions determines what to find] [-options] [what to find]
```

> You can read up more about how to use the `find` command [here](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/) and [there](https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/).

Actual solution in [10-no_more_js](./10-no_more_js)

## 11. Don't just count your directories, make your directories count
A bash script that deletes all the regular files with a `.js` extension that are present in the current directory and all its subfolders.

```
#!/bin/bash
find . -mindepth 1 -maxdepth 1 -type d | wc -l
```

> The `wc` command means `word count`. The `wc -l` command thus performs a line count on it's input.

> The `-mindepth` and `maxdepth` options have to come before the `-type` option because they are global options.

> You can read up more about [how this command works](https://www.baeldung.com/linux/count-directories#1-using-pure-bash)

Actual solution in [11-directories](./11-directories)


# 0x03. Shell, init files, variables and expansions

## 0. <o>

A bash script that creates an alias with the name `ls` and a value of `rm *`.
```
#!/bin/bash
alias ls="rm *"
```
> The alias command allows a user to create simple names or abbreviations (even consisting of just a single character) for commands regardless of how complex the original commands are and then use them in the same way that ordinary commands are used.

> The general syntax for the alias command varies somewhat according to the shell. In the case of the bash shell it is:

> alias [-p] [name="value"]

Actual solution in [0-alias](./0-alias)

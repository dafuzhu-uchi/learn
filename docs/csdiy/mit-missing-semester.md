---
title: MIT Missing Semester
parent: CS DIY
nav_order: 1
toc: true
---

# MIT Missing Semester
{: .no_toc}

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Shell

| Command | Meaning/output |
|---|---|
| `date` | Mon Oct 27 11:03:30 CDT 2025 |
| `echo "Hello world"` | Hello world |
| `echo $PATH` | print all paths |
| `which echo` | echo: shell built-in command |
| `pwd` | /Users/zdf |
| `cd -` | toggles between two different directories |
| `man ls` | manual for command `ls` (press `q` to exit) |
| `ls -l` | Long format (detailed) | 
| `mv a b` | Move from a to b, can use it for renaming |
| `cp a b` | Copy from a to b |
| `rm a` | Remove, by default it's not recursive |
| `rmdir` | can only delete empty dir |
| `mkdir` | make directory |
| `Ctrl+l` | clear terminal, go back to top |
| `sudo su` | change identity to super user |

Arguments are seperated by spaces. 

Environment variable: things set whenever you start your shell. One critical variable is `$PATH`. Bash will search through all these paths to get the programs/files you run in the command.

Use `which` if we want to know which program/file is actually running.

Most programs take flags and options, most start with a `-`.

Some operations with `<` and `>`.

```bash
zdf@zdf-mac learn % echo hello > hello.txt
zdf@zdf-mac learn % cat hello.txt
hello
zdf@zdf-mac learn % cat < hello.txt > hello2.txt
zdf@zdf-mac learn % cat hello2.txt
hello
```

`>` is overwrite, `>>` is append.

```bash
zdf@zdf-mac learn % cat < hello.txt >> hello2.txt
zdf@zdf-mac learn % cat hello2.txt
hello
hello
```

Pipe `|`: take output from the left, pass as input to the right

```bash
zdf@zdf-mac learn % ls -l ~ | tail -n1
drwxr-xr-x    4 zdf  staff    128 Mar 22  2024 ~
```
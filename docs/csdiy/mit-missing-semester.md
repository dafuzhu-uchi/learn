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

Website: [`./missing-semester`](https://missing.csail.mit.edu/)

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

## Shell scripting

```bash
foo=bar
echo "$foo"
# prints bar
echo '$foo'
# prints $foo
```

| command | meaning |
|---|---|
|`$0` | Name of the script |
|`$1` to `$9` | Arguments to the script. $1 is the first argument and so on.|
|`$@` | All the arguments|
|`$#` | Number of arguments |
|`$?` | Return code of the previous command |
|`$$` | Process identification number (PID) for the current script |
|`!!` | Entire last command, including arguments. A common pattern is to execute a command only for it to fail due to missing permissions; you can quickly re-execute the command with sudo by doing sudo !! |
|`$_` | Last argument from the last command|

- The true program will always have a `0` return code and the false command will always have a `1` return code.

```bash
false || echo "Oops, fail"
# Oops, fail

true || echo "Will not be printed"
#

true && echo "Things went well"
# Things went well

false && echo "Will not be printed"
#

true ; echo "This will always run"
# This will always run

false ; echo "This will always run"
# This will always run
```

To print variable using `$`, do not use `'`, instead use `"`.

- An example:

```bash
#!/bin/bash

echo "Starting program at $(date)" # Date will be substituted

echo "Running program $0 with $# arguments with pid $$"

for file in "$@"; do
    grep foobar "$file" > /dev/null 2> /dev/null
    # When pattern is not found, grep has exit status 1
    # We redirect STDOUT and STDERR to a null register since we do not care about them
    if [[ $? -ne 0 ]]; then
        echo "File $file does not have any foobar, adding one"
        echo "# foobar" >> "$file"
    fi
done
```

- `ls *.sh` list all files ends with `.sh`. 
- `ls project?` expands one character. 
- `{}` is very powerful.

```bash
convert image.{png,jpg}
# Will expand to
convert image.png image.jpg

cp /path/to/project/{foo,bar,baz}.sh /newpath
# Will expand to
cp /path/to/project/foo.sh /path/to/project/bar.sh /path/to/project/baz.sh /newpath

# Globbing techniques can also be combined
mv *{.py,.sh} folder
# Will move all *.py and *.sh files


mkdir foo bar
# This creates files foo/a, foo/b, ... foo/h, bar/a, bar/b, ... bar/h
touch {foo,bar}/{a..h}
touch foo/x bar/y
```

- The kernel knows to execute this script with a python interpreter instead of a shell command because we included a shebang (`#!`) line at the top of the script

```bash
#!/usr/local/bin/python
import sys
for arg in reversed(sys.argv[1:]):
    print(arg)
```

- Usage of `find`

```bash
# Find all directories named src
find . -name src -type d
# Find all python files that have a folder named test in their path
find . -path '*/test/*.py' -type f
# Find all files modified in the last day
find . -mtime -1
# Find all zip files with size in range 500k to 10M
find . -size +500k -size -10M -name '*.tar.gz'
```

- ripgrep (`rg`)

```bash
# Find all python files where I used the requests library
rg -t py 'import requests'
# Find all files (including hidden files) without a shebang line
rg -u --files-without-match "^#\!"
# Find all matches of foo and print the following 5 lines
rg foo -A 5
# Print statistics of matches (# of matched lines and files )
rg --stats PATTERN
```
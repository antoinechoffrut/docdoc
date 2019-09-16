---
layout: post
title:  "Unix commands"
date:   2019-06-27 13:20:00 +0100
categories: unix
---

This is my own cheatsheet on unix commands.

I am on a mac (currently Mojave), so some things may be specific to that OS.

# The `ls` command
The `ls` command lists files (including directories, since "everything is a file").  

List everything in the current directory:  
```bash
ls
```
List everything in a specified directory:  
```bash
ls path/to/directory
```
List one file per line (in current directory):  
```bash
ls -1
```
(the `1` is a one "1", not an ell "l").  [Alternatively](alternative-ls-one-file-per-line):  
```bash
ls -a | cat
```

List contents of subdirectories in current directory:  
```bash
ls */
```

List subdirectories only:  
```bash
ls -d */
```

List of changed directories:
```bash
ls -ltc


List files in decreasing order of size:  
```bash
ls -Sl
```
List files in increasing order of size:  
```bash
ls -Slr
```
Display complete time information (used with `-l`) including month, day, hour, minute, second, and year:  
```bash
ls -lT file.txt
```

Listing files by file extension (probably not robust nor safe, but
solution is cute, from
[superuser](superuser-cute-file-listing-by-extension)):  
```bash
ls | rev | sort | rev
```


Some options:  
- `-a` lists everything in the directory, including hidden files,
  starting with `.`
- `-l` use long listing format  (note `l` is an ell "l", not a one "1") including ([more info here](garron-ls-file-permissions)):  
  -  file permission
  -  number of links or directories inside current or specified directory
  -  file owner
  -  groupowner
  -  filesize (in bytes by default, or else use the `-h` option for human readable)
  -  creation date
- `-t` sorts by modification time
- `-r` reverses order
- `-u` sorts by last access time
- `-F` shows the file type 


## Remark on parsing output of `ls`

There is a viewpoint that [`ls` is designed for human
consumption](gilles-ls-for-human-consumption) and therefore [outputs
to `ls` should not be parsed](wooledge-dont-parse-outputs-to-ls).

# The `wc` command
Count the number of lines (`-l`), words (`-w`) or characters (`-c`):  
```bash
wc -l file.txt
wc -w file.txt
wc -c file.txt
```

# The `sort` command  
Sort lines of text files.  

Sort lines alphabetically:  
```bash
sort file.txt
```
Sort lines numerically:  
```bash
sort -n file.txt
```
Sort numerically along second column, where columns are separated by
`,`:  
```bash
sort -t "," -k 2 -n file.csv
```



# The `cut` command  
[Reference](thegeekstuff-cut-command-examples)  
The `cut` command divides a file into several columns.  
Main options:  
- `-c`: list of columns to select  
- `-f`: list of fields to select   
- `-d`: specify delimiter  

Select columns `2` through `4`:  
```bash
cat file.txt | cut -c2-4
```
Select columns `2` and `4`:  
```bash
cat file.txt | cut -c2,4
```
Select all columns starting with column `3`:  
```bash
cat file.txt | cut -c3-
```

Select columns `2`, and `4` through `7`:  
```bash
cat file.txt | cut -c2,4-7
```

Select columns `2` and `5` (separated by `,`):  
```bash
cat file.txt | cut -d2,4-7
```
Select all fields starting with field `3`:  
```bash
cat file.txt | cut -d3-
```

# The `stat`  command  
Display file status.  
The `-f` option specifies the format of display.  



# The translate command: `tr`

Print `PATH` variable as a list:
```bash
echo $PATH | tr ":" "\n"
```

Obfuscate your email address:
```bash
echo "name@example.com" | tr "namexplco" "poiuytrew"
echo "poiu@uyoitru.ewi" | tr "poiuytrew" "namexplco"
```


# Disk usage with `du`

The command `du` displays disk usage statistics.


A **summary** of a directory is the total space that it takes.

To display the disk usage summary (in number of blocks) of the current
directory and all subdirectories:
```bash
du
```
(Note: on my system the last line displays the summary of the current
directory, which is the total sum of the subdirectories as well as the
files in the
directory.  

To display disk usage summary of another directory or file:
```bash
du /path/to/directory/or/file
```


The result will show the number of _blocks_.  The most popular
alternative is to use the `-h` switch in order to display disk usage
in "human readable" format:
```bash
du -h
```
**Warning**
The `-h` switch does not play well with sorting.
Suppose that the output of a `du` command is:
```bash
2G   ./bob
1.0M ./joe
4K   ./tim
```
Piping this wih `sort -n` (numeric sort) will result in
```bash
1.0M ./joe
2G   ./bob
4K   ./tim
```
because the `sort` command orders the arithmetic values at the
beginning of the lines.

A better solution is to use:  
- `-k` to display sizes in kilobyte units;  
- `-m` to display sizes in megabyte units;  
- `-g` to display sizes in gigbyte units.  

Note that there will be rounding off.  

To get the grand total:
```bash
du -s
```

To display disk usage for all files and folders:
```bash 
du -a
```

To include the grand total disk usage of the current directory as the
last line:
```bash
du -c
```
which doesn't give any new information.  On the other hand, the `-c`
switch gives the total of a list of files, for instance:
```bash
du -c *.jpg
```
ill list all `jpg` files and at the end their total.

To restrict to subdirectories of a certain depth, say 1:
```bash
du -d1
```


# The `find` command
[Find files with timestamps between two dates](askubuntu-find-files-between-two-dates):  
```bash
find . -type f -newermt 2010-10-07 ! -newermt 2014-10-08
```

# The `w` command  
Displays who is logged in and what they are doing.  


# The `xargs` command  
Adjust the argument positionin `xargs` (from [LinuxAsk!](linuxask-adjust-argument-position-in-xargs))
```bash
echo "foo" | xargs -i echo {} "bar"
foo bar
```

# Piping commands - a miscellany.

Number of occurrences of unique values in a given column:
```bash
cat file.csv | cut -d "," -f 2 | sort | uniq -c
```


List all distinct file extensions in a directory:
```bash
find . -type f | perl -ne 'print $1 if m/\.([^.\/]+)$/' | sort -u
```
(taken from [Stackoverflow](stackoverflow-liset-file-extensions), see
alternative answers).

List the 5 most recently modified files (whose name follows a certain regex pattern):
```bash
find . -name "*cv*.tex" -print0 | xargs -0 stat -f "%m%t%Sm %N" | sort -rn | head -n 5 | cut -f2-
```
(rearranged from [unix.stackexchange])


Show the names and login times of the currently logged in users:
```bash
who | cut -c 1-8,26-38
```

Sort a text file by line length including spaces
(taken from [this stackoverflow post](stackoverflow-sort-by-line-length)):  
```bash
cat testfile | awk '{ print length, $0 }' | sort -n -s | cut -d" " -f2-
```


# References
- [Check linux disk usage of files and directories](tecmint-du) (Tecmint)
- ss64's [command line reference](ss64)
- IBM's [command page](ibm-aix-commands)
- Oliver Elliott's [100 useful unix commands](oliver-elliott-100-useful-unix-commands)
- [How to find out top directories and files in linux](tecmint-top-files-and-directories-in-linux)
- [Learn how to Find and list down recently Modified files in Linux](tutorialspoint-find-list-files)

[tecmint-du]: https://www.tecmint.com/check-linux-disk-usage-of-files-and-directories/
[ss64]: https://ss64.com/
[ibm-aix-commands]: https://www.ibm.com/support/knowledgecenter/en/ssw_aix_71/com.ibm.aix.cmds.navigation/alphabeticallistofcommands.htm
[oliver-elliott-100-useful-unix-commands]: http://oliverelliott.org/article/computing/ref_unix/[
[tecmint-top-files-and-directories-in-linux]: https://www.tecmint.com/find-top-large-directories-and-files-sizes-in-linux/
[stackoverflow-list-file-extensions]: https://stackoverflow.com/a/1842270/9472676]
[tutorialspoint-find-list-files]: https://www.tutorialspoint.com/articles/learn-how-to-find-and-list-down-recently-modified-files-in-linux
[unix-stackexchange-recently-modified-files-on-macos]: https://unix.stackexchange.com/questions/191422/how-can-i-quickly-find-the-20-most-recently-modified-files-on-mac-os-x-instead
[alternative-ls-one-file-per-line]: https://stackoverflow.com/a/3886314/9472676
[garron-ls-file-permissions]: https://www.garron.me/en/go2linux/ls-file-permissions.html
[thegeekstuff-cut-command-examples]: https://www.thegeekstuff.com/2013/06/cut-command-examples/
[gilles-ls-for-human-consumption]: https://stackoverflow.com/a/3894410/9472676
[wooledge-dont-parse-outputs-to-ls]: http://mywiki.wooledge.org/ParsingLs
[askubuntu-find-files-between-two-dates]: https://askubuntu.com/a/533797/917310
[superuser-cute-file-listing-by-extension]: https://superuser.com/a/292700
[stackoverflow-sort-by-line-length]: https://stackoverflow.com/questions/5917576/sort-a-text-file-by-line-length-including-spaces
[linuxask-adjust-argument-position-in-xargs]: echo "foo" | xargs -i echo {} "bar"

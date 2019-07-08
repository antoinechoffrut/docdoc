---
layout: post
title:  "Unix commands"
date:   2019-06-27 13:20:00 +0100
categories: unix
---

This is my own cheatsheet on unix commands.

I am on a mac, so some things may be specific to that OS.

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

# Piping commands

A miscellany.

List all distinct file extensions in a directory:
```bash
find . -type f | perl -ne 'print $1 if m/\.([^.\/]+)$/' | sort -u
```
(taken from [Stackoverflow](stackoverflow-liset-file-extensions), see
alternative answers).

# References
- [Check linux disk usage of files and directories](tecmint-du) (Tecmint)
- ss64's [command line reference](ss64)
- IBM's [command page](ibm-aix-commands)
- Oliver Elliott's [100 useful unix commands](oliver-elliott-100-useful-unix-commands)
- [How to find out top directories and files in linux](tecmint-top-files-and-directories-in-linux)

[tecmint-du]: https://www.tecmint.com/check-linux-disk-usage-of-files-and-directories/
[ss64]: https://ss64.com/
[ibm-aix-commands]: https://www.ibm.com/support/knowledgecenter/en/ssw_aix_71/com.ibm.aix.cmds.navigation/alphabeticallistofcommands.htm
[oliver-elliott-100-useful-unix-commands]: http://oliverelliott.org/article/computing/ref_unix/[
[tecmint-top-files-and-directories-in-linux]: https://www.tecmint.com/find-top-large-directories-and-files-sizes-in-linux/
[stackoverflow-list-file-extensions]: https://stackoverflow.com/a/1842270/9472676]

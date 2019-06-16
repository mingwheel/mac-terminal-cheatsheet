# Terminal commands
Cheatsheet with *basic* commands for the OS X Terminal <br><br>
[10 Essential Commands](#10-essential-commands) <br>

#### Files  
[File Operations](#file-operations) <br>
[File Compressing & Archiving](#compressing-and-archiving) <br>
[File Permissions](#file-permissions) <br>
[File Searching](#file-searching) <br>


#### System
[Disk Space](#disk-space) <br>
[Processes](#processes) <br>


## **10 Essential Commands** 
| Command | Usage | Description         | Details |
|---------|-------|---------------------|---------| 
| **`cd`** | **`cd`** `[dir]` | change directory | **`cd`** - home dir <br> **`cd \`** - root dir <br> **`cd ..`** - one level up |
| **`cp`** | **`cp`** `[original_file] [copied_file]` | copy file(s) | **`cp -R`** `[path_to_source] [path_to_dest/]` - copy *directories* recursively <br> **`cp -v`** - cause cp to be verbose |
| **`grep`** | **`grep`** `[pattern] [filename(s)]` | search for `pattern` across file(s) | **`grep -c`** - print *only* count of matching line <br> **`grep -i`** - case insensitive <br> **`grep -n`** - print matched line and line number <br>  [more](#grep) |
| **`less`** | **`less`** `[filename]` | display long text file one page at a time | *while in less* <br> `g` - go to 1st line <br>  `q` - quit less <br>  `return` - next line <br> `spacebar` - next page <br>`/word` - search *forward* for `word` <br> [more](#less) | 
| **`ls`** | **`ls`** | list all files or directories <br> common usage: **`ls -rtl`**| **`ls -a`** - list all (incl. hidden files) <br> **`ls -h`** - list with human readable file size <br> **`ls -l`** - long list <br> **`ls -r`** - reverse order <br> **`ls -t`** - sort by time modified |
| **`man`** | **`man`** `[command]` | access built-in documentation for `command` |
| **`mv`** | **`mv`** `[original_file] [new_file]` | move `original_file` to `new_file` | rename files / directories 
| **`pwd`** | **`pwd`** | display current working directory 
| **`rm`** | **`rm`** `[filename]` | remove a `file`, `set of files` or `folder full of files` | **`rm -f`** `[file]` - force removal without confirmation <br>**`rm -r`** `[dir]` - remove directory & contents |
| **`top`** | **`top`** | show `top` (cpu%) running applications and processes |

[↑ back](#terminal-commands)

## **File Operations**
| Command | Usage | Description         | Details |
|---------|-------|---------------------|---------|
| **`cat`** | **`cat`** `[filename]` | print file contents onto screen | **`cat -n`** - add line numbers | 
| **`cp`** | **`cp`** `[old] [new]` | copy file(s) | **`cp -i ...`** - interactive mode with option (e.g. overwrite existing file) <br> **`cp -R`** `[path_to_source] [path_to_dest/]` - copy *directories* recursively <br> **`cp -v`** - cause cp to be verbose |
| **`less`** | **`less`** `[filename]` | display long text file one page at a time | <a name="less"></a> *while in less* <br> `g` - go to beginning of file <br> `G` - go to end of file <br> `return` - next line <br>  *`n`*`g` - go to *`n`* line <br> `q` - quit less <br>   `spacebar` - next page <br> `b` - previous page <br>`/word` - search *forward* for `word` <br> `?word` - search *backward* for `word` <br> `v` - start *vi* editor <br> | 
| **`ln`** | **`ln`** `[source] [target]` | Hard link `target` to `source` file | **`ln -s`** - create symbolic link 
| **`mkdir`** | **`mkdir`** `[dirname]` | create directory(s) | **`mkdir "dirname with spaces"`** - create dir with spaces in `dirname` <br> **`mkdir -p parent/child{01,02,03}`** - create dir `parent` with *subdir* `child01`, `child02`, `child03`
| **`open`** | **`open`** `[filename]` | open file in default application | **`open -e file`** - opens `file` with *TextEdit* |
| **`rm`** | **`rm`** `[filename]` | remove a `file`, `set of files` or `folder full of files` | **`rm ch*`** - removes *all* files with prefix `ch` <br> **`rm -f`** `[file]` - force removal without confirmation <br>**`rm -r`** `[dir]` - remove directory & contents |
| **`touch`** | **`touch`** `[filename]` | create file(s) | **`touch /path/file`** - create file in `/path`
| **`vi`** | **`vi`** `[filename]` | open file in vi editor | [cheatsheet](http://michael.peopleofhonoronly.com/vim/) | 

[↑ back](#terminal-commands)

## **Compressing and Archiving**
| Command | Usage | Description         | Details |
|---------|-------|---------------------|---------|
| **`gzip`** | **`gzip`** `[-v] [filename(s)]` | compress file with *verbose* `.gz` output | **`gunzip`** `[filename]` - uncompress file |
| **`tar`** | **`tar`** `[-c|t|x] [flags] [files_and_dir_to_archive]` | *tape archiver* <br> **`tar -c`** create archive <br> **`tar -t`** show contents <br> **`tar -x`** extract files and dirs <br> e.g. **`tar -czvf thesis.tgz "Masters Thesis"`**| `-f` to specify archive name <br> `-v` for verbose output <br> `-z` compress with gzip |

[↑ back](#terminal-commands)

## **File Permissions**
<pre><code><b>$ ls -l</b>
drwxr-x---  9  user  user  238 Jun 15 18:49 Documents
</code></pre>
> **`d` | `rwx` | `r-x` | `---`**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**`d`** - **File Type** (`d` = directory) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**`rwx`** - **User** file permission (`r` = readable, `w` = writable, `x` = executable)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**`r-x`** - **Group** file permission <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**`---`** - **Other** file permission


<pre><code>-r--r-----  1  root  wheel  2299 Jun 15 20:33 filename
<b>$ chmod <i>a+x filename</i>
$ ls -l</b>
-r-x--x--x  1  root  wheel  2299 June 15 20:33 filename
</code></pre>
> **`chmod` | `a` | `+x` | `filename`**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**`chmod`** - Change file mode <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**`a`** - All categories (`u` = user, `g` = group, `o` = other) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**`+x`** - Add 'executable' (`-` remove, `=` exact) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**`filename`** - Also works with a `directory`

[↑ back](#terminal-commands)

## **File Searching**
| Command | Usage | Description         | Details |
|---------|-------|---------------------|---------|
| **`grep`** | **`grep`** `[pattern] [filename(s)]` | search for `pattern`* across file(s) <br> `pattern` can be a `RegEx` <br><br> *example:* <br> **`grep word *txt`** - match `word` in all `.txt` files <br> **`grep [[:digit:]]{3}A file`** - match *exactly 3 digits followed by 'A'* in file  | <a name="grep"></a>**`grep -c`** - print *only* count of matching line <br> **`grep -i`** - case insensitive <br> **`grep -l`** - print *only* matched filename(s) <br> **`grep -n`** - print matched line and line number <br>  **`grep -v`** - print *only* lines that *don't* match `pattern` <br> **`grep -A`** *`n`* - show *`n`* lines *after* matching line <br> **`grep -B`** *`n`* - show *`n`* lines *before* matching line <br> **`grep -C`** *`n`* - show *`n`* lines *before and after* matching line <br> **`grep --color=always`** - highlights `pattern` in matched lines | 
| **`find`** | **`find`** `[flags] [pathname] [expression]` | search for file(s) matching `expression` <br><br> *example:* <br> **`find $HOME -name "*.html" -print`** - find all .html files and print to screen <br> **`find . -cmin -30 -print -type f`** - find all files modified *within last 30 min*| `-ls` - output in `ls` format <br> `-regex` *`RegEx`* - match full *regular expressions* <br> `-cmin` *`time`* - true if file was modified within last *`time`* min <br> `-type` *`t`* - true if file is of type *`t`* (`d`ir and `f`ile)
 
[↑ back](#terminal-commands)

## **Disk Space**
| Command | Usage | Description         | Details |
|---------|-------|---------------------|---------|
| **`du`** | **`du`** `[file]` <br> **`du`** `[dir]` | calculate size of file(s) in dir <br> common usage: **`du -sh /Applications/*.app`** | **`du -s`** - total for dir |
| **`df`** | **`df -H`** | calculate free disk space with human readable format | **`df -i`** - show available inodes |


[↑ back](#terminal-commands)

## **Processes**

| Command | Usage | Description         | Details |
|---------|-------|---------------------|---------|
| **`ps`**| **`ps -acx`** <br><br> **`ps -ax \| grep`** `[word]`| list all processes <br><br>list all processes containing `word`  | `PID` - process id number <br> `TTY` - terminal process runs in <br> `TIME` - duration process has been running for <br> `CMD` - specific command being run |
| **`kill`** | **`kill`** `[PID]` | kill process `PID` | 

[↑ back](#terminal-commands)
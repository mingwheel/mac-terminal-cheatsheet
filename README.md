# Terminal commands

[10 Essential Commands](#10-essential-commands) <br>
#### Commands
[File handling](#file-handling) <br>
[Processes](#processes) <br>

#### Files
[File Permissions](#file-permissions) <br>
[Disk Space](#disk-space)

## **10 Essential Commands**
| Command | Usage | Description         | Details |
|---------|-------|---------------------|---------| 
| **`cd`** | **`cd`** `[dir]` | change directory | 
| **`cp`** | **`cp`** `[original_file] [copied_file]` | copy file(s) | **`cp -R`** `[path_to_source] [path_to_dest/]` - copy *directories* recursively <br> **`cp -v`** - cause cp to be verbose |
| **`grep`** | **`grep`** `[pattern] [filename(s)]` | search for `pattern` across `file(s)` |
| **`less`** | **`less`** `[filename]` | display long text file one page at a time | `g` - go to 1st line <br>  `q` - quit <br> `v` - start *vim* editor <br> `return` - next line <br> `spacebar` - next page <br>`/word` - search *forward* for `word` <br> [more](#less) | 
| **`ls`** | **`ls`** | list all files or directories <br> common usage: **`ls -rtl`**| **`ls -a`** - list all (incl. hidden files) <br> **`ls -h`** - list with human readable file size <br> **`ls -l`** - long list <br> **`ls -r`** - reverse order <br> **`ls -t`** - sort by time modified |
| **`man`** | **`man`** `[command]` | access built-in documentation for `command` |
| **`mv`** | **`mv`** `[original_file]` `[new_file]` | move `original_file` to `new_file` | rename files / directories 
| **`pwd`** | **`pwd`** | display current working directory 
| **`rm`** | **`rm`** `[filename]` | remove a `file`, `set of files` or `folder full of files` | **`rm -f`** `[file]` - force removal without confirmation <br>**`rm -r`** `[dir]` - remove directory & contents |
| **`top`** | **`top`** | show `top` (cpu%) running applications and processes |

## **File Handling**
| Command | Usage | Description         | Details |
|---------|-------|---------------------|---------|
| **`cat`** | **`cat`** `[filename]` | print file contents onto screen | **`cat -n`** - add line numbers | 
| **`less`** | **`less`** `[filename]` | display long text file one page at a time | <a name="less"></a>`g` - go to beginning of file <br> `G` - go to end of file <br> `return` - next line <br>  *`n`*`g` - go to *`n`* line <br> `q` - quit <br>   `spacebar` - next page <br> `b` - previous page <br>`/word` - search *forward* for `word` <br> `?word` - search *backward* for `word` <br> `v` - start *vim* editor <br> | 
## **Processes**

| Command | Usage | Description         | Details |
|---------|-------|---------------------|---------|
| **`ps`**| **`ps -acx`** <br><br> **`ps -ax \| grep`** `[word]`| list all processes <br><br>list all processes containing `word`  | `PID` - process id number <br> `TTY` - terminal process runs in <br> `TIME` - duration process has been running for <br> `CMD` - specific command being run |
| **`kill`** | **`kill`** `[PID]` | kill process `PID` |


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
## **Disk Space**
| Command | Usage | Description         | Details |
|---------|-------|---------------------|---------|
| **`du`** | **`du`** `[file]` <br> **`du`** `[dir]` | calculate size of `file` / files in `directory` <br> common usage: **`du -sh /Applications/*.app`** | **`du -s`** - total for dir |
| **`df`** | **`df -H`** | calculate free disk space with human readable format | **`df -i`** - show available inodes |
|
# Terminal commands

## **10 Essential Commands**
| Command | Usage | Description         | Details |
|---------|-------|---------------------|---------| 
| **`cd`** | **`cd`** `[dir]` | change directory | 
| **`cp`** | **`cp`** `[original_file] [copied_file]` | copy file(s) | `cp -R [path_to_source] [path_to_dest/]` - copy directories recursively <br> `cp -v` - cause cp to be verbose |
| **`grep`** | **`grep`** `[pattern] [filename(s)]` | search for `pattern` across `file(s)` |
| **`less`** | **`less`** `[filename]` | display long text file one page at a time | `spacebar` - next page <br> `q` - quit |
| **`ls`** | **`ls`** | list all files or directories <br><br> common usage: `ls -rtl`| `ls -a` - list all (incl. hidden files) <br> `ls -h` - list with human readable file size <br> `ls -l` - long list <br> `ls -r` - reverse order <br> `ls -t` - sort by time modified |
| **`man`** | **`man`** `[command]` | access built-in documentation for `command` |
| **`mv`** | **`mv`** `[original_file]` `[new_file]` | move `original_file` to `new_file` | rename files / directories 
| **`pwd`** | **`pwd`** | display current working directory 
| **`rm`** | **`rm`** `[filename]` | remove a `file`, `set of files` or `folder full of files` | `rm -f [file]` - force removal without confirmation <br>`rm -r [dir]` - remove directory & contents |
| **`top`** | `top` | show running applications and processes |

---
## **Processes**

| Command | Usage | Description         | Details |
|---------|-------|---------------------|---------|
| **`ps`**| **`ps -acx`** <br><br> **`ps -ax \| grep`** `[word]`| list all processes <br><br>list all processes containing `word`  | `PID` - process id number <br> `TTY` - terminal process runs in <br> `TIME` - duration process has been running for <br> `CMD` - specific command being run |
| **`kill`** | **`kill`** `[PID]` | kill process `PID` |

---
## **File Permissions**
#### Example
<pre><code><b>$ ls -l</b>
drwxr-x---  9  user  user  238  Jun 15  18:49  Documents
...
</code></pre>
**`d` | `rwx` | `r-x` | `---`**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**`d`** - File Type ("d" = directory) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**`rwx`** - Owner's file permission <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**`r-x`** - Group file permission <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**`---`** - Other file permission 
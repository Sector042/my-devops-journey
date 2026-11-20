# Linux Cheat Sheet

My personal notes from Week 1 of learning DevOps.

## Navigation

| Command | What it does |
|---|---|
| `pwd` | Show where I am |
| `cd ~` | Go to home folder |
| `cd ..` | Go up one level |
| `cd folder` | Go into a folder |
| `ls` | List files |
| `ls -l` | List with details (permissions, size, date) |
| `ls -a` | List including hidden files |

## Files and folders

| Command | What it does |
|---|---|
| `mkdir` | Make a folder |
| `touch` | Make an empty file |
| `cp` | Copy a file |
| `mv` | Move or rename a file |
| `rm` | Delete a file (permanent!) |
| `rmdir` | Delete an empty folder |

## Reading and editing

| Command | What it does |
|---|---|
| `cat` | Print the whole file |
| `less` | Scroll through a file (`q` to quit) |
| `head` | First 10 lines |
| `tail` | Last 10 lines |
| `nano` | Edit a file (`Ctrl+O` save, `Ctrl+X` exit) |

## Permissions

| Number | Symbolic | Use for |
|---|---|---|
| `644` | `-rw-r--r--` | Normal files |
| `755` | `-rwxr-xr-x` | Scripts, folders |
| `600` | `-rw-------` | Private files |

| Command | What it does |
|---|---|
| `chmod +x file` | Make a file executable |
| `chmod 644 file` | Set standard file permissions |

## Searching

| Command | What it does |
|---|---|
| `find . -type f -size 1033c` | Find files by size and type |
| `find / -user X 2>/dev/null` | Search whole system, hide errors |
| `grep "word" file` | Search inside a file for text |
| `strings file` | Pull readable text from binary |
| `sort file` | Sort lines |
| `uniq -u` | Show only unique lines |

## The pipe `|`

Sends output of one command into the next.

```bash
cat file.txt | grep "error" | sort | uniq -c
Reads as: "show the file, keep only errors, sort them, count duplicates."

Things I learned the hard way
rm has no undo. No trash can. Be careful.

cat - doesn't work — use cat ./- for files named -.

Filenames with spaces need quotes: cat "my file.txt"

Hidden files start with a dot. Use ls -a to see them.

2>/dev/null throws away error messages — useful when find gets noisy.

Never chmod 777. Ever.

# LINUX COMMANDS (BANDIT LEVELS 5–10)

### File Search – find
```bash
find .                         # Search current directory and subdirectories
find /                         # Search entire filesystem
find . -type f                 # Find regular files
find . -type d                 # Find directories
find . -size 1033c             # Find files exactly 1033 bytes
find . -user bandit7           # Find files owned by bandit7
find . -group bandit6          # Find files belonging to bandit6
find . ! -executable           # Find non-executable files
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

### File Identification – file
```bash
file filename                  # Identify file type
file ./*                       # Identify all items in current directory
```

### Reading Files
```bash
cat filename                   # Display file contents
less filename                  # View file page by page
strings filename               # Extract readable text from binary files
```

### Searching Text – grep
```bash
grep "word" filename           # Search for a word in a file
grep -i "word" filename        # Search without case sensitivity
grep -n "word" filename        # Display matching line numbers
```

### Sorting and Duplicates
```bash
sort filename                  # Sort lines alphabetically
uniq filename                  # Remove consecutive duplicate lines
uniq -u filename               # Display lines occurring once
uniq -c filename               # Count consecutive occurrences
sort filename | uniq           # Sort and remove duplicates
sort filename | uniq -u        # Find lines occurring once
```

### Base64 Encoding and Decoding
```bash
base64 filename                # Encode a file
base64 -d filename             # Decode a Base64 file
```

### Output Redirection
```bash
command > file                 # Save output (overwrite)
command >> file                # Save output (append)
command 2>/dev/null            # Discard error messages
```

### Important Symbols
```text
.       Current directory
..      Parent directory
~       Home directory
/       Root directory
*       Wildcard
!       NOT / Negation
|       Pipe (connect commands)
>       Redirect output
>>      Append output
2>      Redirect error output
```

### Useful Notes
- `c` after `-size` means bytes.
- `-type f` means regular files.
- `-type d` means directories.
- `-executable` checks executable permission.
- `! -executable` means not executable.
- `2>/dev/null` hides error messages.
- `uniq -u` finds lines occurring exactly once, provided duplicates are sorted first.
- `./filename` specifies a file in the current directory, useful when its name starts with `-`.

- grep is used to search text inside files
- very powerful

## Flags

| FLAG | RESULT                                   |
| ---- | ---------------------------------------- |
| -i   | ignore case                              |
| -r   | recursive search (crawl through dirs)    |
| -n   | show line numbers                        |
| -v   | invert matching (lines that don't match) |
| -c   | count only matches                       |
| -l   | list only filenames (not matches)        |
| -w   | match whole words only                   |
| -E   | extended regex (egrep)                   |
| -A n | show n lines after match                 |
| -B n | show n lines before match                |
| -C n | show n lines of context before and after |

```bash
# Find errors, show 3 lines of context
grep -C 3 "error" app.log

# Find IP addresses (regex)
grep -E "[0-9]+\.[0-9]+\.[0-9]+\.[0-9]+" access.log

# Exclude blank lines
grep -v "^$" file.txt

# Search recursively, ignore case, show line numbers
grep -rin "function" /path/to/code/
```

## Pipe Combo

- great way to filter out a command output

```bash
# List all running processes, then filter to show only lines containing "nginx"
ps aux | grep nginx

# Show kernel messages, filter for "usb" (case-insensitive)
dmesg | grep -i usb

# Display all user accounts, exclude lines containing "nologin"
cat /etc/passwd | grep -v nologin
```




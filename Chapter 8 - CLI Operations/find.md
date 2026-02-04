- find lists all files in cwd and all subdirs if not provided with a flag
- common flags:

| FLAG            | RESULT                                                                                    |
| --------------- | ----------------------------------------------------------------------------------------- |
| -name           | filter by name                                                                            |
| -iname          | ignore case sensitivity                                                                   |
| -type           | filter to specific files - `d` for dirs, `l` for symbolic links, `f` for regular file     |
| -exec           | run command on the search result, has to finish line with either `';'` or `\;` at the end |
| -ok             | same as -exec but prompts for permission before executing                                 |
| -maxdepth n     | limit search results to n level of depth down the directory tree                          |
| -newer filename | it will show all files newer than filename file                                           |
| not             | reverse the command function                                                              |

```bash
# Searching for files and directories named gcc
find /usr -name gcc

# Searching only for directories named gcc 
find /usr -type d -name gcc

# Searching only for regular files named gcc:  
find /usr -type f -name gcc
```

## using `-exec` flag

- using `-exec` or `-ok` flag enables operations on files matching the criteria

```bash
# find all .swp files and remove them
find -name "*.swp" -exec rm {} ';' # {} is  filename placeholder

# find all files in the folder with word "log", follow symlinks
sudo find . -type f -exec grep -H log {} \;

# find all files in cwd with size 0, verify with ls displaying size
sudo find . -size 0 -ls
```

[[grep]]
## Finding based on time or size


| FLAG     | RESULT                                                                                   |
| -------- | ---------------------------------------------------------------------------------------- |
| -ctime n | when [[inode]] metadata last changed in n days                                           |
| -atime n | search for accessed/last read in n days                                                  |
| -mtime n | modified/last written in n days                                                          |
| n        | number of days or min `n` is exact value / `+n` more than n days / `-n` less than n days |
| -cmin n  | when [[inode]] metadata last changed in n minutes                                        |
| -amin    | search for accessed/last read in n minutes                                               |
| -mmin    | modified/last written in n minutes                                                       |



```bash
# find files based on time 
find / -ctime 3
```
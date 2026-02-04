
## Absolute vs Relative Paths
### Absolute Path

- Absolute pathnames begin in the root dir (/) and follow the tree until reaches the desired dir or file
- they ALWAYS start with `/`
### Relative Path

- They start in pwd
- Never start with `/`

```bash
# Absolute path way
cd /usr/bin

# Relative path way
cd ../../usr/bin
```



## syntax

- `/////` - m,ultiple slashes are allowed but all but one are ignored by the system
	- `/////usr/bin` just means `/usr/bin`
- Relative paths are much easier to use, often used with 
	- `.` - present dir
	- `..` - parent dir
	- `~` - home dir
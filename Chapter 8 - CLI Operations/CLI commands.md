## Syntax 

- most input lines follow the schema: `<command> <options> <arguments>` but some don't have any or have additional `environment variables`
	1) `command` - name of the program or script
	2) `options` - also called switches or [[flag]]s, usually starts with one or two dashes like `-p` or `--print` in order to differentiate them from `arguments`
	3) `arguments` - represent what the command is operating on

| command  | action                                                     |
| -------- | ---------------------------------------------------------- |
| \|       | [[pipe]] - sends output of one command as input to another |
| [[grep]] | filter lines matching pattern                              |
| uniq     | remove duplicates                                          |
| [[echo]] | same as python's `print('')`                               |


# Basic CLI system operations
## Navigating the [[File system]]

| COMMAND | ACTION                                                                                        |
| ------- | --------------------------------------------------------------------------------------------- |
| cd      | change directory                                                                              |
| [[ls]]  | lis `-a` to include hidden files, `*keyword*` to filter out by keyword, can use [[wildcards]] |

### cd

- cd - change directory
- often used with flag or [[Path]] to navigate the directory

|     | flag     | action                                                                               |
| --- | -------- | ------------------------------------------------------------------------------------ |
| cd  | `~`      | change directory, `~` means home dir, `..` means , `-` means , and `$HOME` is r,  is |
|     | `..`     | parent directory                                                                     |
|     | `-`      | previous working dir                                                                 |
|     | `$HOME`  | home di                                                                              |
|     | `/`      | root dir                                                                             |
|     | [[Path]] | navigate to either absolute or relative path                                         |

### `shutdown` and `reboot` 

- requires [[sudo]] to access

| command  | flag | action                                     | example                                     |
| -------- | ---- | ------------------------------------------ | ------------------------------------------- |
| shutdown |      | shuts down system immidiately              |                                             |
| shutdown | -r   | reboots system, same as `reboot`           |                                             |
| shutdown | -h   | halts the shutdown for time specified time | shutdown -h 10 "shutting down at 10:00 CST" |

### `which` and `whereis`

- There are many locations where software packages are installed and sometimes it may be quite a feat to be able to find them
- Depending on the distro and the config of the system, they may be in:
	- `/bin` or `/usr/bin` or `/usr/local/bin`
	- `/sbin` or `/usr/sbin` or `/usr/local/sbin`
	- somewhere under `/opt`
	- or somewhere under `home/username/bin`
- Using [[CLI]] command finding specific files becomes much easier

Example:
```bash
# Find where 'diff' program is in the file system
which diff
# /usr/bin/diff

# IF which does not work, whereis is a good alternative, it looks in broader range of directories
whereis diff
# diff: /usr/bin/diff /usr/share/man/man1/diff.1.gz # this also shows location of the manual file

```

### `pushd` and `popd`

- `pushd` and `popd` manage a stack of directories - lets you jump between folders and return easily
- Think of it like browser back/forward but for directories.

```bash
# Commands:
pushd /path/to/dir   # Go to dir, remember where you were
popd                 # Go back to previous dir
dirs                 # Show the stack

# Quick swap between two dirs:
pushd /other/place   # Go there
pushd                # Swap back (no argument = swap top two)
pushd                # Swap again
```

### `tree`

- prints out a filesystem tree
- `-d` flag allows to suppress file names and only see directories
- it may have to be installed `sudo apt get tree`

```
user@PC:~/claude$ tree -d
.
├── Personas
│   └── Recipes
└── Prompts
```




---
## Managing Files

### Viewing Files

| COMMAND | ACTION                                               | FLAGS                                                                                                          |
| ------- | ---------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| cat     | print out file contents (or combine files) no scroll | `-n` show line numbers                                                                                         |
| tac     | look at file backwards                               |                                                                                                                |
| head    | print out first few lines of file                    | `-10` is default 10 lines, can be changed to `-n` of choice                                                    |
| tail    | print last few lines of file                         | `-10` - 10 lines is default if not specified                                                                   |
| less    | split print out into pages                           | `/` to search for pattern in forward direction, `?` to search in backwards direction `-N` to show line numbers |
| wc      | count lines/words/chars                              |                                                                                                                |

### File and Directory operations

| COMMAND  | ACTION                                                     | FLAGS                                                                                                                     |
| -------- | ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| touch    | create a placeholder file or edit permissions or timestamp | `-t` - set timestamp                                                                                                      |
| mkdir    | creates directory in cwd or specified path                 | `-p` if path does not exit, it will create it                                                                             |
| rmdir    | removes directory, it must be empty unless you use `-rf`   | `-rf` to remove dir with files inside (recursively- DANGEROUS) `dir*` to remove all (empty) dirs starting with name "dir" |
| mv       | rename or move file                                        |                                                                                                                           |
| rm       | remove file                                                | `-f` to force, `-i` for confirmation prompt                                                                               |
| stdin    | where input comes from (keyboard by default)               | `>`, `>>`,`<` and `&`                                                                                                     |
| stdout   | where normal output goes (screen by default)               | `>`, `>>`,`<` and `&`                                                                                                     |
| stderr   | where errors go (screen by default, but can be separated)  | `>`, `>>`,`<` and `&`                                                                                                     |
| \|       | [[pipe]]                                                   |                                                                                                                           |
| locate   | searches using indexed db of files and dirs                | use \| to filter out results                                                                                              |
| find     |                                                            |                                                                                                                           |
| updatedb | update file index (for locate), requires root              |                                                                                                                           |
| cp       | copy file or directory                                     | `cp oldpath\filename newpath\fileame`                                                                                     |
| [[du]]   | disk usage                                                 | `du -sh a*` find all files staring with letter a                                                                          |

#### Touch

- often used to set or update access, change and modify times of files (metadata)
- By default it resets timestamp to match current time
- You can also use it to create empty files as placeholders

```bash
#create empty file
touch <filename>
# set timestamp to specific value
touch -t 12091600
# -rw-r--r-- 1 babs babs 0 Dec  9  2026 myfile
```



#### Standard File Streams

- Every command has 3 default channels for data:
	- `stdin` (0) = where input comes from (keyboard by default)
	- `stdout` (1) = where normal output goes (screen by default)
	- `stderr` (2) = where errors go (screen by default, but can be separated)
- we use those so we can for example send output of a specific stream to a file

| PATTERN           | MEANING                                 |
| ----------------- | --------------------------------------- |
| command `>` file  | stdout file (overwrite mode)            |
| command `>>` file | stdout file (append mode)               |
| command `2>` file | stderr to file                          |
| command `&>` file | stdout and stderr to file               |
| command `<` file  | read stdin from file                    |
| `2>&1`            | redirect stderr to same place as stdout |
- The `&1` syntax means "wherever file descriptor 1 is going" — it's a reference, not a filename.

```bash
# The numbers matter for redirection
command > file.txt      # Redirect stdout (1) to file
command 2> file.txt     # Redirect stderr (2) to file
command &> file.txt     # Redirect both to file

# You can redirect them separately in one line
command > output.txt 2> errors.txt
#         ↑ stdout      ↑ stderr


# Input from file, output to file
sort < unsorted.txt > sorted.txt
```



#### locate and [[find]]

- `locate` searches for file with keyword using indexed database of files and directories in the system
	- run `sudo updatedb` to manually updated, usually automatically done once a day - [[updatedb]] for more info
- `find` can be passed more detailed arguments like path, and flag `-name` , it can also use wildcards and `-ls` flag to show details

#### copy

- use cp to copy files or directories
- 
---
#### [[pipe]]

#### [[wildcards]]

#### [[echo]]

## Installing software using [[CLI]]

- Different families use different [[Package Manager]] systems
- There are 2 package manager LEVELS
	- **low-level** tool (such as [[dpkg]]or [[rpm]]) takes care of the details of unpacking individual packages, running scripts, getting the software installed correctly,
	- **high-level** tool (such as [[apt]], [[dnf]] or [[zypper]] works with groups of packages, downloads packages from the vendor, and figures out dependencies
- Check [[Package Manager]] notes or following utility names for more details 

| FAMILY NAME | LOW LEVEL | HIGH LEVEL |
| ----------- | --------- | ---------- |
| [[Debian]]  | [[dpkg]]  | [[apt]]    |
| [[SUSE]]    | [[rpm]]   | [[zypper]] |
| [[Red Hat]] | [[rpm]]   | [[dnf]]    |








---
See also [[Virtual Terminal]], [[bash]], [[CLI]]
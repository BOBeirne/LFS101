- man - is short for manual, first introduced in UNIX in 70s
- [Online man pages](http://man7.org/linux/man-pages/) - man pages converted to pdfs and web pages
- Man pages are most often used source of [[Documentation]] in Linux systems
- Usually shorter than [[info]]

## man vs info

| Feature      | man                 | info                               |
| ------------ | ------------------- | ---------------------------------- |
| Format       | single page, linear | Hyperlinked sections (like a wiki) |
| Navigation   | Scroll up/down      | Jump between linked "nodes"        |
| Detail level | Often shorter       | Usually more comprehensive         |
| Age          | 70s (UNIX)          | 80s (GNU)                          

## man command usage

| COMMAND        | DESCRIPTION                                        |
| -------------- | -------------------------------------------------- |
| man topic      | Open manual page for the topic                     |
| man -k keyword | Search man for keyword (same as [[apropos]] )      |
| man -f command | short description of command (same as [[whatis]] ) |
| man -a topic   | view all chapters one after another                |
## Navigating inside man pages

| KEY            | ACTION            |
| -------------- | ----------------- |
| space / pgdown | Next page         |
| b / pgdown     | Previous page     |
| /pattern       | search forward    |
| n              | next search match |
| q              | quit man page     |
## man Sections / Chapters

- man sections use priority sections to display results in case search yields multiple results

| Section | Content                    | example                   |
| ------- | -------------------------- | ------------------------- |
| 1       | User commands              | ls, grep, man             |
| 2       | System calls (kernel)      | open(2), read(2), fork(2) |
| 3       | C Library functions        | printf(3), malloc(3)      |
| 4       | Special files (/dev)       | /dev/null, /dev/sda       |
| 5       | File formats (/etc/passwd) | /etc/passwd, /etc/fstab   |
| 6       | Games                      | fortune, cowsay           |
| 7       | Miscellaneous              | ascii, regex, signal      |
| 8       | Admin commands (root)      | mount, fdisk, useradd     |
| 9       | Kernel routines            | rarely used               |
### Search priority order

- default order configuration can be found in `/etc/man_db.conf` and it's sorted by usefulness, not numerically:
- Typical section order: 1 8 3 2 5 4 9 6 7
- Section 1 (user commands) — most frequently needed
- Section 8 (admin commands) — also very common
- Section 3 (C library) — developers need this often
- Section 6 (games) — rarely looked up, low priority
## Section subcategories

- Chapter 3 is "library functions" — but there are thousands of libraries. 
- The letter suffix groups related functions together.

| Chapter 3 | category: Library functions (main category) |
| --------- | ------------------------------------------- |
| 3         | Standard C library (libc)                   |
| 3X        | [[X Window System]]                         |
| 3p        | [[POSIX]] standard functions                |
| 3pm       | Perl modules                                |
**Example:**

```bash
whatis printf
printf (1)    - format and print data           # Chapter 1: command
printf (3)    - formatted output conversion     # Chapter 3: C library
printf (3p)   - print formatted output          # Chapter 3p: POSIX version
```

- Without suffixes, chapter 3 would have one massive unorganized list. 
- The suffix separates them for use category

| SUFFIX | TARGET AUDIENCE                        |
| ------ | -------------------------------------- |
| 3      | C programmers                          |
| 3X     | GUI/X11 programmers                    |
| 3p     | Programmers writing portable Unix code |
| 3pm    | Perl developers                        |


- `ps` - process status
- [[CLI commands]] utility, which provides info about currently running processed with PID
- to see constantly updated values, use `top`, `htop`, `atop or ,btop`
- process names between square brackets - `[processname]` - means they were started by [[Kernel]]

| FLAG | USE                                         |
| ---- | ------------------------------------------- |
| -u   | processes for specific username only        |
| -f   | shows PPID                                  |
| -l   | see niceness and priority                   |
| -ef  | full detail                                 |
| -elf | one line of info per thread (more granular) |
#### BSD ps

- from BSD variety of UNIX, where options didn't use dashes
- `ps aux` - all processes for all users, also shows % of CPU use
- `ps axo` - allows to specify attributes to filter by
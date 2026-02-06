- process is an instance of one or more related tasks (aka threads) executing on the machine
- They are not programs or commands, but a command can start multiple processes
- Failure of one process may affect others and stability of the system
- Processes use many different system resources such as CPI cycles, peripheral devices, drives, printers and displays
- [[Kernel]] is responsible for allocating a proper share of resources to each process and ensuring optimization of the system

## Types of processes

| TYPE                | DESCRIPTION                                                                                                                                                                                                                           | EXAMPLE                                    |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| Interactive Process | started by user using either a [[CLI commands]] or [[GUI]]]                                                                                                                                                                           | bash, web browser, top, slack, libreoffice |
| Batch Proces        | Automatic, scheduled process and disconnected from rerminal. Queued on [[FIFO]] basis                                                                                                                                                 | updatedb, idconfig                         |
| Daemons             | Server processes running continuously. Launched at start of the system and waiting for user or system request. Their names usually end with letter `d` for daemon                                                                     | httpd, sshd. libvirtd, cupsd               |
| Threads             | Lightweight process. Small tasks running under a main process, sharing it's memory and other resources. scheduled and run by OS on individual basis. Threads can end without terminating the process and process can create new ones. | dconf-service, gnome-terminal-server       |
| Kernel Threads      | Tasks run by kernel to which user has not much control over. Many perform resource balancing control like moving thread from one cpu to another or making sure I/O operations on disk are completed                                   | kthreadd, migration, ksoftrqd              |

## Process scheduling

- [[Kernel]]'s critical function is called a [[scheduler]]. 
- It's job is to constantly shift processes on and off cpu, sharing time according to relative priority and checking how much time is needed vs how much time has already been granted to the task.
- When process is `running` - it means it's either currently executing instructions on cpu or waiting to be granted time resource so it can execute (run queue)
	- On computers with multiple CPU / cores - each has their own queue

## Process and thread IDs

- PID - Linux assigns a unique ID number for each process. that number is used to track it's usage of CPU, time, memory etc
- New PIDs are usually assigned in the ascending order
- PID 1 is usually [[init]] process as it's the first one to run during [[BOOT]]

| NAME | ID TYPE           | DESCRIPTION                                                                                                                                           |
| ---- | ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| PID  | Process ID        | Unique process ID number                                                                                                                              |
| PPID | Parent Process ID | Parent Process that started this process, if the Parent terminates PPID will refer to adoptive parent (on moder kernels it's `kthreadd` with  PPID 2) |
| TID  | Thread ID         | Thread Id number, for multi thread process each thread shares same PID but TID will be unique                                                         |
|      |                   |                                                                                                                                                       |
## Terminating a process

- You can only kill your own processes, the ones belonging to other users are unreachable, unless you are [[root]]
- To terminate a process use `kill -SIGKILL <PID>` or `kill -9 <PID>`

## [[Users and Groups]] IDs


|      | ID TYPE       | ROLE                                      |
| ---- | ------------- | ----------------------------------------- |
| RUID | REAL USER ID  | Identifies who started the process        |
| RGID | REAL GROUP ID | Identifies group that started the process |

## Process priorities

- Each CPU can accommodate one task at a time, 
- Some of them are more important than others so they get higher priority to CPU resources
- the priority value is called a [[nice value]] aka niceness of the process
- The lower the nice value, the higher the priority. `-20` is highest priority, while `+19` is lowest
- While it may sound confusing, it dates back to [[UNIX]] times
- there is an optional `real-time` priority that can be assigned to time-sensitive tasks, it's just very high priority and it's not `hard real-time`. They are different concepts


### changing [[nice value]]

- Increasing / lower the value will also affect any future process created by the affected process
- Example: if you change niceness of `bash` to +5 all tasks created from that bash console will also have increased niceness!

| COMMAND                      |                                                    |
| ---------------------------- | -------------------------------------------------- |
| ps                           | basic process list                                 |
| ps lf                        | more detailed process list                         |
| renice `+` `<value>` `<PID>` | increase niceness of the process by selected value |
| renice `-` `<value>` `<PID>` | lower the niceness, required sudo                  |

## [[GUI]] process list

- To access GUI version of ps use `gnome-system-monitor`
- It's pretty much an equivalent of Window's system Task manager

## [[Load average]]s

- Load Average - the load number for a given period of time
	- Actively running Processes on CPU
	- Runnable but waiting in queue
	- Sleeping - waiting for some kidn of resource, like I/O to become available
	- Uninterruptible sleepers - cannot be awakened easily
- To see load average use `w` `top` or `uptime`


## Background and Foreground Processes

- When you run a command, the terminal is blocked until it finishes (foreground)
- The solution to that problem is running long tasks in the background

| COMMAND   | ACTION                              | Flags              |
| --------- | ----------------------------------- | ------------------ |
| command & | Start command in the background     |                    |
| jobs      | list background & stopped jobs      | `-l` provides PID  |
| fg        | bring most recent job to foreground |                    |
| fg %n     | bring job n to foreground           |                    |
| bg        | resume stopped job in background    |                    |
| bg %n     | resume n job in the background      |                    |
| CTRL-Z    | Suspend a running job               |                    |
| CTRL-C    | Kill foreground job                 |                    |
### fg & bg Workflow Examples

```bash
# Start a job in background:
updatedb &
#[1] 12345              # Job number [1], PID 12345
#$                      # Terminal free immediately

# Suspend then background:
find / -name "*.conf"     # Running, terminal blocked
^Z                          # Press Ctrl+Z
#[1]+  Stopped  find / -name "*.conf"

bg                        # Resume it in background
#[1]+ find / -name "*.conf" &
#$                           # Terminal free now

# Bring back to foreground:
fg                        # Brings last background job to foreground

# Managing Multiple Jobs
jobs                      # List all background/stopped jobs
#[1]-  Running    updatedb &
#[2]+  Stopped    vim file.txt

fg %1                     # Bring job 1 to foreground
bg %2                     # Resume job 2 in background
kill %1                   # Kill job 1
```


## Listing processes
### [[ps]]

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
#### Process Tree

- You can see process tree by using command `pstree`
- just like file system `tree` it shows processes in a form of a tree diagram showing relationship between tasks and their parent processes
- Duplicates of process are not displayed
- task names are displayed in curly brackets `{task}`
### [[top]]

- Use it to see constantly updated values by typing `top` for updates every 2 sec by default
- exit by pressing `q`
- `top`, `htop`, `atop or ,btop` are different system monitor utilities

#### Navigating [[top]]

| KEY        | WHAT IT DOES                                          |
| ---------- | ----------------------------------------------------- |
| `h` or `?` | Display available interactions                        |
| t          | Toggle summary (rows 2 & 3)                           |
| m          | Toggle memory info (rows 4 & 5)                       |
| l          | Toggle CPU info view between totals or per core / CPU |
| d          | Set display update interval                           |
| A          | Sort by top resource drainers                         |
| r          | Change priority of specific processes (Renice)        |
| k          | Kill specific process                                 |
| f          | `top` configuration screen                            |
| o          | toggle between sort orders                            |

## [[System Monitor]]

- GUI, interactive tool very similar to Window's task manager

## Scheduling processes

### [[at]]

- at can be used to schedule any non-interactive command at a specified time
- example:
1) `> at now + 2 days` 
2) input commands `> echo "it works!" > /tmp/test.txt`
3) `CTRL-D` to exit and schedule

### [[cron]]

- `cron` — Schedule Recurring Tasks daemon
- Runs commands automatically at specified times/intervals.
- runs with minimal environment — use full paths for commands (`/usr/bin/python3` not just python3).
- used in UNIX-like operating systems for decades
- Assumes machine is always running
### [[anacron]]

- Successor of [[cron]]
- Unlike cron, if machine is is powered off, anacron will queue jobs and run them in staggered manner when system is up and running again
- Config file location: `etc/anacrontab`

### [[sleep]]

- you can use `sleep` command to make application wait until necessary requirements are met so it can complete it's work or to simply run periodically to deal with queued jobs

#### usage 

 `sleep NUMBER[SUFFIX]`

| SUFFIX | MEANING           |
| ------ | ----------------- |
| s      | seconds (default) |
| m      | minutes           |
| h      | hours             |
| d      | days              |
#### sleep vs [[at]]


| UTILITY | DIFFERENCE                         |
| ------- | ---------------------------------- |
| at      | starts execution at specific time  |
| sleep   | delays execution for specific time |



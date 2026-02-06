- Use it to see constantly updated values by typing `top` for updates every 2 sec by default
- exit by pressing `q`
- `top`, `htop`, `atop or ,btop` are different system monitor utilities

| tool | Visual Style      | Use case                               | Pre-installed |
| ---- | ----------------- | -------------------------------------- | ------------- |
| top  | text              | Quick check                            | YES           |
| htop | colors, bars      | Daily use                              | NO            |
| atop | detailed text     | historical logging, disk / network I/O | NO            |
| btop | modern and pretty | Visuals                                | NO            |

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

#### understanding output

| LINE | WHAT IT SHOWS                                                                                                                                                                                                          |
| ---- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1    | uptime, logged in users, load average                                                                                                                                                                                  |
| 2    | total nr of processes, running, sleeping, stopped and zombie processes                                                                                                                                                 |
| 3    | CPU usage stats split per users (us) and kernel (sy) in %, nicenes (ni), idle mode (id), waiting jobs for i/o (wa) , hardware interrupts (hi), software interrupts (si), steal time (st) - st is usually used with vms |
| 4    | RAM - total, used and free                                                                                                                                                                                             |
| 5    | Swap space - total, used and free - can be increased                                                                                                                                                                   |
| 6+   | Process list - PID, process owner (USER), Priority (PR), nice Values (NI), MEMORY - VIRTUAL (VIRT), PHYSICAL (RES), SHARED (SHR), status (s) , %CPU and %MEM used, execution time (TIME+), Command (COMMAND)           |


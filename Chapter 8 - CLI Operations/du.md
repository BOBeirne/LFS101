- [[CLI commands]] for disk usage utility
- common flag is `-sh`
	- `-s` - summary, show only the total
	- `-h` - Human-readable, show sizes in KB, MB and GiB instead of bytes

```bash
# Without -s (lists every subdirectory)
du -h /var/log
4.0K    /var/log/apt
12M     /var/log/journal
2.1M    /var/log/syslog
...

# With -s (just the total)
du -sh /var/log
14M     /var/log
```


## Common usage

| COMMAND              | RESULT                                 |
| -------------------- | -------------------------------------- |
| `du -sh .`           | Total size of current directory        |
| `du -sh *`           | Size of each item in current directory |
| `du -sh ~/Downloads` | Total size of Downloads folde          |

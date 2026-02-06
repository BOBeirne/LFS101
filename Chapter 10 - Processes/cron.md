- `cron` — Schedule Recurring Tasks daemon
- Runs commands automatically at specified times/intervals.
- runs with minimal environment — use full paths for commands (`/usr/bin/python3` not just python3).

## components

- cron uses a configuration file called **/etc/crontab** (cron table), which contains the various shell commands that need to be run at the properly scheduled times
- There are system-wide and user specific cron tabs
- Each line of crontab file represents a job and is composed of CRON expressions, followed by shell command to execute

## Cron navigation

| COMMAND    | USAGE                                                    |
| ---------- | -------------------------------------------------------- |
| cron       | The daemon (background service) that runs scheduled jobs |
| crontab    | The file containing your scheduled jobs                  |
| crontab -e | crontab editor                                           |
| crontab -l | List your current jobs                                   |
| crontab -r | Remove all your jobs                                     |

## CRONTAB

- each tab in crontab has 6 fields

| ID  | FIELD | VALUES     | DESCRIPTION                   |
| --- | ----- | ---------- | ----------------------------- |
| 1   | MIN   | 0 - 59 / * | Minute                        |
| 2   | HOUR  | 0 - 23 / * | Hour                          |
| 3   | DOM   | 1 - 31 / * | Day of the month              |
| 4   | MON   | 1 - 12 / * | Month                         |
| 5   | DOW   | 0 - 6 / *  | Day of the week ( 0 = Sunday) |
| 6   | CMD   | Command    | Any command                   |

## cron logs

```bash
# Cron logs (check if job ran)
grep CRON /var/log/syslog      # Debian/Ubuntu
journalctl -u crond            # RHEL/openSUSE
```

## Examples:

| CRONTAB                                       | INTERPRETATION                             |
| --------------------------------------------- | ------------------------------------------ |
| * * * * /usr/local/bin/execute/this/script.sh | schedule script.sh to execute every minute |
| 30 08 10 06 * /home/sysadmin/full-backup      | Full backup @ 8:10AM on the 10th of June   |



[[Processes]]
[[anacron]]
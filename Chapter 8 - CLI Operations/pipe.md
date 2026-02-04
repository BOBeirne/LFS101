- `|` is the pipe - sends output of one command as input to another, called `pipeline`
- pipe allows us to chain multiple [[CLI commands]] in one line saving time


```bash
command1 | command2 | command3
```

- pipe allows us to operate on files in memory without having to save them on the hard drive
- there is no need to save output in (temporary) files between the stages in the pipeline

```bash
# Without pipe
ls -la > temp.txt # export list of files to txt file
grep test temp.txt # search for keyword 'test' in text file
rm temp.txt # remove text file after operation

# With pipe
ls -la | grep test # filter out output list of files to show only ones with 'test' in their name
```



  Common examples:

```bash
ls -la | grep test # List files, then search for "test"

ps aux | grep python # Show processes, find python ones

cat file.txt | wc -l # Count lines in a file

# you can chain multiple pipes too
cat /var/log/syslog | grep error | head -20 # show only last 20 errors from the log
```


 Common commands used with pipes:

| Command | Purpose                                 |
| ------- | --------------------------------------- |
| grep    | Filter lines matching pattern           |
| head -N | Show first N lines                      |
| tail -N | Show last N lines                       |
| wc      | Count lines/words/chars                 |
| sort    | Sort output                             |
| uniq    | Remove duplicates                       |
| less    | break long output into scrollable pages |


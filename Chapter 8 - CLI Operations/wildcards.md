- You can search for a filename containing specific characters using wildcards
- handy when using `ls` opr `find` [[CLI commands]]

| WILDCARD | RESULT                                                              | USAGE           |
| -------- | ------------------------------------------------------------------- | --------------- |
| ?        | match any single character                                          | `ls ba?.out`    |
| *        | match any string of characters                                      | `ls *.out`      |
| `[set]`  | matches any of the characters between the brackets                  | `du -sh a[p-z]` |
| `[!set]` | matches any character not mentioned in the set between the brackets |                 |
| "file"   | do not look in current directory to fill the results                |                 |

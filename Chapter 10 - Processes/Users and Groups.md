- Linux is capable of supporting multiple users being logged in simultaneously
- Each of them can run their own set of [[Processes]]es
- OS identifies who started each process by `RUID` - Real User ID

|      | ID TYPE            | ROLE                                                                                  |
| ---- | ------------------ | ------------------------------------------------------------------------------------- |
| RUID | REAL USER ID       | Identifies who started the process                                                    |
| EUID | EFFECTIVE USER ID  | Determines access rights of the user, it may or may not have same ID as RUID          |
| RGID | REAL GROUP ID      | Identifies group that started the process                                             |
| EGID | EFFECTIVE GROUP ID | Determines access rights of the groups. each user can be a member of multiple groups. |

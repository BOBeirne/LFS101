- Load Average - the load number for a given period of time
	- Actively running [[Processes]] on CPU
	- Runnable but waiting in queue
	- Sleeping - waiting for some kidn of resource, like I/O to become available
	- Uninterruptible sleepers - cannot be awakened easily
- To see load average use `w` `top` or `uptime`

### Interpreting load average

#### 1 CPU

- Assuming system has 1 CPU, the 3 load average numbers are interpreted as follows

| Load average  | 0.45        | 0.17      | 0.12       |
| ------------- | ----------- | --------- | ---------- |
| Utilization % | 45%         | 17%       | 12%        |
| Time frame    | last minute | last 5min | last 15min |

- If any of those numbers was `1` it would mean `100%` CPU utilization
- If it was over 1 it would mean that it was over-utilized - more processes needing CPU than available resources

#### Multiple-core CPU

- For multiple core or multiple-CPU setup, the averages need to be divided by core numbers
- Example: 4 core CPU, Averages: 0.8, 4.0, 2.0

| Load average  | 0.8         | 4.0       | 2.0        |
| ------------- | ----------- | --------- | ---------- |
| Utilization % | 20%         | 100%      | 50%        |
| Time frame    | last minute | last 5min | last 15min |

## Checking CPU cores

| Command | RESULT            |
| ------- | ----------------- |
| nproc   | CPU count         |
| lscpu   | CPU detailed info |

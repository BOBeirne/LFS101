
- `echo` - prints text to the terminal (or to a file)
- essentially a Linux's print statement

Example of use in scripts:
```bash
#!/bin/bash
echo "Starting backup..."
# do backup
echo "Done!"
```

Echo vs printf:
```bash
echo "Hello"           # Simple, good enough usually
printf "Hello\n"       # More control, portable across shells
```
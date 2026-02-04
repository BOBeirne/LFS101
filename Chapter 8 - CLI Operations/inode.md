- inode is a file's unique ID on the disk
- the filename is just a label pointing to it

## Information stored by inode

- File Size
- Owner & permissions
- timestamps (metadata)
- location of data blocks on the disk itself
- count of links ([[Hard link]] and [[Soft link]]) - `rm` decreases link count; data only deleted when count = 0

- Inode does NOT store the filename (that's store in the directory)

## How to see inode ID

```bash
ls -i file.txt
# 12345 file.txt
#   ↑
#  inode number

ls -li         # Long listing with inodes
stat file.txt  # Detailed inode info
```


##  Why it matters:

  - Hard links work because multiple filenames can point to one inode
  - Renaming/moving a file doesn't change the inode (just updates directory)
  - `rm` decreases link count. Data is only deleted when count = 0

 - A hard link is another name pointing to the same file data on disk.

## Creating a Hard Link

```bash
# Create a hard link:
ln file1 file2    # file2 is now another name for file1's data
```

### What actually happens:

  file1  ──┐
         ├──→ [inode 12345] ──→ actual data on disk
  file2 ──┘

Both names point to the same [[inode]] (file's unique ID). It's not a copy - it's the same file with two names.

## How to verify

```bash
Verify with ls -li:
ls -li file1 file2
# 12345 -rw-r--r-- 2 user user 100 Jan 31 file1
# 12345 -rw-r--r-- 2 user user 100 Jan 31 file2
#   ↑                ↑
#   same inode       link count = 2
```


## Key behaviours:

| Action            | Result                                                   |
| ----------------- | -------------------------------------------------------- |
| Edit file1        | file2 also changes (same data)                           |
| Delete file1      | file2 still works (data remains until all links deleted) |
| Delete both files | Data removed from disk                                   |

### Gotchas:

- Delete one link → other still exists (can cause confusion)
- Some editors may break the link when saving (creates new file instead of editing in place), 
	- vi and gedit are considered safe
- Only works within the **same filesystem**

### When to use:

- Multiple references to same file without duplicating data
- Backup strategies
- **Rarely needed day-to-day**
## Hard vs [[Soft link]]s
- Hard link = same inode, same data
- [[Soft link]] = shortcut/pointer to a path
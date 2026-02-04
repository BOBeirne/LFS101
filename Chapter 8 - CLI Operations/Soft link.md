- Soft (or Symbolic) links are created just like [[Hard link]] but with the **-s** option
- Symbolic links take no extra space on the filesystem (unless their names are very long)
- file 3 will have a different [[inode]] number

```bash
# create symbolic link
ln -s file1 file3

# verify
ls -li file1 file3

```

## Use cases

- An easy way to create a shortcut from your home directory to long pathnames is to create a symbolic link
- Unlike [[Hard link]]s, symbolic links can point to objects even on different file systems / partitions / media (which may not even exist at the moment)
	- If the object where link points to is not available, it will create a `dangling link`
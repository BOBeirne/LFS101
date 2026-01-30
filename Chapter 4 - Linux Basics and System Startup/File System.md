- File System is a method for storing and organizing arbitrary collections of data in human-usable form
- during [[BOOT]], a file system contains critical files and device drivers required to start the system
- User data -> File System (method) -> raw partition -> HDD

## File system types:
### Conventional Disk:

Windows:
- NTFS
- exFAT

Linux:
- ext3 
- ext4
- XFS
- Btrfs
### Flash Storage

Linux:
- ubifs
- jffs2
- yaffs

Windows: 
- exfat

Cross-platform (Wind, Linux and macOS)
- vfat (FAT32)
### Database

- SQL

### Network

Linux:
- NFS

Windows:
- CIFS
- SMB (shares)
### Special-Purpose

- procfs - process info `/proc`
- sysfs - device/driver info `/sys`
- tmpfs - RAM-based temp storage 
- squashfs - live USB compressed read only
- debugfs - kernel debugging
- fuse - userspace filesystems


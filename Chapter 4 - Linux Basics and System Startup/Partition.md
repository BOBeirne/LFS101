


- Partition is a dedicated subsection of physical storage (fixed area to be treated as a whole)
- [[File System]] resides within a partition
- In some cases, if using [[symbolic links]] a [[File System]] can span more than one partition

| Concept              | Windows                       | Linux                                |
| -------------------- | ----------------------------- | ------------------------------------ |
| Partition            | Disk1, Disk2                  | /dev/sda1, /dev/sdb1                 |
| [[File System]] type | NTFS, FAT32                   | ext4, XFS, Btrfs                     |
| How to access        | Drive letter ( `C:` and `D:`) | Mount Point (`/home` and `/mnt/usb`) |
| Root of the FS       | `C:\`                         | `/`                                  |

## Linux partitions

- It is best to choose how many partitions you need at the point of the installation
- It can be changed later but it's easier to do while installing OS

Default Linux HDD partition (sda) layout
- / (sda1)
- home (sda2)
- var (sda3)
- swap (sda4)

### Terminal Commands

- Use command `df -h` to see how much space is being used by each partition
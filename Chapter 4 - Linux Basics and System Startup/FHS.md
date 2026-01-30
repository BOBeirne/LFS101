# Filesystem Hierarchy Standard

- [Official Docs PDF](https://refspecs.linuxfoundation.org/FHS_3.0/fhs-3.0.pdf) - LSB Workgroup
- Ensures that users, admins and devops can move between distros without having to re-learn every OS structure

## /

- Linux uses `/` to separate paths (like [[UNIX]]), for comparison Windows uses `\`
- It does not use drive letters (unlike windows), partitions are mounted as directories in single filesystem
- Directories are case-sensitive so /BOOT/ , /Boot/ and /boot/ are different directories
- removable media can be found in `/run/media/username/disklabel` (or in `/media/` in older distros)


## Inside the ROOT directory


| DIRECTORY | DESCRIPTION                                                       |
| --------- | ----------------------------------------------------------------- |
| /bin/     | essential command binaries                                        |
| /boot/    | [[BOOT Loader]] static files                                      |
| /dev/     | Device files                                                      |
| /etc/     | Host-specific sys config                                          |
| /home/    | USER home directories                                             |
| /lib/     | Essential shared libraries and kernel modules                     |
| /media/   | mount point - removable media                                     |
| /mnt/     | mount point - temp filesystem                                     |
| /opt/     | optional app software packages                                    |
| /run/     | Data relevant to running processes                                |
| /sbin/    | Essential system binaries                                         |
| /srv/     | data for services                                                 |
| /tmp/     | temp files                                                        |
| /usr/     | secondary hierarchy - bin / include / lib / local / stbin / share |
| /var/     | Variable data                                                     |
| /root/    | ROOT user home directory                                          |
| /proc/    | virtual FS documenting kernel and process status as txt files     |

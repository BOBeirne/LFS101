
## [[Kernel]]

- Brain of the OS
- Glue between hardware and apps
	- `Hardware` <-> `kernel` <-> `Applications`
- All kernels can be found at [kernel.org](https://kernel.org)

## [[Linux Distributions]]

- collection of software making up a Linux-based OS
- Ubuntu, CentOS, SLES, OpenSUSE etc

## [[Bootloader]]

- program that boots the OS for eg. GRUB or ISOLINUX
- `init file` <-> `Kernel` <-> `Boot Loader`

## [[Service]]

- Program that runs as a background process
- Examples: 
	- ftpd - FTP server
	- httpd - http server
	- named - name server
	- dhcpd - DHCP server
- `d` stands for daemon

## [[File System]]

- method for storing and organizing files
- User data -> File System (method) -> raw partition -> HDD
- Examples:
	- ext3 /ext4
	- FAT
	- XFS
	- NTFS
	- Btrfs

## [[X Window System]]

- Standard toolkit provided with Linux allowing creation of GUI for nearly all Linux systems
- GUI - Graphical User Interface on top of OS
	- Desktop
		- [[KDE]]
		- [[Gnome]]
		- [[XFCE]]
		- Fluxbox
	- Window Manager
	- x Window System / X11
- Console
	- Shell: CLI / tcsh / zsh
	- Kernel
	- Hardware
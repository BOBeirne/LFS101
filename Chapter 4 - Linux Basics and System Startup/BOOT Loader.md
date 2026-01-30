- Kicks in after POST

- Loader location depends if you're using BIOS or UEFI
- If using [[BIOS]] - loader is located in [[MBR]] - the 1st sector of the disk
- if using [[UEFI]] - loader is located in [[EFI]] partition
- IT is responsible for loadingthe [[Kernel]] Image and Initial RAM disk or [[File System]] into memory

1) Shows menu (pick OS or kernel version)
2) Loads kernel into memory
3) Loads initramfs (mini filesystem with drivers needed to boot

## Stages

- Boot Loader has **2 distinct stages**:

#### Stage 1
- [[BIOS]]: 
	- BOOT loader examines partition table and finds a bootable partition
	- Then searches for second stage boot loader (e.g. [[GRUB]] and loads it into [[RAM]])
- UEFI
	- [[UEFI Firmware]] reads Boot Manager data and check which boot loader application to launch (e.g. [[GRUB]] ) and where in [[EFI]] is it located
	- Loads GRUB
#### Stage 2

- 2nd Stage loader is located in `/boot`
	1) Displays a splash screen 
	2) Allows a choice [[OS]] / [[Kernel]] to boot
	3) Loads the choice into [[RAM]] and passes control to it
	4) Uncompresses (usually compressed) Kernel
	5) Checks and analyses the hardware and any drivers needing to be initialized built into [[Kernel]]
### Types

- There are multiple types of boot loaders for Linux
- Most common Linux boot loader is [[GRUB]]
- ISOLINUX - for booting from removable media
- DAS U-Boot - for booting from embedded devices or appliances
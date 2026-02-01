- BOOT Process / sequence - It's a **procedure** for initializing system
- Everything that happens from the moment power is introduced to the computer until when the UI is fully operational for the user to interact with
- Knowing how booting works could help with troubleshooting system issues or tailoring system performance to your needs.
- It can be quite technical
- There are 2 types: [[BIOS]] / [[UEFI]] BOOT types, in general it follows:

1) Power ON - electricity is introduced
2) [[BIOS]] / [[UEFI]] 
3) [[POST]]
4) [[CMOS]]
5) [[MBR]] / [[EFI]]
6) [[BOOT Loader]] (e.g. GRUB) 
7) [[Kernel]] + Initial [[RAM]] disk - [[initramfs]]
8) /sbin/[[init]] (parent process)
9) command [[shell]] using getty
10) [[GUI]] ([[X Window System]]/ [[wayland]])


### BOOT alternatives 

- [[SysVinit]] - old method of sequential stages, where each had to stop before next one ran.
	- It was moved away from since it could not take advantage of multiple processors (parallel processing), a lot of scripts were hard to keep compatible and it was slow.
- Upstart - First alternative to SysVinit Developed by [[Ubuntu]] and first released in 2006
	- Fedora 9 - adopted in 2008
	- RHEL 6
- [[systemd]] - It was seen as quite controversial but has been adopted by all major distributions as it takes advantage of aggressive parallelization techniques, which allows multiple services to be initiated at the same time 
	-  First adopted by Fedora in 2011. 
	- adopted in RHEL in version 7 and SUSE
	- Replaced in Ubuntu 16.04
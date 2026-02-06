- UDEV - user device system
- Responsible for figuring out which devices are present, locating their drivers and loading them during the [[initramfs]] [[BOOT]] stage
- Modern Linux uses `udev` to create [[device node]]s dynamically when hardware is detected:

1) USB drive plugged in 
2) [[Kernel]] detects it
3) `udev` creates `/dev/sdb`
4) `udev` may also create friendly link: `/dev/disk/by-id/usb-SanDisk...`
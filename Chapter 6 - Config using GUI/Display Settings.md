- Access the settings panel by using one of the following options:
	1) `Settings` -> `displays`
	2) `Settings` -> `devices` -> `displays`
	3) `Right-Click` on the desktop


## GPU drivers

- If you use a proprietary GPU card (NVIDIA or AMD) you may have a separate access panel for that card
- It may have more config options but it may also be more complicated
- it is recommended to focus on Display settings panel, rather than proprietary programs


## X window

- systems using [[X Window System]] use `xorg` server that provides the [[GUI]]
- config file is located in `/etc/X11/xorg.conf` IF it exists
- On newer distros this config file doesn't exist, unless there is a specific circumstance, such as less common GPU [[drivers]] being used

## Changing resolution

- OS usually figures out the best resolution itself, but it can be changed in settings
- You can change them in `Displays` panel -> change resolution -> apply -> confirm
- IF you don't confirm, OS will switch back to the old resolution after a while
```bash
#find out the current screen resolution
username:/tmp> $ xdpyinfo | grep dim
```
## Multiple screens

- Multiple displays are usually detected and set up automatically as one big screen spanning multiple monitors (extended on windows)
- You can change this setting to mirrored mode
- You can also config each screen's resolution separately
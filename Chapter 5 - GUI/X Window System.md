- [[GUI]] for Linux
- Sometimes just called `X` or `X11`
- Created in 80s
- Legacy but still works
- Has weak security (any app can see other windows)
- It's used as default in older distros, otherwise used as a fallback
- has been mostly replaced by [[Wayland]]

## Xorg

- systems using [[X Window System]] use `xorg` server that provides the [[GUI]]
- xorg config file is located in `/etc/X11/xorg.conf` IF it exists
- On newer distros this config file doesn't exist, unless there is a specific circumstance, such as less common GPU [[drivers]] being used
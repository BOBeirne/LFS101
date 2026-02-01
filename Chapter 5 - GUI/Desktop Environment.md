

- Components below come packaged together ([[GNOME]], [[KDE]], [[XFCE]]) so everything works seamlessly.

| Component name  |                                                                |
| --------------- | -------------------------------------------------------------- |
| Session Manager | Starts/maintains your desktop session, remembers open apps     |
| Window Manager  | Controls windows - move, resize, title bars, minimize/maximize |
| Utilities       | Apps that come bundled (file manager, settings, terminal)      |

## Find out what [[GUI]] is being used

```bash
# display manager in use
systemctl status display-manager

# search for what is running
ps aux | grep -E 'gnome-shell|plasmashell|xfce|cinnamon|mate'
```

## Starting GUI manually 

if you boot to terminal):


```bash
# Option 1: Start X directly (no login screen, already logged in terminal)
startx

# Option 2: Start display manager (shows login screen)
sudo systemctl start gdm    # GNOME
sudo systemctl start sddm   # KDE
sudo systemctl start lightdm # XFCE/others
```

## Make GUI default on boot:
```bash
sudo systemctl set-default graphical.target
```


## Installing GUI

If distro comes without GUI, you can install it after the base OS installation
### [[GNOME]]

The default display manager for GNOME is called **gdm**

```bash
# GNOME:
sudo zypper install -t pattern gnome
```
### [[KDE]]

KDE Plasma - [[openSUSE]]'s default, best integration, familiar Windows-like layout

```bash
# KDE Plasma:
sudo zypper install -t pattern kde
```

### [[XFCE]]

 XFCE if the VM or hardware is slow/low resources
 
```bash
# XFCE (lightweight):
sudo zypper install -t pattern xfce
```

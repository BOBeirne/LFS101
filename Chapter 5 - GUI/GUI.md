- Loading GUI is one of the last [[BOOT]] processes.
- It used to be known as [[X Window System]] or simply called X
- X11 is the old display system from the 80s. 
- [[Wayland]] is the modern replacement with better security (Fedora, THEL 8+, Ubuntu 22.04+)
### Types

- There are 3 distinct types of Linux GUI
1) [[GNOME]]
	1) [[Unity]] (based on GNOME)
2) [[KDE]]
3) [[XFCE]]
4) [[LXDE]]

## Components

| Component Name          | What it does                                                              |
| ----------------------- | ------------------------------------------------------------------------- |
| Display Manager         | Handles login screen, starts your desktop ([[GDM]], [[SDDM]], [[LightDM]] |
| Display Server          | Draws windows, handles mouse/keyboard input                               |
| [[Desktop Environment]] | The actual UI you interact with ([[GNOME]], [[KDE]], [[XFCE]])            |

## Login Screen

- Very similar look to Windows - select user and type password in
- When you select user -> gear icon you get the option to change GUI type 
- To log out you click on power icon in the upper-right corner -> username -> switch / log out

## Lock

- You can lock screen using combination of `SUPERKEY`+`L` or `SUPERKEY` + `ESC` 
- `SUPERKEY` is also known as `WINDOWS KEY`

## Switching users

- Switching users works just like on Windows


## Switching off or restarting

- To switch system off you simply go to power icon in top-right corner -> `power off`
	- Restart
	- Shut down
	- cancel
- or you can use bash command `shutdown` or `reboot`


## Suspending & waking up

- called `suspend mode` , works just like windows's `sleep mode`
- click on `power icon` -> `hold` it until it shows `pause icon` -> press `pause icon`
- to `wake up` simply press mouse button or any other key


## Background

To change a background...
1) click on background -> change background -> background

## Applications

- Linux comes pre-installed with many applications helping you complete basic tasks and more are available to installation
- Installed apps can be found in different locations
	- Applications menu - upper-Left corner
	- Activities menu - upper-Left corner
	- `Dash` button- upper-Left corner
	- KDE & some others - lower-left corner button
- to set default apps go to
	1) settings
	2) Default Applications OR Details -> default apps

## File Manager

- **Default File Manager** for Linux is [[Nautilus]]
- It usually has a **file cabinet icon**
- By default it opens `/home/` directory of a user (`/home/user/`) - every user has one
- You can change view type in top-Left corner
- **hidden files** start with a dot `.` - to enable hidden files view:
	- sometimes option is called `show system files` even though it's not all just system files
	- Press `CTRL-H`
- You can **search for files** using lens icon box or using shortcut `CTRL-F`
	- To search in **specific directory** - press `CRTL-L`
	- You can refine search using:
		- filter to sort by location, file type and more
		- use `+` button to add additional criteria
		- use `reload` icon to reload search results

## Text editing

- default text editor in [[GNOME]] is [[gedit]]
- general-purpose editor with additional features like spell-check, highlight, file listings and stats

## Deleting files

- Deleting files will move them to `.local/share/Trash/files` under user's `/home/` dir
- There are multiple ways of deleting files in [[Nautilus]]
	1) Select files for deletion
	2) press `CTRL-DEL` or right-click file -> `move to trash`
	3) `delete permanently` - bypasses trash folder (may be only visible when selecting a list of files) or `SHIFT-DEL`
- To empty trash:
	1) in Nautilus -> left panel -> right-click on `Trash` directory
	2) select `Empty Trash`

**FYI Do not ever delete `/home/` directory**


## Disabling & Enabling GUI -> [[Virtual Terminal]]

```bash
# Turn off GUI
sudo systemctl stop gdm 
# OR 
sudo telinit 3

###
# Turn ON GUI
sudo systemctl start gdm 
# OR 
sudo telinit 3
```
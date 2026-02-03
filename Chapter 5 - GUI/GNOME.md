- [GNOME WIKI](https://wiki.gnome.org/Personalization)
- GNOME is a popular Desktop env, with easy to use [[GUI]]
- Bundled by default in [[RHEL]], [[Fedora]], [[CentOS]], [[SUSE]] Linux enterprise, [[Ubuntu]] and [[Debian]]
- It has menu-based navigation, which windows users may find easier to navigate
- GNOME may differ between different distros in how it looks or feel


## Theme

- GNOME comes with a few themes you can use to change UI looks
- Usually available in `gnome-tweaks` but if not there, it can be found in `gnome-extensions-app`
## [[gnome-tweaks]]

- Utility for tweaks and options for GNOME
- It also allows to install [[Extensions]]

## enabling GNOME "new" option Template

```bash
# to enable option to create new files in folder in gnome by-right clicking use:
username:/tmp> touch ~/Templates/new

# If system is new and there is no /Templates/ folder yet use this instead:
mkdir -p ~/Templates
touch ~/Templates/new
```
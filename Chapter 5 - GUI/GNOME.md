- [GNOME WIKI](https://wiki.gnome.org/Personalization)
- GNOME is a popular Desktop env, with easy to use [[GUI]]
- Bundled by default in [[RHEL]], [[Fedora]], [[CentOS]], [[SUSE]] Linux enterprise, [[Ubuntu]] and [[Debian]]
- It has menu-based navigation, which windows users may find easier to navigate
- GNOME may differ between different distros in how it looks or feel


## Theme

- GNOME comes with a few themes you can use to change UI looks
- Usually available in `gnome-tweaks` but if not there, it can be found in `gnome-extensions-app`
## gnome-tweaks

- Utility for tweaks and options for GNOME
- It provides much more granular access to  GUI appearance and behaviour
- It also allows to install extensions, although some distros has placed them in separate utility called `gnome-extensions-app`
- It may not be installed by default but it can be installed
- Older name was `gnome-tweak-tool`


## Extensions

- You can find GNOME extensions in `gnome-extensions-app`
- To control GNOME Shell extensions using [website](https://extensions.gnome.org/) you must install GNOME Shell integration that consists of two parts: 
	1) `browser extension`
		- **Chrome**-based browsers install the extension using then [Chrome Web Store](https://chrome.google.com/webstore/detail/gnome-shell-integration/gphhapmejobijbbhgpjhcjognlahblep).
		- **Firefox** - manually install extension from [Mozilla Add-ons site](https://addons.mozilla.org/firefox/addon/gnome-shell-integration/). Please note that Firefox is supported since connector version 8.
		- **Opera** was supported since connector version 7 up to version 10.1. However extension [was deactivated at Opera addons website without any technical explanation](https://gnome.pages.gitlab.gnome.org/gnome-browser-integration/images/opera-conversation.png).
	2) `native host messaging application` - [wiki page](https://gnome.pages.gitlab.gnome.org/gnome-browser-integration/pages/installation-guide.html) with installation instructions.



## enabling GNOME "new" option Template

```bash
# to enable option to create new files in folder in gnome by-right clicking use:
username:/tmp> touch ~/Templates/new

# If system is new and there is no /Templates/ folder yet use this instead:
mkdir -p ~/Templates
touch ~/Templates/new
```
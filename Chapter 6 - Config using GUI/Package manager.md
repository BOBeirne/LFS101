- package managers provide a way to install and uninstall software on Linux systems
- each package in Linux provides one piece of the functionality
- packages often rely on each other's utilities such as e-mail package relies on using SSL and TLS packages

## Low-level

- All systems have `lower-level package manager`, who's job is to handle details of unpacking packages and putting pieces in the right places.
- It does not use internet and it does not provide support for dependencies, unlike the high-level package managers
- Examples:
	- [[dpkg]] - [[Debian]] family
	- [[rpm]]  - [[Red Hat]] and [[SUSE]] family	

## High-level

- You can also use `higher-level utility`, which knows how to:
	1) download packages from internet 
	2) Install the package
	3) manage dependencies and groups automatically
- Those package managers come in [[CLI]] and [[GUI]] versions 

### [[CLI commands]]

| FAMILY NAME | LOW LEVEL | HIGH LEVEL | Note                           |
| ----------- | --------- | ---------- | ------------------------------ |
| [[Debian]]  | [[dpkg]]  | [[apt]]    |                                |
| [[SUSE]]    | [[rpm]]   | [[zypper]] |                                |
| [[Red Hat]] | [[rpm]]   | [[dnf]]    | RHEL 7 + CentOS 7 used [[yum]] |
|             |           |            |                                |

### Basic packaging commands

| Operation                                   | [[Red Hat]]                   | [[Debian]]              |
| ------------------------------------------- | ----------------------------- | ----------------------- |
|                                             |                               |                         |
| install package                             | rpm -i foo.rpm                | dpkg --install foo.deb  |
| install with dependencies                   | dnf install foo               | apt install foo         |
| remove package                              | rpm -e foo.rpm                | dpkg --remove foo.deb   |
| remove incl dependencies                    | dnf remove foo                | apt autoremove foo      |
| update package                              | rpm -U foo.rpm                | dpkg --install foo.deb  |
| update incl dependencies                    | dnf update foo                | apt install foo         |
| Update entire OS                            | dnf update                    | apt dist-update         |
| show ALL installed packages                 | rpm -qa OR dnf list installed | dpkg --list             |
| get info on the package                     | rpm -qil foo                  | dpkg --listfiles foo    |
| show packages that have `foo` in their name | dnf list "foo"                | apt-cache search foo    |
| show all available packages                 | dnf list                      | apt-cache dumpavail foo |
| what package is `file` part of?             | rpm -qf file                  | dpkg --search file      |

- for [[SUSE]] - [[zypper]] - just replace `dnf` with `zypper`
### [[GUI]]

| FAMILY      | SOFTWARE NAME                                   |
| ----------- | ----------------------------------------------- |
| [[Debian]]  | [[Synaptic]], [[GNOME]], Ubuntu Software Center |
| [[Red Hat]] | [[GNOME]], dnfdragora                           |
| [[SUSE]]    | [[YaST]]                                        |

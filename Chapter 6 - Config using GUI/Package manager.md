- package managers provide a way to install and uninstall software on Linux systems
- each package in Linux provides one piece of the functionality
- packages often rely on each other's utilities such as e-mail package relies on using SSL and TLS packages

## Low-level

- All systems have `lower-level package manager`, who's job is to handle details of unpacking packages and putting pieces in the right places.
- It does not use internet and it does not provide support for dependencies, unlike the high-level package managers
- Examples:
	- [[dpkg]] - [[Debian]] family
	- [[RPM]]  - [[Red Hat]] and [[SUSE]] family	

## high-level utility

- You can also use `higher-level utility`, which knows how to:
	1) download packages from internet 
	2) Install the package
	3) manage dependencies and groups automatically
- Those package managers come in [[CLI]] and [[GUI]] versions 

### CLI

- [[APT]] used in [[Debian]] family
- [[yum]] -  [[RHEL]] 7 & [[CentOS]] 7
- [[dnf]] - [[RHEL]] 8 & 9, [[CentOS Stream]], [[Fedora]]
- [[zypper]] - [[openSUSE]] / [[SLES]] (but uses .rpm packages like red hat)

### GUI

- [[Synaptic]], GNOME Software. Ubuntu Software Center - [[Debian]] family
- GNOME Software, dnfdragora - [[Red Hat]] family
- [[YaST]] - [[SUSE]] family
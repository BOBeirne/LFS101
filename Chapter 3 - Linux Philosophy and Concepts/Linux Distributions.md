There are **hundreds of Linux distributions**, but **primary [[Linux families]]** are:

- **[[Red Hat]]** - Family
	- **[RHEL](http://www.redhat.com/)** - Distro
	- **[CentOS](http://www.centos.org/)** - Distro 
	- **[Fedora](http://www.fedoraproject.org/)** - Distro 
- **[[SUSE]]** - Family 
	- **[openSUSE](http://www.opensuse.org/)** - Distro 
	- **[SLES](https://www.suse.com/products/server/)** - Distro
- **[[Debian]]** - Family
	- **[Debian](http://www.debian.org/)**
	- **[Ubuntu](http://www.ubuntu.com/)** - Distro 
	- [Linux Mint](http://www.linuxmint.com/) - Distro 
-  Other distros...

- Full Distro consist of [[Kernel]] + software tools for administrating the system files, users and software packages
## [[Kernel]]

- Kernel is at the heart of the OS
- All Kernels can be found in [Linux Kernel Archives](https://www.kernel.org/)
- Different distributions may be based on widely different Kernel versions
	- e.g. RHEL 8 - 4.18 (older, but stable)
	- RHEL 9 - 5.14 (much newer)


## Kernel vs Distribution

- [[Kernel]] - the core engine that talks to hardware and manages processes
- Distribution (distro) - kernel + all the software needed to make a usable system

## Software

Types of software added to kernel to make distro:

  - Package manager (apt, dnf, pacman)
  - System libraries
  - Compilers/dev tools
  - Desktop environment (if GUI)
  - Pre-installed applications

## OS Support

### Enterprise

Enterprise distros provide commercial (paid) support in a way of:

  - Long-term security updates
  - Hardware/software certification
  - Bug fixes and performance patches
  - Technical support

#### Favourite Distributions

- Red Hat - RHEL
- SUSE
- Ubuntu (cannonical)

### Community-backed alternatives

#### Enterprise

- CentOS (EOL)
- CentOS Stream (RHEL preview)
- Alma Linux - Active replacement (RHEL-derived substitutes)
- Rocky Linux - Active replacement

#### DevOps / Education

- Ubuntu
- Fedora


## Choosing a Linux Distribution

Examples of popular choices depending on the system purpose

### Server

- RHEL
- CentOS
- Ubuntu Server
- SLES
- OpenSUSE
- Debian

### Desktop

- Ubuntu
- Fedora
- Debian
- ArchLinux

### [[Embedded]]

- Yocto
- Android
- Open Embedded
- OpenWrt (routers)


### Questions to ask before choosing

- What is main function of the system (server/desktop/embedded)
- what types of packages does it need (web server/word processing etc)
- Required storage space
- How often needing updates
- Support cycle - LTS or not
- Hardware used - X86 / RISC-V / ARM / PPC
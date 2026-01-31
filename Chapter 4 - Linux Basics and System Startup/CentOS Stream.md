### Downloading

1) go to [Download link](https://www.centos.org/download/)
2) choose CentOS stream 10 (or latest)
3) Download the iso file
4) Mount into VM

### Installation (Hyper-V)

1) Quick create...
2) tick OFF the box "this vm will run windows"
3) Change install source -> Select ISO
4) Let the system unpack install files for installation
5) Select language and keyboard layout
6) Create **user** + **password** and set up a root account
7) In software selection -> select **Workstation Installation**
8) Pick drive or partition to use or create your own
9) Choose [[File System]] as [[xfs]]
10) Let the system download or / and install 
11) **restart** once prompted
### Post-installation Setup

1) login to account
2) Terminal 
	1) `su` + password when prompted
	2) `dnf update` - to update system packages
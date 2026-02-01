### Downloading

1) go to [Download link](https://www.centos.org/download/)
2) choose CentOS stream 9 (or latest)
3) Download the iso file
4) Mount into VM

### Installation (Hyper-V)

1) Quick create...
2) Tick OFF the box "this vm will run windows"
3) Change install source -> Select ISO
4) connect to vm
5) Let the system unpack install files for installation
6) Select **language** and keyboard layout
7) Create **user** + **password**
8) **Root** password + disable ssh
9) In **software selection** -> select **Workstation Installation**
10) **create partitions**: (slightly different setup that LF101 tutorial due to Hyper-V disk being type 2)
	1) custom...
	2) Press `+` -> `/boot/efi` -> `512m`
	3) Press `+` -> `swap` -> `4GiB`
	4) Press `+` ->  simple partition  
	5) click `+` mount point: `/` -> confirm
	6) Choose [[File System]] as [[ext4]] for `/`
	7) Done
11) Let the system and install 
12) **restart** once prompted
### Post-installation Setup

1) login to account
2) Terminal 
	1) `su` + password when prompted (this will be changed to sudo later)
	2) `dnf update` - to update system packages
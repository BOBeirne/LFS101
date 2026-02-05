- Being able to find documentation is a valuable skill as many distributions differ but every one of them has a manual page
- Documentation sources:
	- [[man]] pages
	- GNU [[info]]
	- command `--help`
	- other.. 
		- Desktop help system [[GUI]]  
			- [[GNOME]] - `gnome-help` or `yelp`
			- [[KDE]] - `khelpcenter`
		- package documentation - usually in `/usr/share/doc`directory, grouped in subdirectories named after each package
		- online resources - each distro has it's own documentation online
			- - [Ubuntu Documentation](https://help.ubuntu.com/)
			- [CentOS Documentation](https://wiki.centos.org/Documentation)
			- [openSUSE Documentation](https://doc.opensuse.org/)
			- [Gentoo Documentation](https://www.gentoo.org/support/documentation/)
			- [Fedora Documentation](https://docs.fedoraproject.org/).

## [[man]]

- man - is short for manual, first introduced in UNIX in 70s
- [Online man pages](http://man7.org/linux/man-pages/) - man pages converted to pdfs and web pages
- Man pages are most often used source of info in Linux systems

## [[info]]

- GNU project's standard documentation format, which it prefers as an alternative to **man**.
## `--help`

- short description of the manual
- it's much faster to display
- usage: `man --help` to see help page about [[man]]
- you can also use `-h`

### bash `help` version

- In the bash cmd shell some commands run it's own bash version rather than usual binaries in OS
- there may be some small changed between `--help` from system and bash version but it performs the same function


## Desktop help system

- [[GUI]] documentation but search seems to be broken and usually only brings up the [[GNOME]] desktop information
- you can use command line to "hop" onto page you are looking for in GUI interface
- It is suspected that this is a bug

Example:
`yelp man:cat` - should open yelp gui appwith cat [[man]]ual
`yelp info:cpio` - should also work for [[info]]
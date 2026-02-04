- Low-level [[Package Manager]] for [[Red Hat]] family and some SUSE
	- Red Hat family: RHEL, CentOS, Fedora, Rocky, Alma
	- SUSE family: openSUSE, SLES
- Only installs/uninstalls individual .rpm files
- does not work on dependencies, use [[dnf]] for higher level - dependencies management
- no internet involved

## Common query flags

| Command                   | result                                   |
| ------------------------- | ---------------------------------------- |
| rpm -q package            | Check if package is installed            |
| rpm -qa                   | List all installed packages              |
| rpm -qi package           | Package info (description, version)      |
| rpm -ql package           | List files installed by package          |
| rpm -qf /path/to/file     | Which package owns this file?            |
| rpm -q --whatprovides foo | Which package provides capability "foo"? |
| rpm -q --whatrequires foo | What packages depend on foo?             |

## Dry run

-   No actual changes made — just shows what would happen or what errors would occur

| Flag combo  |                                       |
| ----------- | ------------------------------------- |
| -ivh --test | Test install (verbose, hash progress) |
| -Uvh --test | Test upgrade                          |
| -e --test   | Test erase/remove                     |


## Repositories in Linux Package Management

  - A repository (repo) is a remote server hosting software packages. 
  - Your package manager downloads and installs from these sources.

## Why Repositories Matter

| Concept           | Explanation                                      |
| ----------------- | ------------------------------------------------ |
| Official repos    | Maintained by distro, tested, secure             |
| Third-party repos | Extra software not in official repos, not tested |
| Priority/trust    | Official repos preferred over third-party        |
| Metadata          | Repo index listing available packages + versions |

## Comparison of [[CLI commands]] Across Distribution Families

| TASK        | [[openSUSE]]        | [[Ubuntu]]                | [[Red Hat]]                   |
| ----------- | ------------------- | ------------------------- | ----------------------------- |
| List repos  | zypper lr           | cat /etc/apt/sources.list | dnf repolist                  |
| Add repo    | zypper ar URL alias | add-apt-repository        | dnf config-manager --add-repo |
| Remove repo | zypper rr alias     | edit sources.list         | dnf config-manager --disable  |
| Refresh     | zypper refresh      | apt update                | dnf makecache                 |

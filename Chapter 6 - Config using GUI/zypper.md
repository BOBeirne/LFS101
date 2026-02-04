- [[CLI]] - based [[Package Manager]] for [[SUSE]] family


## Basic Commands


| COMMAND            | RESULT                  |
| ------------------ | ----------------------- |
| zypper search foo  | Search for package      |
| zypper install foo | Install package         |
| zypper remove foo  | Remove package          |
| zypper update      | Update all packages     |
| zypper update foo  | Update specific package |
## Flags

| FLAG | MEANING                          |
| ---- | -------------------------------- |
| -y   | Auto-yes (no prompts)            |
| -n   | Dry run (show what would happen) |
| -v   | Verbose output                   |

## Advanced commands


| COMMAND                         | RESULT                                    |
| ------------------------------- | ----------------------------------------- |
| zypper refresh                  | Refresh repository metadata               |
| zypper dup                      | Distribution upgrade (for **Tumbleweed**) |
| zypper info foo                 | Show package details                      |
| zypper search -i                | List only currently installed packages    |
| zypper search --provides foo OR | What package provides "foo"?              |
| zypper wp foo                   | Short for what-provides                   |
| zypper search --requires foo    | What requires "foo"?                      |
| zypper clean                    | Clear package cache                       |
| zypper lr                       | List repositories                         |
| zypper ar URL alias             | Add [[repository]]                        |
| zypper rr alias                 | Remove repository                         |

## Example usage

```bash
# search for package
zypper search foo
# Dry run — see what would be installed
sudo zypper install -n foo
# install package
sudo zypper install foo
#remove package
sudo zypper remove foo
# Update all, no prompts
sudo zypper -y update

# Refresh repos then update
sudo zypper refresh && sudo zypper update
```

# Leap vs Tumbleweed


| Distro               | command                           |
| -------------------- | --------------------------------- |
| Leap (stable)        | zypper update                     |
| Tumbleweed (rolling) | zypper dup (distribution upgrade) |

## [[Repository]] commands

### Adding a Repository

```bash
# Add repo with URL and give it a name (alias)
sudo zypper ar https://download.example.com/repo/ my-repo

# Add and refresh immediately
sudo zypper ar -f https://download.example.com/repo/ my-repo

# Add and auto-import GPG key
sudo zypper ar -G https://download.example.com/repo/ my-repo
```


## Removing a Repository

```bash
# List repos first to find alias
zypper lr

# Remove by alias
sudo zypper rr my-repo

# Remove by number (from lr output)
sudo zypper rr 5
```  


### Common Third-Party Repos (openSUSE)

| REPOSITORY    | USAGE                                  |
| ------------- | -------------------------------------- |
| Packman       | Multimedia codecs, restricted software |
| NVIDIA        | Proprietary graphics drivers           |
| Google Chrome | Chrome browser                         |
| VS Code       | Microsoft VS Code                      |

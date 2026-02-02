- [[APT]] - Advanced Package Tool
- high-level [[Package manager]] package management utility used in [[Debian]] family
-  apt = app store (finds, downloads, installs everything you need)


## [[Repository]] compatibility

- [[APT]] repos have the same format across [[Debian]]/[[Ubuntu]]/Mint but packages inside are built for specific distros
- A .deb for Ubuntu 22.04 might not work on Debian 12
- Software publishers often maintain separate repos per distro

## CLI

```bash
# Common commands:
sudo apt update          # Refresh package list
sudo apt install nginx   # Install package + dependencies
sudo apt remove nginx    # Remove package
sudo apt upgrade         # Update all packages
```
- Core engine that talks to hardware and manages processes
- Kernel is at **the heart of the OS**
- All Kernels can be found in [Linux Kernel Archives](https://www.kernel.org/)
- Different distributions may be based on widely different Kernel versions 
- Stable/enterprise distros (RHEL, Ubuntu LTS) use older, battle-tested kernels
- Enterprise distros backport security fixes and features to their older kernels, so "old" doesn't mean "insecure"
- Rolling/bleeding-edge distros (Arch, Fedora) use newer kernels

| Distro | Kernel | Philosophy                   |
| ------ | ------ | ---------------------------- |
| RHEL 8 | 4.18   | Stability over features      |
| RHEL 9 | 5.14   | Newer but still conservative |
| Fedora | Latest | Testing ground for RHEL      |
- Kernel alone is not usable, you need to pair it with tools, package mgmnt etc to make it usable!
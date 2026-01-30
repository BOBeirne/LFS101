## Linux vs UNIX 

- Linux System was built from scratch, not derived from UNIX code, Linus was only inspired by it
- UNIX philosophy was designed for very powerful computers, not PCs
- Commercial Unix for Intel PCs (like SCO Unix) existed but was too expensive for individuals
- Linus couldn't afford a Unix system, so he wrote Linux for his 386 PC

## Linux

- `Files` - stored in hierarchical filesystem
	- TOP NODE - `root` or `/`
- Linux makes it's `components` available via **files or objects that look like files**
	- **processes, devices and net sockets are represented** by file-like objects and can be used via same utils used for regular files
- `Multitasking` - Linux can perform multiple threads of execution simultaneously
- Supports `multiple users` with built-in `networking` and `service processes `(aka daemons)
	- `sshd`, `systemd`, `httpd` — the d stands for daemon.
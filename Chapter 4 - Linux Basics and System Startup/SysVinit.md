- Back in the 80s in System V variety of UNIX, the startup (equivalent of current [[BOOT]]) process was using a sequence of `runlevels` containing a collection of scripts
- each script was responsible for starting and running services and each runlevel supported a different mode of running the system
- within each runlevel, individual services could be set to run or to be shut down if needed

Currently most major distros have moved away from this method but they can be emulated if needed
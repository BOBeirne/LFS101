
- Located in root filesystem `/sbin/init`
- It has been replaced by [[systemd]] and now just points to `/lib/systemd/systemd`

If used by system instead of [[systemd]]
- Launches after [[initramfs]] is cleared from RAM after all the basic checks and driver loads are done
- handles the [[mount]]ing and pivoting(???) over to real root [[File System]]
- Besides starting the system, it is also responsible for keeping the system running and shutting it down ina clean way.
- It is also a manager for any non-kernel processes - cleanup on completion, restart of user login services etc
- See [[SysVinit]] - for explanation of old method managing those processes

## Text-mode Login

- at the end of BOOT process, the init starts a number of login prompts in text mode [[Virtual Terminal]]
- they allow you to type in username and password
- You may not see them if you use GUI until they are launched in GUI
- After providing credentials it runs Command [[Shell]]


- The Yet another Setup Tool (YaST) - actualluy `yast2`
- [[GUI]] [[Package Manager]] for [[openSUSE]]
- it uses [[rpm]]-based application
- YaST2 replaced YaST1 around 1999-2000 when SUSE Linux 6.3/7.0 was released.
	- YaST1 (1994) - text-based, ncurses interface
	- YaST2 (1999+) - rewritten with GUI support (Qt/GTK), modular architecture
- The "2" stuck even though it's been over 25 years. There's no YaST3 - they just keep updating YaST2. 
- when tutorials/courses say "YaST" they mean YaST2
## Accessing YaST

- Option 1:
	1) Activities
	2) search for "YaST"
	3) click the YaST icon
	4) click `software management`

-  Option 2 - KRunner:
	1) Press Alt+F2 (or Alt+Space)
	2) Type yast
	3) Press Enter

 Option 3 - Terminal:
-  `sudo yast2`


## Troubleshooting

```bash
# Check if yast is installed
rpm -qa | grep yast

# Install if missing
sudo zypper install yast2 yast2-packager
```
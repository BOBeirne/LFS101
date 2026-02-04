- CLI - command line interface
- It allows for much deeper and granular control of the system's settings that a [[GUI]]
 environment
 - while [[GUI]] varies between distributions, the CLI does not
 - It allows to remotely connect to devices anywhere on the internet
 - Allows to implement scripts for repeatable but easy-to forget tasks
 
## CLI vs [[Virtual Terminal]]

 - In GUI you can have multiple CLI terminals opened at once and visible on the screen at the same time
 - This is different from [[Virtual Terminal]], where you can only see 1 terminal at the time

## [[CLI commands]]

See [[CLI commands]] for list of usable commands

## Modifying CLI display

### PS1

- default character string displayed at the CLI prompt
- to enable visibility of current user and hostname in cli, use this setting

```bash
# check current setup
echo $PS1
# \$
# change the display setting
PS1="\u@\h \$ "
# confirm changes
echo &PS1
username@host $
```

- remember that [[root]] always uses `#` as their prompt char
## CLI shortcuts

- `CTRL-L` - clear screen

















also see [[Virtual Terminal]], [[Shell]] and [[CLI commands]]
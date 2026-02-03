- VT - Virtual Terminals
- VT are console sessions that use whole screen + keyboard controls outside of GUI
- They are considered virtual because only one appears at the time on the screen

- Terminals can be accessed by `ALT+FN` keys
- Most distros start system with `6` text terminals + `1` GUI terminal starting with `F1` or `F2`
- 1 virtual terminal (usually `VT1` or `VT7`) is reserved for the graphical environment, and text logins are enabled on the unused VTs

- On systems with [[GUI]], the [[CLI]] in application running is actually a [[Terminal Emulator]]

## Choosing between [[GUI]] and [[Virtual Terminal]] environment

- The nature of Linux allows for customizability when it comes to choice between VT and GUI.
- Linux can be run purely using terminal and many production servers have GUI completely switched off to conserve resources and security
- If your system comes configured without GUI, there is always an option to install it and enable it.

## Switching between VTs

- To switch, press `CTRL-ALT-FN`
- for e.g. `CTRL-ALT-F6` for `VT6`
- While in the [[Virtual Terminal]], you only ned to use `CTRL-FN` to switch between other VTs
## Use cases

- Very handy to use if you ever run into an issue with [[GUI]] and need to troubleshoot the issue with it










also see [[CLI]], [[CLI commands]]or [[Shell]]
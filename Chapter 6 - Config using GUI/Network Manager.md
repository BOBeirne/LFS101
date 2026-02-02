- A single utility that contains settings for all available network types in order to avoid having to configure different files in different location for each network
- It can list all available networks wireless and wired, mobile bb network, handle passwords and set up VPNs

## Wired connections

- usually do not require manual config, the hardware picks up the presence of a sigmal and Network Manager sets up the network settings via [[DHCP]]
- You can use Network Manager to make [[IP]] address static
- You can also change the [[MAC]] address

## Wi-Fi (wireless)

- You may be prompted to provide credentials to access the settings
- When you provide password for wifi network it will remember it by default for the next time
- You can use Network Manager to access more network information, change IP to static, Change DNS or manage remembered wifi networks

## Mobile Broadband

- You can setup mobile broadband connection using [[Network Manager]] -> it will launch a wizard to set up the details
- Once configured, the setup will be remembered for any future connections

## VPN

- you can use [[Network Manager]] to set up a VPN connection
- It supports many VPN technologies, such as
	- IPSec (native)
	- Cisco OpenConnect - either via cisco client or native OSS client
	- Microsoft PPTP
	- OpenVpn
	- WireGuard (ubuntu) 
	- For custom VPNs you need to install packages from distributor 

## Proxy

- You can setup HTTP, HTTPS, FTPS, SOCKS Host proxy
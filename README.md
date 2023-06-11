# macOS_Network_Commands
This is cheat sheet of Mac network commands

## ipconfig
1. get ip address
```bash
 $ ipconfig getifaddr en0
 $ ip=`ipconfig getifaddr en0`
 $ echo $ip
 ```
2. get subnet mask
```bash
$ ipconfig getoption en0 subnet_mask
```
3. get dns server
```bash
 $ ipconfig getoption en0 domain_name_server
 ```
 4. get info about how en0 got its dhcp on
 ```bash
 $ ipconfig getpacket en0
  ```
5. renew dhcp lease
```bash
 $ ipconfig set en0 DHCP
 ```
6. set a specific ip address 
```bash
  $ ipconfig set en0 INFORM 192.168.1.160
```
## ifconfig

1. get network info
```bash
$ ifconfig en0
```
2. set ip address and netmask
```bash
 $ ifconfig en0 inet 192.168.1.154 netmask 255.255.255.0
 ```
 3. renew dhcp leases
 ```bash
 $ ipconfig set en0 BOOTP && ipconfig set en0 DHCP
 $ ifconfig en0 down && ifconfig en0 up
 ```
 
 ## networksetup
 1. get a list of location on the computer
 ```bash
  $ networksetup -listlocations
  ```
  2. get active location
  ```bash
  $ networksetup -getcurrentlocation
  ```
  3. config manual static ip address
  ```bash
  $ networksetup -setmanual Wi-Fi 192.168.1.154 255.255.255.0 192.168.1.253
  ```
  4. config dns server
  ```bash
  $ networksetup -setdnsservers Wi-Fi 192.168.1.154 192.168.1.253
  ```
  5. get dns server
  ```bash
  $ networksetup -getdnsservers Wi-Fi
  ```

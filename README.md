## upc_keys.py ##

**upc_keys.py** WPA2 passphrase recovery tool for UPC%07d devices with automatic WIFI scanning and passphrase validation.

### What is this? ###

A while ago [some smart guys in a university](https://www.usenix.org/system/files/conference/woot15/woot15-paper-lorente.pdf) figured out that untouched WIFI access points by UPC routers are vulnerable to passphrase cracking based on their SSID. [upc_keys.c](https://haxx.in/upc_keys.c) was quickly coded as POC by [bl4sty](https://twitter.com/bl4sty). I took the time to 'weaponize' it with this little script.

### Built exclusively for network-manager ###

This script uses `network-manager` to scan for SSIDs starting with UPCxxxxxx and validates the keys generated by [upc_keys.c](https://haxx.in/upc_keys.c). `network-manager` is present on Debian based systems and used to control WIFI connections, among other things.


### How to install ###

```
~$ git clone <this repo>
~$ python setup.py develop
```

### How to use ###

```
~$ crack-upc -i wlan0 
or
~$ crack-upc -s UPC1234567
```
- --help for more info

### Disclaimer ###

Coded as an excuse to get into Python bindings for C, the mileage you'll get out of this script might vary.
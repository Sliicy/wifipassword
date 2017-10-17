# wifipassword
Quickly get the Wifi Password on Debian Linux

# How to use:
Simply allow execution of wifipassword (either by rightclicking and selecting "allow executing file as a program", or with chmod +x) and run from Terminal.

# Code Explanation:

#!/bin/bash
The header needed to run.

WIFI="$(iwgetid -r)"
Create a variable called "WIFI" equal to the name of the current Network.

echo ${WIFI}
Say the Wi-Fi Name.

awk '/psk=/{print $NF}' /etc/NetworkManager/system-connections/${WIFI} | cut -c 5-
Print out the saved password of this wifi and trim the results (so you don't see "psk=").

#Network Configuration

##Remove network-manager

remove network-manager package:

    sudo apt-get purge network-manager

##Configure a network connections using a native way

open the interfaces file:

    sudo nano /etc/network/interfaces

add lines:

    auto eth0
    allow-hotplug eth0
    iface eth0 inet dhcp

    auto wlan0
    allow-hotplug wlan0
    iface wlan0 inet dhcp
        wireless-essid <ESSID>
        wireless-key <mysecretpassphrase>

save the changes and close the file:

    Ctrl+O, Ctrl+X

apply changes:

    sudo ifdown -a && sudo ifup -a

##Remove udev rules

open a file with udev net rules:

    nano /etc/udev/rules.d/70-persistent-net.rules

remove all lines containing NAME="eth0" or NAME="wlan0"

save the changes and close the file:

    Ctrl+O, Ctrl+X

##Links

[Ubuntu WiFiHowTo](https://help.ubuntu.com/community/WifiDocs/WiFiHowTo)

[Ubuntu Network Configuration](https://help.ubuntu.com/lts/serverguide/network-configuration.html)

[Debian Network Configuration](https://wiki.debian.org/NetworkConfiguration)

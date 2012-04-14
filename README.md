README
======

This script should allow you to autologin to WiFi networks that are managed
by Mikrotik routers that require you to enter a username and password.

You need to put mikrotiklogin into /etc/NetworkManage/dispatcher.d/

Then copy mikrotiklogindetails.sh into /etc/ and edit to put your details
into the file.

Then when you connect to the network with that SSID the script will be called.
It will fetch the login page, extract the salt from it, hash the salt and your
password together and POST it back to the gateway server. Then you will be
online without having to do anything.

To test the script you can run:

    bash -x /etc/NetworkManager/dispatcher.d/mikrotiklogin wlan0 up

which will show you the commands being run so you can see if they are what
you expect.

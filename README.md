# jpioBox
analog, digital to OSC interface

Login info for ssh into jPio box
user: pi
pass: ***************

It is also possible to acces the jPio box over WiFi. SSID is same as host name. password is ***************

Some commands that can be run.
rw = enter read/write mode for the file system
ro = enter read only mode for the file system
sudo systemctl status oscio.service = status of OSCio service
sudo systemctl stop oscio.service = stop OSCio service
sudo systemctl start oscio.service = start OSCio service
/home/pi/OSCio.py = run OSCio.py script, this will have some debugging info. Stop oscio.service before running this.

For the jpiotest.toe file to work do the following.
Log into the jPio box over ssh. (e.g. 'ssh pi@jpio-01.local')
Run the command 'rw' to enter read/write mode
Edit the file /home/pi/OSCio.py
Change the IP address for the variable PRIMARY_ADDRESS to the IP of the machine running the file jpiotest.toe 
(OSCio.py line 24)
Run the command 'sudo systemctl restart oscio.service'
The Online indicator in the test file should be green. (Hostname field should contain the hostname of the box being tested e.g. jPio-01)

The shipped config is for the jPio box to look for DHCP server, if none found it falls back to a static IP.
To change the fallback static IP edit the file /etc/dhcpcd.conf
There are configuration examples in the file.

Automation Hat documentation is here:
https://shop.pimoroni.com/products/automation-hat
Automation Hat documentation and examples in /home/pi/Pimoroni/automationhat/

Fan SHIM documentation is here:
https://shop.pimoroni.com/products/fan-shim
Fan SHIM examples in: /home/pi/fanshim-python/examples/

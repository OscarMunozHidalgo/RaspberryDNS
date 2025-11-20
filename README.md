# RaspBerryDNS
Making a network-wide ad blocker using Raspberry Pi 5. 

## Installing RaspberryPiOS
First things first an *Operating System* through an SD card, in this case *Raspberry Pi OS* will be installed using *Raspberry Pi Imager*, enabling ssh following this [guide][1].

## Setting the network up
The RaspBerry Pi should be connected to the network router using a *static IP address* as we will be accessing to it by ssh from another device connected to the same router. Also it will be required in the future steps, as we will chose this device as our DNS server, and so the router will need this IP to find the DNS device.

To make Raspberry Pi IP static, first we need to access the *router's administration interface*, you can do this by entering its IP address in a browser, usually it is 192.168.1.1, although more information might be available in the backside, under the router or in its manuals.

Once the router's IP is known and you have accessed its web interface, in this case it is located at *Advanced > Network > DHCP Server > Address Reservation*, when located, we select the Raspberry Pi and choose the IP it will be asigned next time it connects to the router.

Añadir Imagen

## Bibliography
[1]: https://www.youtube.com/watch?v=sq5S1MM2Pmo

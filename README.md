# RaspberryDNS
Making a network-wide ad blocker using Raspberry Pi 5. 

## Installing RaspberryPiOS
First things first an *Operating System* through an SD card, in this case *Raspberry Pi OS* will be installed using *Raspberry Pi Imager*, enabling ssh following this [guide][1].

## Setting the network up
The RaspBerry Pi should be connected to the network router using a *static IP address* as we will be accessing to it by ssh from another device connected to the same router. Also it will be required in the future steps, as we will chose this device as our DNS server, and so the router will need this IP to find the DNS device.

To make Raspberry Pi IP static, first we need to access the *router's administration interface*, you can do this by entering its IP address in a browser, usually it is 192.168.1.1, although more information might be available in the backside, under the router or in its manuals.

Once the router's IP is known and you have accessed its web interface, in this case it is located at *Advanced > Network > DHCP Server > Address Reservation*, when located, we select the Raspberry Pi and choose the IP it will be asigned next time it connects to the router.

Añadir Imagen

## Pi-hole
### Remote Control
This step can be skiped by locally operating the device, nontheless in this case ssh will be used to remote control the Raspberry Pi, using its IP address and user.

```bash
ssh <username>@<ipaddress>
```

## Instalation
In this step Pi-hole official [guide][2] will be followed, using the *One-Step Automated Install* by executing the following command in the terminal.

Please check the oficial [guide][2] as this command or the instalation method may change.
```bash
curl -sSL https://install.pi-hole.net | bash
```
> [!WARNING]  
> Pi-hole web interface uses port 80 for http and 443 for https by default so it may fail other service (as apache2) is active simoultaneously.
If both services need to be running at the same time, the port configuration needs to be modified.

Pi-hole web interface files should be moved to other location rather than the original `/var/www/html/admin` it can be done with the next commands.

```
mkdir <new directory>
mv /var/www/html/admin <directory path>
```
Now that pi-hole files have been moved its configuration needs to be updated too. This can be made by `pihole-FTL --config` command or by modifying `/etc/pihole/pihole.toml` file, añadir explicación de como lo hice.

Pi-hole web interface
Some pihole improvements

## Bibliography
[1]: https://www.youtube.com/watch?v=sq5S1MM2Pmo
[2]: https://github.com/pi-hole/pi-hole/#one-step-automated-install

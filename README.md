# solar
Using [Gino Ledesma's](https://github.com/ginoledesma/) [sunpower-pvs-exporter](https://github.com/ginoledesma/sunpower-pvs-exporter)

Variations in my setup:
- Not using a Raspberry Pi, just routing 172.27.153.0 on my local network to allow the machine running Gino's code to communicate to it without a Pi bridge.
- Needed to 172.27.153.1 in /etc/hosts so sunpower-pvs-exporter will run unmodified

Still working through some local issues but the first run is [here](https://github.com/hasherati/solar/blob/master/first-run).
It's 7:18pm PST and the sun is down so no power is being generated.

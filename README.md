# solar
Using [Gino Ledesma's](https://github.com/ginoledesma/) [sunpower-pvs-exporter](https://github.com/ginoledesma/sunpower-pvs-exporter)

Variations in my setup:
- Not using a Raspberry Pi, just routing 172.27.153.0 on my local network to allow the machine running Gino's code to communicate to it without a Pi bridge.
- Needed to put 172.27.153.1 in /etc/hosts so sunpower-pvs-exporter will run unmodified

Still working through some local issues but the first run is [here](https://github.com/hasherati/solar/blob/master/first-run).
It's 7:18pm PST and the sun is down so no power is being generated.

[Here](https://github.com/hasherati/solar/blob/master/second-run) is a run when the suns up.  Summing the lines that have sunpower_pvs_inverter_dc_power_watts will give you the total watts the system is generating.

To run all this, simply run sunpower-pvs-exporter and put it in the background:
```
sunpower-pvs-exporter &
```

Then, in a one-liner, since I always look for excuses to use awk:

```
curl http://localhost:9110 | grep sunpower_pvs_inverter_dc_power_watts | awk -F " " '{s+=$3} END {print s}'
9572.5
```

i.e. system is currently generating 9,572.5 watts, more than I need ;)

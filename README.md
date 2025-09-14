# RPi4 with TSOP IR sensor

This is my small pet-project to create handy HTPC device for vacation travels. There are multiple sources how to setup new remote type ([here](https://forum.libreelec.tv/thread/23391-kodi-harmony-and-raspberry-pi-4-with-ir-sensor-newb-guide/) and [here](https://wiki.libreelec.tv/configuration/ir-remotes)) and how to connect TSOP receiver ([here](https://learn.adafruit.com/using-an-ir-remote-with-a-raspberry-pi-media-center/hardware)), unfortunatelly all a little bit outdated.

So I noted all my steps into this short guide.

## Hardware:
- RPi4 4GB
- [Argon Remote](https://www.amazon.com/Argon-Raspberry-Infrared-Batteries-Included/dp/B091F3XSF6) (why this one? I had a spare, and besides I like its terse design)
- Eventually use [One For All URC 7935](https://www.amazon.com/One-For-All-URC7935/dp/B07R7WNJH7) remote, if you are missing play/pause key :)
- TSOP sensor (any type for 38 kHz will work, I used [TSOP4838](https://www.amazon.com/Bridgold-TSOP4838-Receiver-Infrared-Module%EF%BC%8CDIP-3/dp/B09BTD69C3/))

## Software:
- Installed latest stable LE11 on RPi4
- TSOP in my case was connected to GPIO pin 23, so following line needs to be added to config.txt (you can edit it directly on the SD card):
  - dtoverlay=gpio-ir,gpio_pin=23
- Connect via SSH to RPi4 and create with nano editor these 2 files in case you are connecting Argon remote (see for the contents of zip files in the setup/ folder, it also contains setup for One4All remote):
  - /storage/.config/rc_keymaps/argon40.toml
  - /storage/.config/rc_maps.cfg

That's it, pretty simple. Attached few pictures from my setup, I used alu fanless cooling case and drilled hole in it to expose the sensor.

<img src="https://github.com/adam-aph/rpi4-tsop-ir-sensor/blob/main/pics/RPI4-GPIO23.jpg"/>
<img src="https://github.com/adam-aph/rpi4-tsop-ir-sensor/blob/main/pics/RPI4-inside.jpg"/>
<img src="https://github.com/adam-aph/rpi4-tsop-ir-sensor/blob/main/pics/RPI4-outside.jpg"/>

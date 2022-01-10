# Raspberry-Pi

## Installing Arduino IDE

Update the system

`sudo apt-get update`

`sudo apt-get upgrade`

Installing IDE from terminal

`sudo apt-get install arduino`

## Run Chromium on StartUp

`/usr/bin/chromium-browser --kiosk  "my web address"`

### Open an HTML page on Chromium startup

open the following page,

`sudo nano /etc/xdg/lxsession/LXDE-pi/autostart`

then add the following lines,

`@lxpanel --profile LXDE-pi`

`@pcmanfm --desktop --profile LXDE-pi`

`@xscreensaver -no-splash`

`/usr/bin/chromium-browser --kiosk  --disable-restore-session-state http://localhost:8080/#/Dashboard`

After this run,

`sudo raspi-config`
and from the window turn on wait for network on boot option from network

# Raspberry-Pi

## Installing Arduino IDE

Update the system

`sudo apt-get update`

`sudo apt-get upgrade`

Installing IDE from terminal

`sudo apt-get install arduino`

## Run Chromium on StartUp

`/usr/bin/chromium-browser --kiosk  "my web address"`

## Run a script on Startup

Open rc.local,

`sudo nano /etc/rc.local`

add command,

`python sample.py`

Make rc.local executable

`sudo chmod +x /etc/rc.local`

To make boot not wait for running the script,

`python sample.py &`

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

# Python Virtual Environment Setup
To install python3-venv in the raspberry pi system,
`sudo apt-get install python3-venv -y`

To create an virtual environment,
`python3 -m venv ~/my_venv`

To activate virtual environment,
`source ~/my_venv/bin/activate`

To test virtual environment has been activated or not,

`which python`

`which pip`

# Auto start nodejs server on boot

install pm2 using, `npm install pm2 -g`

startup pm2 on boot using, `pm2 startup`
This will prompt you to add service to systemd if detected. It will also guide you to add pm2 as a service.

start node server using pm2, `pm2 start "yarn run watch" --name project_name`

save the server for starting on boot, `pm2 save`

list running server, `pm2 list` 

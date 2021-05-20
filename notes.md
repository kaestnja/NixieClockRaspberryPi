# sudo nano /etc/rc.local
# sudo "/home/pi/NixieClockRaspberryPi/DisplayNixie/bin/DisplayNixie" 24hour
#or
# sudo nano /home/pi/.bashrc 
# sudo "/home/pi/NixieClockRaspberryPi/DisplayNixie/bin/DisplayNixie" 24hour
#or
#1) Edit the provided nixie.service template to reflect the full path down to your binary:
#  ExecStart=/home/pi/NixieClockRaspberryPi/DisplayNixie/bin/DisplayNixie
#2) Copy your customized nixie.service into the /etc/systemd/system directory:
# sudo cp nixie.service /etc/systemd/system
#3) Reload the systemd state and start the nixie service:
# sudo systemctl daemon-reload
# sudo systemctl start nixie
#4) To stop and/or restart the nixie binary at any time:
# sudo systemctl stop nixie
# sudo systemctl restart nixie

#sudo rpi-update 
sudo apt-get install --fix-missing && sudo apt-get update -y && sudo apt-get upgrade -y --force-yes && sudo apt-get clean -y --force-yes && sudo apt-get dist-upgrade -y --force-yes && sudo apt-get autoremove -y --force-yes && sudo apt-get autoclean -y --force-yes

sudo raspi-config
#Enable SPI and I2C modules

sudo killall DisplayNixie; sudo killall CLITool
cd /home/pi/NixieClockRaspberryPi/DisplayNixie/src && make
cd /home/pi/NixieClockRaspberryPi/CLITool/src && make
cd /home/pi/NixieClockRaspberryPi/Firmware/src && make
cd "/home/pi/NixieClockRaspberryPi/Firmware for NCS314 v3.x/src" && make
cd "/home/pi/NixieClockRaspberryPi/Firmware for NCS318/src" && make

sudo "/home/pi/NixieClockRaspberryPi/DisplayNixie/bin/DisplayNixie" 24hour
sudo "/home/pi/NixieClockRaspberryPi/DisplayNixie/bin/DisplayNixie" 24hour
sudo "/home/pi/NixieClockRaspberryPi/DisplayNixie/bin/DisplayNixie" 24hour
sudo "/home/pi/NixieClockRaspberryPi/DisplayNixie/bin/DisplayNixie" 24hour

sudo "/home/pi/NixieClockRaspberryPi/CLITool/bin/DisplayNixie" 123456
sudo "/home/pi/NixieClockRaspberryPi/CLITool/bin/DisplayNixie" now
sudo "/home/pi/NixieClockRaspberryPi/CLITool/bin/DisplayNixie" settime 11:22:33
sudo "/home/pi/NixieClockRaspberryPi/CLITool/bin/DisplayNixie" setsystime

sudo "/home/pi/NixieClockRaspberryPi/Firmware/bin/DisplayNixie" 24hour
sudo "/home/pi/NixieClockRaspberryPi/Firmware for NCS314 v3.x/bin/DisplayNixie" 24hour
sudo "/home/pi/NixieClockRaspberryPi/Firmware for NCS318/bin/DisplayNixie" 24hour


1) 123456 - any 6 digits. Shield will display these numbers.
2) now - Shield will display current system time at the time the command is executed.
3) clock - the program will loop and will update every second the time from Real Time Clock (RTC on shield board) on tubes.
4) settime x - set time, where x time in format [hh:mm:ss].
5) setsystime - set current time from OS.

#https://www.hanselman.com/blog/remote-debugging-with-vs-code-on-windows-to-a-raspberry-pi-using-net-core-on-arm
curl -sSL https://aka.ms/getvsdbgsh | /bin/sh /dev/stdin -v latest -l ~/vsdbg
sudo passwd root
https://www.raspberrypi.org/blog/coding-on-raspberry-pi-remotely-with-visual-studio-code/

https://www.linkedin.com/pulse/python-remote-debugging-visual-studio-code-raspberry-pi-mircea-dogaru

https://code.visualstudio.com/docs/editor/debugging#_launch-configurations
https://code.visualstudio.com/docs/cpp/config-linux



sudo ./DisplayNixie clock
sudo ./CLITool setsystime

cd /home/pi/afchNixieClockRaspberryPi/DisplayNixie/src && make
cd /home/pi/tonyNixieClockRaspberryPi/DisplayNixie/src && make
cd /home/pi/uberNixieClockRaspberryPi/DisplayNixie/src && make

sudo "/home/pi/afchNixieClockRaspberryPi/CLITool/Debug/CLITool" ledson
sudo "/home/pi/tonyNixieClockRaspberryPi/CLITool/Debug/CLITool" ledson
sudo "/home/pi/uberNixieClockRaspberryPi/CLITool/Debug/CLITool" ledson

sudo "/home/pi/afchNixieClockRaspberryPi/CLITool/Debug/CLITool" setsystime
sudo "/home/pi/tonyNixieClockRaspberryPi/CLITool/Debug/CLITool" setsystime
sudo "/home/pi/uberNixieClockRaspberryPi/CLITool/Debug/CLITool" setsystime

sudo "/home/pi/afchNixieClockRaspberryPi/DisplayNixie/bin/DisplayNixie" clock
sudo "/home/pi/tonyNixieClockRaspberryPi/DisplayNixie/bin/DisplayNixie" 24hour fireworks

turn-on-at
turn-off-at


sudo "/home/pi/uberNixieClockRaspberryPi/DisplayNixie/bin/DisplayNixie" clock



sudo "/home/pi/afchNixieClockRaspberryPi/Firmware/Debug/DisplayNixie" clock
sudo "/home/pi/tonyNixieClockRaspberryPi/Firmware/Debug/DisplayNixie" clock
sudo "/home/pi/uberNixieClockRaspberryPi/Firmware/Debug/DisplayNixie" clock

sudo "/home/pi/afchNixieClockRaspberryPi/Firmware for NCS314 v3.x/DisplayNixie3x/Debug/DisplayNixie3x" clock
sudo "/home/pi/tonyNixieClockRaspberryPi/Firmware for NCS314 v3.x/DisplayNixie3x/Debug/DisplayNixie3x" clock
sudo "/home/pi/uberNixieClockRaspberryPi/Firmware for NCS314 v3.x/DisplayNixie3x/Debug/DisplayNixie3x" clock

sudo "/home/pi/afchNixieClockRaspberryPi/Firmware for NCS318/DisplayNixie/Debug/DisplayNixie" clock
sudo "/home/pi/tonyNixieClockRaspberryPi/Firmware for NCS318/DisplayNixie/Debug/DisplayNixie" clock
sudo "/home/pi/uberNixieClockRaspberryPi/Firmware for NCS318/DisplayNixie/Debug/DisplayNixie" clock


which gpio
gpio -v
gpio readall
sudo apt-get purge wiringpi
cd /usr/local/bin && rm -R * && sudo reboot
cd /usr/bin && rm -R * && sudo reboot
hash -r
sudo apt-get install git-core
git clone git://git.drogon.net/wiringPi
cd ~/wiringP
git pull origin
./build

https://devdrik.de/upgrade-stretch-auf-buster/
http://baddotrobot.com/blog/2019/08/29/upgrade-raspian-stretch-to-buster/

wget https://unicorn.drogon.net/wiringpi-2.46-1.deb && sudo dpkg -i wiringpi-2.46-1.deb
wget https://project-downloads.drogon.net/wiringpi-latest.deb && sudo dpkg -i wiringpi-latest.deb

sudo apt-get install wiringpi

Here’s the steps to try to set up a ssh key from win 10 to a Raspberry Pi I named “RPi4-1”:
In powershell, type:
ssh-keygen
File on which to save the key: C:\Users\\.ssh\ (make sure the backslashes are used throughout the file location)
Don’t use a passphrase because VS Code will simply require you enter it each time.
To copy the key over (for the first time):
cat $env:USERPROFILE\.ssh\.pub | ssh pi@ “mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys”
(If you’re doing it a 2nd time or you are OK with overwriting, use this:)
type $env:USERPROFILE\.ssh\.pub | ssh pi@ “cat >> .ssh/authorized_keys”
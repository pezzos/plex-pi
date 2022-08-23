# Tips for plex-pi

## Allow the boot on SSD

If you need to switch the booting sequence from an SD card to an SSD, see [here](boot-on-ssd/README.md).

## Install DietPi

If you need to switch the booting sequence from an SD card to an SSD, see [here](install-dietpi-on-ssd/README.md).

## Attach the SSD to the Raspberry PI

This part is not documented, there is many way to do that like with an USB adaptator or with some cards like the ones from Geekworm. I personnaly use this [kit](https://geekworm.com/products/raspberry-pi-4-x825-board-x825-case-x735-board-dc-5v-4a-power-supply-kit?variant=39832799838296) and this [one](https://geekworm.com/products/geekworm-naspi-2-5-sata-hdd-ssd-kit-for-raspberry-pi-4-model-b?variant=39916589088856). The last one has a smaller form factor.

## First boot on DietPi

Plug it to an Ethernet cable and a power source, boot and let the magic happens.
At the first boot, you're forced to connect as **root** with the pass `dietpi`.
A script is automatically run to setup your dietpi.

DietPi-Survey

> Do what you want.
> It reboot?

DietPi-Set_software

> Ok > Your password > OK

A serial/UART console is currently enabled, would you like to disable it?

> Yes

Install

> Ok for the pure minimal image (or install plexmediaserver from here)

Exit

## Add some security fixes

sudo vim /etc/hostname
sudo vim /etc/hosts > 192.168.1.1

### Add your own user

useradd -m -s /bin/bash -d /home/pezzos pezzos
usermod -G sudo,gpio pezzos
passwd pezzos

Test to connect and to sudo, if ok, continue

### Remove root access to SSH

[dropbear doc](https://linux.die.net/man/8/dropbear)
echo "OPTIONS=-w -g" >> /etc/default/dropbear
DROPBEAR_EXTRA_ARGS=""
DROPBEAR_EXTRA_ARGS="-w -g"

sudo dietpi-software

> plexmediaserver git python (3 + RPi.GPIO)
> sudo apt install file pigpio pigpiod python3-pigpio python3-rpi.gpio python3-smbus rpi.gpio-common vim xz-utils

git clone https://github.com/pezzos/plex-pi.git

sudo cp ~/plex-pi/scripts/pwm_fan_control.py /root/
sudo cp ~/plex-pi/scripts/x735pwr.sh /root/
sudo cp ~/plex-pi/scripts/rpifan-control.service /etc/systemd/system/
sudo cp ~/plex-pi/scripts/rpipower-control.service /etc/systemd/system/
sudo systemctl enable pigpiod
sudo systemctl enable rpifan-control
sudo systemctl enable rpipower-control
sudo systemctl start pigpiod
sudo systemctl start rpifan-control
sudo systemctl start rpipower-control

sudo cp ~/plex-pi/scripts/update /etc/cron.daily
sudo chmod +x /etc/cron.daily/update

exfat-utils ntfs-3g

UUID="C0D4-CE3A" TYPE="exfat"
UUID="8482FAAD82FAA2BA" TYPE="ntfs"
sudo blkid

## Install required packages

sudo apt install -y apt-transport-https binutils exfat-utils git libchromaprint-tools libjna-java libjna-jni libmediainfo0v5 mediainfo ntfs-3g software-properties-common p7zip-full locate

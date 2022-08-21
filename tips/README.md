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

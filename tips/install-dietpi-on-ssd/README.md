# Install DietPi SSD with a Raspberry Pi 4

## Download Raspberry Pi Imager

Goto [Raspberry Pi Download page](https://www.raspberrypi.com/software/ 'Raspberry Pi Download page')

or with Ubuntu:

```
sudo apt install rpi-imager
```

The main purpose of this app is to prepare a SD card for a Raspberry Pi. You can choose among a long list of OS sorted by categories.
It avoids you to search for the last version of an OS, download it and use Balena Etcher to push the OS to the SD card (even if it's perfectly fine!).
You can also use utility images to install a bootloader different from the default one, and this is what we're looking for!

## Run Raspberry Pi Imager and prepare the card

### Choose the OS

The first thing you have to do is to choose the kind of OS.
So, click on "Choose OS"

![Choose OS](images/1.png?raw=true 'Choose OS')

Then choose "**Misc utility images**"

![Choose Misc utility images](images/2.png?raw=true 'Choose Misc utility images')

Then choose "**Bootloader**"

![Choose Bootloader](images/3.png?raw=true 'Choose Bootloader')

And finally, choose "**USB Boot**"

![Choose USB Boot](images/4.png?raw=true 'Choose USB Boot')

## Choose the storage

Now, we have to choose the "**Storage**" to have the utility installed into the SD card.

![Choose Storage](images/5.png?raw=true 'Choose Storage')

Be carefull, if you choose a wrong storage, you'll lose all the data in it.

## Write the OS to the SD Card

Finally, after agreeing on the warning, write the OS into the SD Card.

![Write the OS to the SD Card](images/5.png?raw=true 'Write the OS to the SD Card')

## Write the bootloader from the SD card to the Raspberry Pi

Take your freshly installed SD Card, insert it into your Raspberry Pi and boot it.
Wait at least one minute and shutdown your RPI.

## Conclusion

Your RPI is ready to boot to an external USB disk instead of the classic SD Card.

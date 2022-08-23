# plex-pi

# The full setup of Plex Media Server on a RPi

Plex Media Server on a Raspberry Pi with a script to allow an easy install.

- Install Plex Media Server and configure it

## Why

### Why an external SSD disk instead of an SD card?

## Installation

```
bash -c "$(wget -qO - https://raw.githubusercontent.com/mrworf/plexupdate/master/extras/installer.sh)"
```

## Options

## FAQ

### Any tips?

Yes, plenty [here](tips/README.md)!

## TODO LIST:

- [x] Start the documentation
- [x] Add useless point in this todo
- [x] Boot on an external SSD disk instead of the SD card
- [x] Install Plex Media Server and configure it
- [x] Install the script from Geekworm to control the fan speed
- [x] Install the script from Geekworm to use the button to shut it down
- [x] Add auto-update of the OS and Plex
- [ ] Create an installer file to do that automatically
- [ ] Study https://github.com/l3uddz/plex_autoscan
- [ ] Study https://github.com/wnielson/Plex-Remote-Transcoder
- [ ] Study https://github.com/maykar/plex_assistant
- [ ] Backup the Plex conf and database to S3 to allow a quick restore of the library
- [ ] Backup the Plex conf and database to the unused SD card to allow a quick restore of the library

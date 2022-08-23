# Update RPi eeprom

sudo apt update && sudo apt full-upgrade -y
sudo RPI_REBOOT=1 rpi-update
sudo reboot
sudo rpi-eeprom-update -d -a
sudo reboot

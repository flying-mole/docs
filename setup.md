# Raspberry Pi

Télécharger Raspbian Jessie depuis: https://www.raspberrypi.org/downloads/raspbian/

> NB: si vous avez Wheezy, faire la mise à jour :
```bash
# Replace wheezy by jessie in update sources
sudo sed -i /deb/s/wheezy/jessie/g /etc/apt/sources.list
sudo sed -i /deb/s/wheezy/jessie/g /etc/apt/sources.list.d/*.list
# Do the upgrade
sudo apt-get update
sudo apt-get dist-upgrade
```
> Source: http://raspberrypi.stackexchange.com/a/27860

# Wifi

```bash
sudo apt-get install hostapd
```

La version fournie de `hostapd` ne supporte pas la carte Wifi.

```bash
wget http://adafruit-download.s3.amazonaws.com/adafruit_hostapd_14128.zip
unzip adafruit_hostapd_14128.zip
sudo mv /usr/sbin/hostapd /usr/sbin/hostapd.ORIG 
sudo mv hostapd /usr/sbin
sudo chmod 755 /usr/sbin/hostapd
```

Source : https://learn.adafruit.com/downloads/pdf/setting-up-a-raspberry-pi-as-a-wifi-access-point.pdf

# Node

Notre HUD required Node >= 4.0.

* Pour un Raspberry Pi 1 (B ou B+): l'installer depuis https://github.com/nathanjohnson320/node_arm (ou http://fs.emersion.fr/public/node/)
* Pour un Raspberry Pi 2: l'installer depuis https://github.com/nodesource/distributions

Source : https://github.com/nathanjohnson320/node_arm/issues/10

# Servoblaster

```bash
# Install servoblaster
git clone /github.com/richardghirst/PiBits.git
cd PiBits/ServoBlaster/user
make
sudo make install

# Check that servoblaster is up and running
ls /dev/servoblaster
```

Source : https://github.com/richardghirst/PiBits/tree/master/ServoBlaster

Pour Raspberry Pi 2 : voir https://github.com/richardghirst/PiBits/issues/43

# I2C

Voir https://learn.adafruit.com/adafruits-raspberry-pi-lesson-4-gpio-setup/configuring-i2c

```bash
# Enable I2C support
sudo apt-get install i2c-tools
sudo raspi-config # Advanced Options > Enable I2C
sudo reboot

# Check that I2C is enabled on boot
sudo nano /etc/modules
# Add i2c-bcm2708 and i2c-dev at the end of the file if not already here

# Allow i2c to be used without root privileges
sudo usermod -G i2c pi
# Then logout and login again

# Test I2C
sudo i2cdetect -y 1
```

# Camera

```bash
sudo usermod -a -G video pi
# Then logout and login again
```

# Raspberry Pi

Il nous faut une Debian jessie (stable), mais la version par défaut de Raspbian est wheezy (oldstable). Une fois Raspbian installé, faire la mise à jour :

```bash
# Replace wheezy by jessie in update sources
sudo sed -i /deb/s/wheezy/jessie/g /etc/apt/sources.list
sudo sed -i /deb/s/wheezy/jessie/g /etc/apt/sources.list.d/*.list

# Do the upgrade
sudo apt-get update
sudo apt-get dist-upgrade
```

Source: http://raspberrypi.stackexchange.com/a/27860

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

Notre HUD required Node >= 4.0. L'installer depuis https://github.com/nathanjohnson320/node_arm/ (ou http://fs.emersion.fr/public/node/).

Source : https://github.com/nathanjohnson320/node_arm/issues/10

# Servoblaster

Voir https://github.com/richardghirst/PiBits/tree/master/ServoBlaster

# I2C

Voir https://learn.adafruit.com/adafruits-raspberry-pi-lesson-4-gpio-setup/configuring-i2c

```
# Allow i2c to be used without root privileges
sudo usermod -G i2c pi
# Then logout and login again.
```

# Camera

```bash
sudo usermod -a -G video pi
# Then logout and login again.
```

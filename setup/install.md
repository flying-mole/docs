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

> Pour avoir uniquement le strict nécessaire : utiliser https://github.com/debian-pi/raspbian-ua-netinst
>
> Il faudra installer quand même quelques trucs :
```bash
sudo apt-get install python make git g++
```

# Wifi

Source : https://learn.adafruit.com/downloads/pdf/setting-up-a-raspberry-pi-as-a-wifi-access-point.pdf

## hostapd

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

Modifier `/etc/hostapd/hostapd.conf`:
```
interface=wlan0
driver=rtl871xdrv # Or nl80211
ssid=flying-mole
hw_mode=g
channel=6
macaddr_acl=0
auth_algs=1
ignore_broadcast_ssid=0
wpa=2
wpa_passphrase=raspberry
wpa_key_mgmt=WPA-PSK
wpa_pairwise=TKIP
rsn_pairwise=CCMP
```

(Pas de ligne vide au début/à la fin du fichier !)

Modifier `/etc/default/hostapd`:
```
DEAMON_CONF="/etc/hostapd/hostapd.conf"
```

## isc-dhcp-server

```bash
sudo apt-get install isc-dhcp-server
```

Modifier `/etc/dhcp/dhcpd.conf`:
```
#option domain-name "example.org";
#option domain-name-servers ns1.example.org ns2.example.org;
authoritative;

subnet 192.168.3.0 netmask 255.255.255.0 {
	range 192.168.3.10 192.168.3.50;
	option broadcast-address 192.168.3.255;
	option routers 192.168.3.1;
	default-lease-time 600;
	max-lease-time 7200;
}
```

Modifier `/etc/default/isc-dhcp-server`:
```
INTERFACES="wlan0"
```

## IP statique

Modifier `/etc/network/interfaces`:
```
allow-hotplug wlan0

iface wlan0 inet static
	address 192.168.3.1
	netmask 255.255.255.0
```

Modifier `/etc/sysctl.conf`:
```
net.ipv4.ip_forward=1
```

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
sudo raspi-config # Enable camera
sudo reboot

# Allow camera to be used without root privileges
sudo usermod -a -G video pi
# Then logout and login again
```

# HUD

```bash
git clone https://github.com/flying-mole/hud.git
cd hud
npm install
```

# Matériel

Voir [`hardware/`](../hardware/) pour des documents sur le matériel utilisé.

* Brancher la clef Wifi sur un des ports USB
* Brancher le capteur MPU6050 et les ESC :

---
GPIO | Composant | Pin du composant
---
3V3 | MPU6050 | VCC
2 (SDA) | MPU6050 | SDA
3 (SCL) | MPU6050 | SCL
GND | MPU6050 | GND
4 | ESC #0 | Entrée (jaune)
4 | ESC #0 | Entrée (jaune)

Bibliographie
=============

Exemples de quadcopters
-----------------------

* https://code.google.com/p/owenquad/ et https://ghowen.me/build-your-own-quadcopter-autopilot/
* http://www.instructables.com/id/Autonomous-Cardboard-Rasberry-Pi-Controlled-Quad/
* http://www.raspberrypi.org/forums/viewtopic.php?f=37&t=35746
* Bicoptère à bascule : https://www.youtube.com/watch?v=2AepI7qITgs
* http://www.hobbytronics.co.uk/projects/quadcopter

Raspberry Pi
------------

* Rspbian temps-réel : http://docs.emlid.com/Navio-APM/configuring-raspberry-pi/

Gyromètre/accéléromètre
-----------------------

* Bus I2C : http://en.wikipedia.org/wiki/I%C2%B2C
* Configuration : 
 * http://mchobby.be/wiki/index.php?title=Rasp-Hack-GPIO_Configurer_I2C
 * https://learn.adafruit.com/adafruits-raspberry-pi-lesson-4-gpio-setup/configuring-i2c
 * http://www.advamation.com/knowhow/raspberrypi/rpi-i2c-bug.html
* Lecture : https://lilyhack.wordpress.com/2014/07/25/raspberrypi-reading-i2c-inputs-using-c/
* Travail déjà réalisé :
 * Librairie : https://github.com/emersion/node-i2c-mpu6050
 * Serveur de test : https://github.com/emersion/node-mpu6050-server
* Code analogue en C++ : https://github.com/richardghirst/PiBits/tree/master/MPU6050-Pi-Demo
* http://forum.arduino.cc/index.php?topic=255033.0
* http://raspberrypi.znix.com/hipidocs/topic_i2cbus_2.htm
* http://dsscircuits.com/sale/product/dssc0107
* Librairie Arduino pour MPU6050 : http://www.i2cdevlib.com/docs/html/class_m_p_u6050.html
* Explications sur lmes grandeurs physiques mesurées : http://www.instructables.com/id/Accelerometer-Gyro-Tutorial/step1/The-Accelerometer/

Asservissement
--------------

* http://fr.wikipedia.org/wiki/R%C3%A9gulateur_PID et http://en.wikipedia.org/wiki/PID_controller
* http://blog.oscarliang.net/quadcopter-pid-explained-tuning/
* Librairie Node.js : https://www.npmjs.com/package/node-pid-controller

Moteurs, ESC
------------

* http://fr.wikipedia.org/wiki/Moteur_sans_balais
* Contrôle des ESC via les GPIO du Rpi : http://stephane.lavirotte.com/perso/rov/esc_brushless_raspberry.html
* Doc de ServoBlaster : https://github.com/richardghirst/PiBits/blob/master/ServoBlaster/README.txt
* http://raspberrypi.stackexchange.com/questions/18254/can-i-control-this-esc-brushless-motor-with-a-raspberry-pi-and-or-arduino
* https://solenerotech1.wordpress.com/2013/09/09/tutorialhow-to-control-a-brushless-motor-with-raspberry-pi/
* Travail déjà réalisé : https://github.com/emersion/node-servoblaster

Hélices
-------

* http://www.lavionnaire.fr/MecaHelices.php
* http://www.dronelis.com/choix-des-moteurs-et-des-helices-pour-un-drone/
* http://blog.oscarliang.net/how-to-choose-motor-and-propeller-for-quadcopter/

Batterie
--------

* Pour le Raspberry Pi :
 * Moyenne (140g, 7h) : http://www.adafruit.com/products/1565
 * Grosse (300g, 15h) : https://www.adafruit.com/product/1566
* Pour les moteurs : TODO

Wi-Fi
-----

* Antenne USB (requiert une bonne alimentation) : http://www.adafruit.com/products/1030
* Raspberry Pi comme point d'accès Wi-Fi : 
 * https://learn.adafruit.com/downloads/pdf/setting-up-a-raspberry-pi-as-a-wifi-access-point.pdf
 * http://elinux.org/RPI-Wireless-Hotspot

Accessoires
-----------

* Camera 1080p pour Raspberry Pi : http://www.adafruit.com/product/1367
* http://www.raspberrypi-spy.co.uk/2013/05/capturing-hd-video-with-the-pi-camera-module/

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

* Raspbian temps-réel : http://docs.emlid.com/Navio-APM/configuring-raspberry-pi/

IMU
---

IMU = Inertial Measurement Unit (ici, le MPU6050 qui fait gyromètre et accéléromètre)

* Bus I2C : http://en.wikipedia.org/wiki/I%C2%B2C
* Configuration : 
 * http://mchobby.be/wiki/index.php?title=Rasp-Hack-GPIO_Configurer_I2C
 * https://learn.adafruit.com/adafruits-raspberry-pi-lesson-4-gpio-setup/configuring-i2c
 * http://www.advamation.com/knowhow/raspberrypi/rpi-i2c-bug.html
* Datasheet du MPU6050 : https://www.cdiweb.com/datasheets/invensense/MPU-6050_DataSheet_V3%204.pdf
* Lecture : https://lilyhack.wordpress.com/2014/07/25/raspberrypi-reading-i2c-inputs-using-c/
* Travail déjà réalisé :
 * Librairie : https://github.com/emersion/node-i2c-mpu6050
 * Serveur de test : https://github.com/emersion/node-mpu6050-server
* Code analogue en C++ : https://github.com/richardghirst/PiBits/tree/master/MPU6050-Pi-Demo
* http://forum.arduino.cc/index.php?topic=255033.0
* http://raspberrypi.znix.com/hipidocs/topic_i2cbus_2.htm
* ~~http://dsscircuits.com/sale/product/dssc0107~~
* Librairie Arduino pour MPU6050 : http://www.i2cdevlib.com/docs/html/class_m_p_u6050.html
* Explications sur lmes grandeurs physiques mesurées : http://www.instructables.com/id/Accelerometer-Gyro-Tutorial/step1/The-Accelerometer/

Filtres pour IMU
----------------
* Quaternion to Euler : https://en.wikipedia.org/wiki/Conversion_between_quaternions_and_Euler_angles
* Quaternions en maths : http://www.euclideanspace.com/maths/algebra/realNormedAlgebra/quaternions/index.htm
* DMP aec une Arduino : http://www.geekmomprojects.com/mpu-6050-dmp-data-from-i2cdevlib/
* Explications générales sur le MPU6050 : http://www.cs.unca.edu/~bruce/Fall13/360/IMU_Wk8.pptx

Asservissement
--------------

* http://fr.wikipedia.org/wiki/R%C3%A9gulateur_PID et http://en.wikipedia.org/wiki/PID_controller
* http://blog.oscarliang.net/quadcopter-pid-explained-tuning/
* http://robot-kingdom.com/pid-controller-tutorial-for-robots/
* Librairie Node.js utilisée : https://github.com/emersion/node-pid-controller

* http://www.linushelgesson.se/tag/kalman-filter/
* http://challenge.toradex.com/projects/10078-autopilot-quadcopter
* ~~http://robotics.stackexchange.com/questions/2244/how-to-know-the-desired-orientation-of-a-quadcopter~~
* http://technicaladventure.blogspot.fr/2012/09/quadcopter-stabilization-control-system.html
* http://blog.pistuffing.co.uk/tag/pid/page/8/

* Exemple de programmation d'un PID : http://blog.solutions-cubed.com/pid-motor-control-with-an-arduino/

Moteurs, ESC
------------

* http://fr.wikipedia.org/wiki/Moteur_sans_balais
* Contrôle des ESC via les GPIO du Rpi : http://stephane.lavirotte.com/perso/rov/esc_brushless_raspberry.html
* Doc de ServoBlaster : https://github.com/richardghirst/PiBits/blob/master/ServoBlaster/README.txt
* http://raspberrypi.stackexchange.com/questions/18254/can-i-control-this-esc-brushless-motor-with-a-raspberry-pi-and-or-arduino
* https://solenerotech1.wordpress.com/2013/09/09/tutorialhow-to-control-a-brushless-motor-with-raspberry-pi/
* Travail déjà réalisé : https://github.com/emersion/node-servoblaster
* Notice ESC : http://www.absolu-modelisme.com/media/downloadable/files/notices//n/o/notice_pro-tronik_controleurs_esc.pdf

Hélices
-------

* http://www.dronelis.com/choix-des-moteurs-et-des-helices-pour-un-drone/
* http://blog.oscarliang.net/how-to-choose-motor-and-propeller-for-quadcopter/

Batterie
--------

* Pour le Raspberry Pi :
 * Moyenne (140g, 7h) : http://www.adafruit.com/products/1565
 * Grosse (300g, 15h) : https://www.adafruit.com/product/1566
 * Batterie lipo black lithium 35C 3300mah 11,1V : http://www.absolu-modelisme.com/black-lithium-11-1v-3300mah-35.html
* Pour les moteurs : nope
* Monitor battery usage : http://raspi.tv/2013/controlled-shutdown-duration-test-of-pi-model-a-with-2-cell-lipo

Wi-Fi
-----

* Antenne USB (requiert une bonne alimentation) : http://www.adafruit.com/products/1030
* Raspberry Pi comme point d'accès Wi-Fi : 
 * https://learn.adafruit.com/downloads/pdf/setting-up-a-raspberry-pi-as-a-wifi-access-point.pdf
 * http://elinux.org/RPI-Wireless-Hotspot

Camera
-----------

* Camera 1080p pour Raspberry Pi : http://www.adafruit.com/product/1367
* http://www.raspberrypi-spy.co.uk/2013/05/capturing-hd-video-with-the-pi-camera-module/
* gstreamer avec encodage matériel :
  * http://pi.gbaman.info/?p=150
  * http://www.onepitwopi.com/raspberry-pi/gstreamer-1-2-on-the-raspberry-pi/

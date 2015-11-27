On suppose le Raspberry Pi dans la configuration décrite dans [le guide d'installation](install.md).

* Rejoindre le réseau Wifi du Raspberry Pi (réseau `flying-mole` avec le mot de passe `raspberry` par défaut)
* Se connecter en SSH au Raspberry Pi : `ssh pi@192.168.3.1` (mot de passe par défaut : `raspberry`)
* Lancer le [HUD](https://github.com/flying-mole/hud) : `cd hud && node .` (le stopper avec <kbd>Ctrl</kbd> + <kbd>C</kbd>)
* Se connecter au HUD avec un navigateur Web à l'addresse http://192.168.3.1:3000
* Fly!

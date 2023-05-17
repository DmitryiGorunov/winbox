То же самое репо, но почищено от хохлизма. 
Для тех, кому противна жолтоватоблакитная тряпка =)


Winbox
======

Snap package with winbox

[![winbox](https://snapcraft.io/winbox/badge.svg)](https://snapcraft.io/winbox) [![winbox](https://snapcraft.io/winbox/trending.svg?name=0)](https://snapcraft.io/winbox)
Building
--------

To build the snap yourself, clone this github repo and run snapcraft in the top of the source tree:

```
sudo snap install snapcraft --classic
git clone https://github.com/DmitryiGorunov/winbox.git
cd winbox
snapcraft
```


Fixing neighbors discovery 
------------------------------

#### UFW
```
sudo ufw allow 5678/udp
```
Fix found on https://forum.mikrotik.com/viewtopic.php?t=175420#p941967

#### Firewalld
```
sudo firewall-cmd --permanent --new-service=winbox-neighbors
sudo firewall-cmd --permanent --service=winbox-neighbors --add-port=5678/udp
sudo firewall-cmd --zone=trusted --add-service=winbox-neighbors --permanent 
sudo firewall-cmd --reload
```

### Other firewall
allow UDP 5678
> NOTE: NOT ALLOW THIS PORT WHEN USING GLOBAL NETWORK ACCESS

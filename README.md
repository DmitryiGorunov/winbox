Winbox
======

Snap package with winbox

[![winbox](https://snapcraft.io/winbox/badge.svg)](https://snapcraft.io/winbox) [![winbox](https://snapcraft.io/winbox/trending.svg?name=0)](https://snapcraft.io/winbox)

[![SWUbanner](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/banner-direct.svg)](https://github.com/vshymanskyy/StandWithUkraine/blob/main/docs/README.md)

Installation
------------

[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-black.svg)](https://snapcraft.io/winbox)

Run in terminal `sudo snap install winbox`

Details about installing on various distributions that do not come with snapd out of the box can be found at the bottom of https://snapcraft.io/winbox

Bug reporting
-------------

Please create issue on GitHub https://github.com/panaceya/winbox/issues/new

Building
--------

To build the snap yourself, clone this github repo and run snapcraft in the top of the source tree:

```
sudo snap install snapcraft --classic
git clone https://github.com/panaceya/winbox.git
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

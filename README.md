# aic800
TND-USB-U2 - 2604:0014 Tenda AIC8800DC

https://www.tendacn.com/download/detail-5294.html

https://github.com/radxa-pkg/aic8800/tree/main/src/USB/driver_fw/drivers/aic_btusb

```
[aic800]

dpkg install the linux headers from 
https://github.com/markbirss/linux-6.1.99/releases/tag/1

https://github.com/markbirss/linux-6.1.99/raw/refs/heads/main/linux-headers-6.1.99_6.1.99-3_armhf.deb

sudo apt -y update; sudo apt -y install build-essential make cmake git network-manager

git clone https://github.com/markbirss/aic800.git
cd aic800/
make -j3
sudo make install
sudo cp aic.rules /etc/udev/rules.d/
cd /
sudo tar xvfz /home/lyra/aic800/firmware.tar.gz
sudo reboot

nmcli dev wifi list

```


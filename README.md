# aic800
TND-USB-U2 - 2604:0014 Tenda AIC8800DC

https://www.tendacn.com/download/detail-5294.html

https://github.com/radxa-pkg/aic8800/tree/main/src/USB/driver_fw/drivers/aic_btusb

```
Luckfox Lyra with Wireless
[aic800]

#dpkg install the linux headers from 
#https://github.com/markbirss/linux-6.1.99/releases/tag/1

wget -c https://github.com/markbirss/linux-6.1.99/raw/refs/heads/main/linux-headers-6.1.99_6.1.99-3_armhf.deb
dpkg -i linux-headers-6.1.99_6.1.99-3_armhf.deb

sudo apt -y update; sudo apt -y install build-essential make cmake git network-manager
sudo apt -y update; sudo apt -y install eject network-manager build-essential git make cmake iw wireless-tools rfkill

su lyra
cd ~/

git clone https://github.com/markbirss/aic800.git
cd aic800/
make -j3
sudo make install
sudo cp aic.rules /etc/udev/rules.d/
cd /
sudo tar xvfz /home/lyra/aic800/firmware.tar.gz
sudo reboot

adb shell nmcli dev wifi list

```

```
requires installation of network-manger and

cat <<EOF > /etc/netplan/01-network-manager-all.yaml
network:
  version: 2
  renderer: NetworkManager
EOF

root@luckfox:~# cat /sys/firmware/devicetree/base/model
Luckfox Lyra Zero W

root@luckfox:~# 

/media/user/storage/sdk$ adb push luckfox-config.latest /usr/bin/luckfox-config
luckfox-config.latest: 1 file pushed, ...d. 169.3 MB/s (102478 bytes in 0.001s)

```



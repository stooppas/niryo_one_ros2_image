# Niryo One Ros2 Image
The Raspberry Pi image for my ROS2 Port

This image doesn't automatically launch the Niryo One Driver. 

# How to install
- Download image from [here](https://pamisto-my.sharepoint.com/:u:/g/personal/pascal_stoop_pasto_ch/EWUDUtK2NXNOqs5qzQERD3oBsJbtyU_BScugnc-5wzxOAg?e=ktAvf8)
- Flash .img file onto sd card
- (If needed change hostname in /etc/hostname and in /boot/firmware/user-data)
- Add Network Connection to ```/etc/netplan/50-cloud-init.cfg```

# How to build your own
- Install 64 Bit Ubuntu 22.04 Server image
- Install Network-Manager with sudo ``apt-get install network-manager``
- Set Network-Manager as default renderer by replacing ```networkd``` with ```NetworkManager``` in ```/etc/netplan/50-cloud-init.cfg```
- Add udev files from this repo to /etc/udev/rules.d
- Add following line to config.txt: ```dtparam=uart0=on```
- Remove ```console=serial0``` from cmdline.txt
- Run ```rosdep install --from-paths src --ignore-src -y```
- Install following package with apt:  
  - ros-humble-gripper-controllers


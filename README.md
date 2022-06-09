# Niryo One Ros2 Image
The Raspberry Pi image for my ROS2 Port

This image doesn't automatically launch the Niryo One Driver. 

# How to install
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
- Install following packages with apt:  
  - python3-rpi.gpio 
  - ros-humble-ros2-controllers
  - ros-humble-ros-humble-gripper-controllers
- Run ```rosdep install --from-paths src --ignore-src -y```

# Niryo One Ros2 Image
The Raspberry Pi image for my ROS2 Port

# How to install


# How to build your own
- Install 64 Bit Ubuntu 22.04 Server image
- Install Network-Manager with sudo apt-get install network-manager
  - Set Network-Manager as default renderer
- Add udev files from this repo to /etc/udev/rules.d
- Add following lines to usercfg.txt:
  init_uart_clock=16000000
  dtoverlay=pi3-disable-bt
  dtparam=spi=on
  dtparam=i2c1=on
  dtparam=i2c_arm=on
  dtparam=uart0=on

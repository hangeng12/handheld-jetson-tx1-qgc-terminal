# Jetson TX1 System Information

This file was generated from the target Jetson TX1.

```text
== date ==
2026-06-02T15:52:23+08:00

== os-release ==
NAME="Ubuntu"
VERSION="20.04.6 LTS (Focal Fossa)"
ID=ubuntu
ID_LIKE=debian
PRETTY_NAME="Ubuntu 20.04.6 LTS"
VERSION_ID="20.04"
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
VERSION_CODENAME=focal
UBUNTU_CODENAME=focal

== kernel ==
Linux ubuntu 4.9.337-tegra #1 SMP PREEMPT Mon Nov 4 23:41:41 PST 2024 aarch64 aarch64 aarch64 GNU/Linux

== l4t ==
# R32 (release), REVISION: 7.6, GCID: 38171779, BOARD: t210ref, EABI: aarch64, DATE: Tue Nov  5 07:46:14 UTC 2024

== rootfs ==
/dev/mmcblk2p1 /      ext4
文件系统        容量  已用  可用 已用% 挂载点
/dev/mmcblk2p1   59G   21G   35G   38% /

== memory ==
              总计         已用        空闲      共享    缓冲/缓存    可用
内存：       3.9Gi       1.1Gi       1.3Gi        14Mi       1.5Gi       2.7Gi
交换：       1.9Gi          0B       1.9Gi

== services ==
running
  UNIT LOAD ACTIVE SUB DESCRIPTION
0 loaded units listed.

== held l4t packages ==
nvidia-l4t-3d-core
nvidia-l4t-apt-source
nvidia-l4t-bootloader
nvidia-l4t-camera
nvidia-l4t-configs
nvidia-l4t-core
nvidia-l4t-cuda
nvidia-l4t-firmware
nvidia-l4t-gputools
nvidia-l4t-graphics-demos
nvidia-l4t-gstreamer
nvidia-l4t-init
nvidia-l4t-initrd
nvidia-l4t-jetson-io
nvidia-l4t-kernel
nvidia-l4t-kernel-dtbs
nvidia-l4t-kernel-headers
nvidia-l4t-libvulkan
nvidia-l4t-multimedia
nvidia-l4t-multimedia-utils
nvidia-l4t-oem-config
nvidia-l4t-tools
nvidia-l4t-wayland
nvidia-l4t-weston
nvidia-l4t-x11
nvidia-l4t-xusb-firmware

== gpio ==
crw-rw---- 1 root gpio 254, 0 6月   2 13:38 /dev/gpiochip0
crw-rw---- 1 root gpio 254, 1 6月   2 13:38 /dev/gpiochip1
crw-rw---- 1 root gpio 254, 2 6月   2 13:38 /dev/gpiochip2
crw-rw---- 1 root gpio 254, 3 6月   2 13:38 /dev/gpiochip3
gpiochip0 [tegra-gpio] (256 lines)
gpiochip1 [tca9539] (16 lines)
gpiochip2 [tca9539] (16 lines)
gpiochip3 [max77620-gpio] (8 lines)
```

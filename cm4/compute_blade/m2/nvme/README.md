# NVMe Benchmark Method

* `lsblk` to find device name.
* `lspci -vvv -s 01:00.0` to collect drive info.
* `fdisk -l /dev/nvme0n1` to collect device info.
* `fdisk /dev/nvme0n1` to partition disk.
  * `d` to delete partition(s).
  * `n` to create partition(s).
  * `w` to write (save) and exit.
* `mkfs.ext4 -F /dev/nvme0n1` to format disk.
* `mkdir /mnt/sda1` to create mount point.
* `mount /dev/nvme0n1 /mnt/sda1` to mount disk.
* `df -Th /dev/nvme0n1` to confirm filesystem and mount.
* `curl -O https://raw.githubusercontent.com/geerlingguy/pi-cluster/master/benchmarks/disk-benchmark.sh` to download Jeff Geerling's disk benchmark script.
* `chmod +x disk-benchmark.sh` to enable execution.
* `DEVICE_UNDER_TEST=/dev/DEVICE_NAME ./disk-benchmark.sh` to run benchmark.
* `curl -O https://raw.githubusercontent.com/TheRemote/PiBenchmarks/master/Storage.sh` to download pibenchmarks.com's benchmark script.
* `chmod +x Storage.sh` to enable execution.
* `./Storage.sh` to run benchmark.

# NVMe Boot Method

ICY DOCK MB104U-1SMB w/ Realtek RTL9210B
Raspberry Pi Imager v1.7.3
Set options:
  set name
  enable ssh w/ password authentication
  set username and password
  set locale

sudo cu -l /dev/tty.usbserial-0001 -s 115200

echo -e "dtoverlay=disable-bt\ndtoverlay=disable-wifi\nenable_uart=1\nuart_2ndstage=1\n$(cat /Volumes/boot/config.txt)" > /Volumes/boot/config.txt && cat /Volumes/boot/config.txt

sed -i '' 's/quiet //g' /Volumes/boot/cmdline.txt && cat /Volumes/boot/cmdline.txt

diskutil unmountdisk /dev/disk5 && diskutil eject /dev/disk5

cmdline.txt
console=serial0,115200 console=tty1 root=PARTUUID=21e60f8c-02 rootfstype=ext4 fsck.repair=yes rootwait init=/usr/lib/raspberrypi-sys-mods/firstboot systemd.run=/boot/firstrun.sh systemd.run_success_action=reboot systemd.unit=kernel-command-line.target

config.txt
# For more options and information see
# http://rpf.io/configtxt
# Some settings may impact device functionality. See link above for details

dtoverlay=disable-bt
dtoverlay=disable-wifi
enable_uart=1
uart_2ndstage=1

# uncomment if you get no picture on HDMI for a default "safe" mode
#hdmi_safe=1

# uncomment the following to adjust overscan. Use positive numbers if console
# goes off screen, and negative if there is too much border
#overscan_left=16
#overscan_right=16
#overscan_top=16
#overscan_bottom=16

# uncomment to force a console size. By default it will be display's size minus
# overscan.
#framebuffer_width=1280
#framebuffer_height=720

# uncomment if hdmi display is not detected and composite is being output
#hdmi_force_hotplug=1

# uncomment to force a specific HDMI mode (this will force VGA)
#hdmi_group=1
#hdmi_mode=1

# uncomment to force a HDMI mode rather than DVI. This can make audio work in
# DMT (computer monitor) modes
#hdmi_drive=2

# uncomment to increase signal to HDMI, if you have interference, blanking, or
# no display
#config_hdmi_boost=4

# uncomment for composite PAL
#sdtv_mode=2

#uncomment to overclock the arm. 700 MHz is the default.
#arm_freq=800

# Uncomment some or all of these to enable the optional hardware interfaces
#dtparam=i2c_arm=on
#dtparam=i2s=on
#dtparam=spi=on

# Uncomment this to enable infrared communication.
#dtoverlay=gpio-ir,gpio_pin=17
#dtoverlay=gpio-ir-tx,gpio_pin=18

# Additional overlays and parameters are documented /boot/overlays/README

# Enable audio (loads snd_bcm2835)
dtparam=audio=on

# Automatically load overlays for detected cameras
camera_auto_detect=1

# Automatically load overlays for detected DSI displays
display_auto_detect=1

# Enable DRM VC4 V3D driver
dtoverlay=vc4-kms-v3d
max_framebuffers=2

# Run in 64-bit mode
arm_64bit=1

# Disable compensation for displays with overscan
disable_overscan=1

[cm4]
# Enable host mode on the 2711 built-in XHCI USB controller.
# This line should be removed if the legacy DWC2 controller is required
# (e.g. for USB device mode) or if USB support is not required.
otg_mode=1

[all]

[pi4]
# Run as fast as firmware / board allows
arm_boost=1

[all]

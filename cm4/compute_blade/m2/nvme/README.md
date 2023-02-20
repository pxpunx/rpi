# NVMe Benchmark

## Method

* `lsblk` to find device name.
* `lspci -vvv -s 01:00.0` to collect device info.
* `fdisk -l /dev/nvme0n1` to collect disk info.
* `fdisk /dev/nvme0n1` to partition disk.
  * `d` to delete partition(s).
  * `n` to create partition(s).
  * `w` to write (save) and exit.
* `mkfs.ext4 -F /dev/nvme0n1` to format disk.
* `mkdir /mnt/sda1` to create mount point.
* `mount /dev/nvme0n1 /mnt/sda1` to mount disk.
* `df -Th /dev/nvme0n1` to confirm filesystem and mount.
* `curl -O https://raw.githubusercontent.com/geerlingguy/pi-cluster/master/benchmarks/disk-benchmark.sh` to download [Jeff Geerling's](https://www.jeffgeerling.com/) benchmark script.
* `chmod +x disk-benchmark.sh` to enable execution.
* `DEVICE_UNDER_TEST=/dev/nvme0n1 ./disk-benchmark.sh` to run benchmark.
* `curl -O https://raw.githubusercontent.com/TheRemote/PiBenchmarks/master/Storage.sh` to download [pibenchmarks.com's](https://pibenchmarks.com) benchmark script.
* `chmod +x Storage.sh` to enable execution.
* `./Storage.sh /dev/nvme0n1` to run benchmark.

# NVMe Boot Imaging

NVMe SSDs can be imaged the same way you'd image a microSD card.

* **OS:** macOS Ventura 13.1
* **Adapter:** ICY DOCK MB104U-1SMB w/ Realtek RTL9210B
* **Tool:** Raspberry Pi Imager v1.7.3
  * Options:
    * Set name.
    * Enable SSH w/ password authentication.
    * Set username and password.
    * Set locale.

I used the ICY DOCK adapter and the official Raspberry Pi Imager to image the M.2 NVMe SSD with Raspberry Pi OS Lite (64-bit).

> Note: The CM4 8GB Lite I used required a bootloader update to enable NVMe boot. Update instructions are outlined in the **Enable NVMe Boot** section below.

## Options

I made some modifications to `/boot/config.txt` and `/boot/cmdline.txt`.

Add options to `/boot/config.txt`:

```
echo -e "dtoverlay=disable-bt\ndtoverlay=disable-wifi\nenable_uart=1\nuart_2ndstage=1\n$(cat /Volumes/boot/config.txt)" > /Volumes/boot/config.txt && cat /Volumes/boot/config.txt
```

Remove `quiet` from `/boot/cmdline.txt`:

```
sed -i '' 's/quiet //g' /Volumes/boot/cmdline.txt && cat /Volumes/boot/cmdline.txt
```

Unmount and eject disk:

```
diskutil unmountdisk /dev/disk5 && diskutil eject /dev/disk5
```

## Examples

### /boot/config.txt

The full output of `/boot/config.txt` after imaging and options added.

<details>
  <summary>Click here to expand...</summary>
  
  ```
  dtoverlay=disable-bt
  dtoverlay=disable-wifi
  enable_uart=1
  uart_2ndstage=1

  # For more options and information see
  # http://rpf.io/configtxt
  # Some settings may impact device functionality. See link above for details

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
  ```
</details>

### /boot/cmdline.txt

The full output of `/boot/cmdline.txt` after imaging and options added.

```
console=serial0,115200 console=tty1 root=PARTUUID=21e60f8c-02 rootfstype=ext4 fsck.repair=yes rootwait init=/usr/lib/raspberrypi-sys-mods/firstboot systemd.run=/boot/firstrun.sh systemd.run_success_action=reboot systemd.unit=kernel-command-line.target
```

# Enable NVMe Boot

Update the CM4's bootloader via a Compute Blade dev board's USB-C interface.

1. Switch to USB-C mode.
1. Press and hold the nRPIBOOT button.
1. Connect the USB-C port on the Compute Blade to a Linux or macOS-based host computer.
    * You can power the board via USB-C or PoE, but the USB-C port must be connected in either scenario.
1. Wait a few seconds until the board has powered up.
1. Release the nRPIBOOT button.
    * The host computer may prompt you to allow the connection of a new USB device, ex. "BCM2835" - this is the CM4/Compute Blade. Accept the connection.
1. Install `libusb` and `pkg-utils`.
    * Debian: `apt install git libusb-1.0-0-dev pkg-config`
    * macOS: `brew install libusb pkg-utils`
1. `cd usbboot`
1. `make`
    * If you encounter issues with `make`, you may need to install additional packages or troubleshoot further. For example, I had to install `coreutils` to check the sha256 sum.
1. `cd recovery`
1. `nano boot.conf`
1. Set `BOOT_ORDER` to `0xf16` (see example below)
1. Set `BOOT_UART` to `1` (see example below)
1. Save `boot.conf`; Ctrl-X, Y, Enter. 
1. `./update-pieeprom.sh`
1. `cd ../`
1. `sudo ./rpiboot -d recovery` (see example output below)

The update should be complete. Reboot the Compute Blade and it should boot from the attached NVMe SSD.

## Examples

Example `boot.conf`:

```bash
[all]
BOOT_UART=1
WAKE_ON_GPIO=1
POWER_OFF_ON_HALT=0

# Boot Order Codes, from https://www.raspberrypi.com/documentation/computers/raspberry-pi.html#BOOT_ORDER
# Try SD first (1), followed by, USB PCIe, NVMe PCIe, USB SoC XHCI then network
#BOOT_ORDER=0xf25641
BOOT_ORDER=0xf16

# Set to 0 to prevent bootloader updates from USB/Network boot
# For remote units EEPROM hardware write protection should be used.
ENABLE_SELF_UPDATE=1

```

Example `./rpiboot` output:

```
$ sudo ./rpiboot -d recovery
RPIBOOT: build-date Feb 19 2023 version 20221215~105525 864863bc
Loading: recovery/bootcode4.bin
Waiting for BCM2835/6/7/2711...
Loading: recovery/bootcode4.bin
Sending bootcode.bin
Successful read 4 bytes 
Waiting for BCM2835/6/7/2711...
Loading: recovery/bootcode4.bin
Second stage boot server
Loading: recovery/config.txt
File read: config.txt
Loading: recovery/pieeprom.bin
Loading: recovery/pieeprom.bin
Loading: recovery/pieeprom.sig
File read: pieeprom.sig
Loading: recovery/pieeprom.bin
File read: pieeprom.bin
Second stage boot server done
```

Example UART output:

```
Reading EEPROM: 524288
Writing EEPROM
+++++++++++++++++++++++++++*****++++++++++++++++++++++++++++++++++++++++++++++++++*****************************************....*
Verify BOOT EEPROM
Reading EEPROM: 524288
BOOT-EEPROM: UPDATED
```

Example bootloader_version:

```
# vcgencmd bootloader_version
2023/01/11 17:40:52
version 8ba17717fbcedd4c3b6d4bce7e50c7af4155cba9 (release)
timestamp 1673458852
update-time 1676831636
capabilities 0x0000007f
```

# Resources

* Official Compute Blade documentation (WIP)
* [raspberrypi/documentation > NVMe boot](https://github.com/raspberrypi/documentation/blob/develop/documentation/asciidoc/computers/raspberry-pi/boot-nvme.adoc)
* [raspberrypi/usbboot](https://github.com/raspberrypi/usbboot)
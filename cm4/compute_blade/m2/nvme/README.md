Notes from my M.2 SSD tests on the Compute Blade platform.

# Product List

A list of NVMe SSDs tested with the Compute Blade RC2 w/ CM4 8GB Lite (CM4008000). All SSDs work as non-boot disks, but some do not work as boot disks.

| Product                                          | Model              | Capactiy     | Form Factor | Key   | Boot Disk          | Non-Boot Disk      |
|:-------------------------------------------------|:-------------------|:-------------|:------------|:------|:-------------------|:-------------------|
| [Crucial P3](crucial_p3_500.md)                  | CT500P3SSD8        | 500GB        | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [Intel 670p](intel_670p_512.md)                  | SSDPEKNU512GZ      | 512GB        | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [Intel Optane H10](intel_optane_h10_16%2B256.md) | HBRPEKNX0101A      | 16GB + 256GB | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [Intel Optane M10](intel_optane_m10_32.md)       | MEMPEK1J032GAD     | 32GB         | M.2 2280    | M + B | :x:                | :white_check_mark: |
| [Kingston NV2](kingston_nv2_250.md)              | SNV2S/250G         | 250GB        | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [Kingston SNS8154P3](kingston_sns8154p3_256.md)  | RBUSNS8154P3256GJ1 | 256GB        | M.2 2280    | M + B | :white_check_mark: | :white_check_mark: |
| [KIOXIA BG4](kioxia_bg4_128.md)                  | KBG40ZNS128G       | 128GB        | M.2 2230    | M     | :white_check_mark: | :white_check_mark: |
| [Micron 2450](micron_2450_256.md)                | MTFDKBA256TFK      | 256GB        | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [Micron 3400](micron_3400_512.md)                | MTFDKBA512TFH      | 512GB        | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [Patriot P310](patriot_p310_240.md)              | P310P240GM28       | 240GB        | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [PNY CS1030](pny_cs1030_250.md)                  | M280CS1030-250-RB  | 250GB        | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [Samsung 970 EVO](sec_970_evo_500.md)            | MZ-V7E500          | 500GB        | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [Samsumg PM991a](sec_pm991a_256.md)              | TBD                | 256GB        | M.2 2230    | M     | :white_check_mark: | :white_check_mark: |
| [SK hynix BC711](skhynix_bc711_256.md)           | HFM256GD3JX016N    | 256GB        | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [Solidigm P41 Plus](solidigm_p41_plus_512.md)    | SSDPFKNU512GZ      | 512GB        | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [TEAMGROUP MP33](teamgroup_mp33_256.md)          | TM8FP6256G0C101    | 256GB        | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [Toshiba BG3](toshiba_bg3_256.md)                | KBG30ZMS128G       | 256GB        | M.2 2280    | M + B | :white_check_mark: | :white_check_mark: |
| [Transcend 110S](transcend_110s_256.md)          | TS256GMTE110S      | 256GB        | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [WD Black SN770](wd_black_sn770_250.md)          | WDS250G3X0E        | 250GB        | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [WD Blue SN570](wd_blue_sn570_250.md)            | WDS250G3B0C        | 250GB        | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [WD Green SN350](wd_green_sn350_240.md)          | WDS240G2G0C        | 240GB        | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [WD Red SN700](wd_red_sn700_500.md)              | WDS500G1R0C        | 500GB        | M.2 2280    | M     | :white_check_mark: | :white_check_mark: |
| [WD SN520](wd_sn520_256.md)                      | SDAPNUW-256G-1006  | 256GB        | M.2 2280    | M + B | :white_check_mark: | :white_check_mark: |

See individual product details for benchmarks.

Some drives were tested with the use of an [Ableconn M2MN-151M](http://ableconn.com/products_2.php?gid=137) adapter to preserve the Compute Blade's M.2 connector. See product details for adapter use indication.

# NVMe Benchmark

The steps I used to set up each test and collect information. Total power draw while tests were performed was between 4W and 6W on a [USW Pro 24 PoE](https://store.ui.com/collections/unifi-network-switching/products/usw-pro-24-poe) PoE++ (60W) port.

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
* **Adapter:** [ICY DOCK MB104U-1SMB](https://global.icydock.com/product_322.html) w/ [Realtek RTL9210B](https://www.realtek.com/en/products/communications-network-ics/item/rtl9210b-cg)
* **Tool:** Raspberry Pi Imager v1.7.3, v1.7.4
  * Options:
    * Set name.
    * Enable SSH w/ password authentication.
    * Set username and password.
    * Set locale.

I used the ICY DOCK adapter and the official Raspberry Pi Imager to image the M.2 NVMe SSD with Raspberry Pi OS Lite (64-bit).

> :memo: The CM4 8GB Lite I used required a bootloader update to enable NVMe boot. Update instructions are outlined in the **Enable NVMe Boot** section below.

## Options

I made some modifications to `/boot/config.txt` and `/boot/cmdline.txt`. 

NOTE: v1.7.4 switched to `/bootfs`.

Add options to `config.txt`:

```
echo -e "dtoverlay=disable-bt\ndtoverlay=disable-wifi\nenable_uart=1\nuart_2ndstage=1\n$(cat /Volumes/boot/config.txt)" > /Volumes/boot/config.txt && cat /Volumes/boot/config.txt
```

```
echo -e "dtoverlay=disable-bt\ndtoverlay=disable-wifi\nenable_uart=1\nuart_2ndstage=1\n$(cat /Volumes/bootfs/config.txt)" > /Volumes/bootfs/config.txt && cat /Volumes/bootfs/config.txt
```

Remove `quiet` from `cmdline.txt`:

```
sed -i '' 's/quiet //g' /Volumes/boot/cmdline.txt && cat /Volumes/boot/cmdline.txt
```

```
sed -i '' 's/quiet //g' /Volumes/bootfs/cmdline.txt && cat /Volumes/bootfs/cmdline.txt
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

CM4s with a recent version of the bootloader (after July 2021) should be able to boot from NVMe by default. I had to update mine.

The instructions below outline how to update a CM4's bootloader via a Compute Blade dev board's USB-C interface. 

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
1. `sudo ./rpiboot -d recovery` 

Once the update is complete (see output examples below), reboot the Compute Blade and it should boot from the attached NVMe SSD.

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
* [Raspberry Pi Documentation > Raspberry Pi Hardware > NVMe SSD Boot](https://www.raspberrypi.com/documentation/computers/raspberry-pi.html#nvme-ssd-boot) _(same as link below)_
* [raspberrypi/documentation > NVMe SSD Boot](https://github.com/raspberrypi/documentation/blob/develop/documentation/asciidoc/computers/raspberry-pi/boot-nvme.adoc) _(same as link above)_
* [Raspberry Pi Documentation > Compute Module Hardware > Flashing the Compute Module eMMC > Compute Module 4 Bootloader](https://www.raspberrypi.com/documentation/computers/compute-module.html#compute-module-4-bootloader)
* [raspberrypi/usbboot](https://github.com/raspberrypi/usbboot)

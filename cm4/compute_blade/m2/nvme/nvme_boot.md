# Instructions

1. Switch to USB-C mode.
1. Hold the nRPIBOOT button.
1. Connect the USB-C port on the Compute Blade to a Linux or macOS host computer.
  1. You can power the board in this scenario via USB-C or PoE, but the USB-C port must be connected.
1. Wait a few seconds until the board has powered up.
1. Release the nRPIBOOT button.
  1. The host computer may prompt you to allow the connection of a new USB device, ex. "BCM2835" - this is the CM4/Compute Blade. Accept the connection.
1. Install `libusb` and `pkg-utils`
  1. Linux (Debian): `sudo apt install git libusb-1.0-0-dev pkg-config`
  1. macOS (brew): `brew install libusb pkg-utils`
1. `cd usbboot`
1. `make`
  1. If you encounter issues with `make`, you may need to install additional packages or troubleshoot further. For example, I had to install `coreutils` to check the sha256 sum.
1. `cd recovery`
1. `nano boot.conf`
1. Set `BOOT_ORDER` to `0xf16` (see example below)
1. Set `BOOT_UART` to `1` (see example below)
1. Save `boot.conf` - Ctrl-X, Y, Enter. 
1. `./update-pieeprom.sh`
1. `cd ../`
1. `sudo ./rpiboot -d recovery` (see example output below)
  1. The host computer may prompt you to allow the connection of a new USB device, ex. "BCM2835" - this is the CM4/Compute Blade. Accept the connection.

The update should be complete. Reboot the Compute Blade and it should boot from the attached NVMe drive.

# Examples

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
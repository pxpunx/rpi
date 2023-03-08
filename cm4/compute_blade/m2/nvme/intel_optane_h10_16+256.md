# Product Information

| Product | [Intel® Optane™ Memory H10 with Solid State Storage](https://ark.intel.com/content/www/us/en/ark/products/189614/intel-optane-memory-h10-with-solid-state-storage-intel-optane-memory-16gb-intel-qlc-3d-nand-ssd-256gb-m-2-80mm-pcie-3-0.html) |
|:-|:-|
|----|----|
| *Name* | Intel Optane H10 |
| *Model* | HBRPEKNX0101A |
| *Capacity* | 16GB + 256GB |
| *Form Factor* | M.2 2280 |
| *Key* | M |
| *Interface* | NVMe |
| *NAND Controller* | Silicon Motion SM2263 |
| *NAND Flash* | Intel 64L 3D QLC |
| *Optane Controller* | Intel SLL3D |
| *Optane Memory* | Intel 3D XPoint |
| *Boot Disk* | :white_check_mark: |
| *Non-Boot Disk* | :white_check_mark: |
| *Adapter* | - |

* [The Intel Optane Memory H10 Review: QLC and Optane In One SSD](https://www.anandtech.com/show/14249/the-intel-optane-memory-h10-review-two-ssds-in-one)

This NVMe device has a 16GB of Optane (3D XPoint) NVM as well as a 256GB SSD on the same M.2 device. 

CM4 has one PCIe Gen2 lane; it's not possible to utilize both "disks" on the the H10. 

In this case, the 256GB SSD is usable, but the 16GB of Optane NVM is not.

> *Intel Optane Memory H10 is essentially a hybrid SSD product that fuses two Intel Technologies on to one M.2 PCIe x 4 device. The SSD solution includes Intel Optane Memory functioning as cache combined with the Intel 660P SSD functioning as storage. The benefit of combining these products together is that consumers can now further improve the performance of their SSD through the addition of 3D Xpoint memory which Intel brands as Optane. The storage and caching combination is available in several flavors with the cache being either 16GB or 32GB and the storage being 256GB, 512GB or 1TB. **With this concept, Intel is essentially combining two PCIe x 2 products on to one M.2 form factor so the device internally bifurcates the PCIe x4 lane into two PCIe x 2 lanes, one for the Intel Optane Memory cache and the other for the Intel 660P. Managing this setup makes integrating the H10 more complex than simply adding the module to a system. There are differing considerations that include chipset compatibility, MB compatibility, proper M.2 slot configuration, proper BIOS, proper Windows drivers, proper MB firmware, as well as the correct Intel RST driver and of course proper setup of the entire configuration.** It is for these reasons that the H10 is not intended to be sold as a standalone device and is intended to be integrated by the reseller or by ASI.*

> Source: https://www.asipartner.com/solutions/gaming/intel-optane-memory-h10/#MB%20Compatibility%20List

Unlike the M10, this device *can* boot a CM4 installed on a Compute Blade. Compare **Boot Information** below with the same for the [Intel Optane M10](intel_optane_m10_32.md).

# Device Name

```
# lsblk | grep nvme[01]
nvme0n1     259:0    0 238.5G  0 disk 
```

# Device Information

<details>
  <summary>Click here to expand...</summary>
  
  ```
  # lspci -vvv -s 01:00.0
  01:00.0 Non-Volatile memory controller: Intel Corporation Device 0975 (rev 03) (prog-if 02 [NVM Express])
    Subsystem: Intel Corporation Device 8410
    Control: I/O- Mem+ BusMaster+ SpecCycle- MemWINV- VGASnoop- ParErr- Stepping- SERR- FastB2B- DisINTx+
    Status: Cap+ 66MHz- UDF- FastB2B- ParErr- DEVSEL=fast >TAbort- <TAbort- <MAbort- >SERR- <PERR- INTx-
    Latency: 0
    Interrupt: pin A routed to IRQ 63
    Region 0: Memory at 600000000 (64-bit, non-prefetchable) [size=16K]
    Capabilities: [40] Power Management version 3
      Flags: PMEClk- DSI- D1- D2- AuxCurrent=0mA PME(D0-,D1-,D2-,D3hot-,D3cold-)
      Status: D0 NoSoftRst- PME-Enable- DSel=0 DScale=0 PME-
    Capabilities: [50] MSI: Enable- Count=1/8 Maskable+ 64bit+
      Address: 0000000000000000  Data: 0000
      Masking: 00000000  Pending: 00000000
    Capabilities: [70] Express (v2) Endpoint, MSI 00
      DevCap:	MaxPayload 128 bytes, PhantFunc 0, Latency L0s unlimited, L1 unlimited
        ExtTag- AttnBtn- AttnInd- PwrInd- RBE+ FLReset+ SlotPowerLimit 0.000W
      DevCtl:	CorrErr- NonFatalErr- FatalErr- UnsupReq-
        RlxdOrd+ ExtTag- PhantFunc- AuxPwr- NoSnoop- FLReset-
        MaxPayload 128 bytes, MaxReadReq 512 bytes
      DevSta:	CorrErr+ NonFatalErr- FatalErr- UnsupReq- AuxPwr+ TransPend-
      LnkCap:	Port #0, Speed 8GT/s, Width x2, ASPM L1, Exit Latency L1 <8us
        ClockPM+ Surprise- LLActRep- BwNot- ASPMOptComp+
      LnkCtl:	ASPM Disabled; RCB 64 bytes, Disabled- CommClk+
        ExtSynch- ClockPM- AutWidDis- BWInt- AutBWInt-
      LnkSta:	Speed 5GT/s (downgraded), Width x1 (downgraded)
        TrErr- Train- SlotClk+ DLActive- BWMgmt- ABWMgmt-
      DevCap2: Completion Timeout: Range ABCD, TimeoutDis+ NROPrPrP- LTR+
        10BitTagComp- 10BitTagReq- OBFF Not Supported, ExtFmt- EETLPPrefix-
        EmergencyPowerReduction Not Supported, EmergencyPowerReductionInit-
        FRS- TPHComp- ExtTPHComp-
        AtomicOpsCap: 32bit- 64bit- 128bitCAS-
      DevCtl2: Completion Timeout: 50us to 50ms, TimeoutDis- LTR+ OBFF Disabled,
        AtomicOpsCtl: ReqEn-
      LnkCap2: Supported Link Speeds: 2.5-8GT/s, Crosslink- Retimer- 2Retimers- DRS-
      LnkCtl2: Target Link Speed: 8GT/s, EnterCompliance- SpeedDis-
        Transmit Margin: Normal Operating Range, EnterModifiedCompliance- ComplianceSOS-
        Compliance De-emphasis: -6dB
      LnkSta2: Current De-emphasis Level: -3.5dB, EqualizationComplete- EqualizationPhase1-
        EqualizationPhase2- EqualizationPhase3- LinkEqualizationRequest-
        Retimer- 2Retimers- CrosslinkRes: unsupported
    Capabilities: [b0] MSI-X: Enable+ Count=16 Masked-
      Vector table: BAR=0 offset=00002000
      PBA: BAR=0 offset=00002100
    Capabilities: [100 v2] Advanced Error Reporting
      UESta:	DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
      UEMsk:	DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
      UESvrt:	DLP+ SDES+ TLP- FCP+ CmpltTO- CmpltAbrt- UnxCmplt- RxOF+ MalfTLP+ ECRC- UnsupReq- ACSViol-
      CESta:	RxErr- BadTLP- BadDLLP- Rollover- Timeout+ AdvNonFatalErr-
      CEMsk:	RxErr- BadTLP- BadDLLP- Rollover- Timeout- AdvNonFatalErr+
      AERCap:	First Error Pointer: 00, ECRCGenCap+ ECRCGenEn- ECRCChkCap+ ECRCChkEn-
        MultHdrRecCap- MultHdrRecEn- TLPPfxPres- HdrLogCap-
      HeaderLog: 00000000 00000000 00000000 00000000
    Capabilities: [158 v1] Secondary PCI Express
      LnkCtl3: LnkEquIntrruptEn- PerformEqu-
      LaneErrStat: 0
    Capabilities: [178 v1] Latency Tolerance Reporting
      Max snoop latency: 0ns
      Max no snoop latency: 0ns
    Capabilities: [180 v1] L1 PM Substates
      L1SubCap: PCI-PM_L1.2+ PCI-PM_L1.1+ ASPM_L1.2+ ASPM_L1.1+ L1_PM_Substates+
          PortCommonModeRestoreTime=100us PortTPowerOnTime=3100us
      L1SubCtl1: PCI-PM_L1.2- PCI-PM_L1.1- ASPM_L1.2- ASPM_L1.1-
          T_CommonMode=0us LTR1.2_Threshold=3145728ns
      L1SubCtl2: T_PwrOn=3100us
    Kernel driver in use: nvme
  ```
</details>

# Disk Information

```
# fdisk -l /dev/nvme0n1
Disk /dev/nvme0n1: 238.47 GiB, 256060514304 bytes, 500118192 sectors
Disk model: H10 HBRPEKNX0101A NVMe INTEL 256GB      
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
```

# Filesystem Information

```
# df -Th /dev/nvme0n1
Filesystem     Type  Size  Used Avail Use% Mounted on
/dev/nvme0n1   ext4  234G   28K  222G   1% /mnt/sda1
```
# Benchmarks

## PiBenchmarks.com

Credit: [James C. Chambers](https://jamesachambers.com/) ([source](https://raw.githubusercontent.com/TheRemote/PiBenchmarks/master/Storage.sh))

Full benchmark: [pibenchmarks.com #67412](https://pibenchmarks.com/benchmark/67412/)

| Category | Test | Result |
|:-|:-|:-|
| DD | Disk Write | TBD |
| HDParm | Disk Read | TBD |
| HDParm | Cached Disk Read | TBD |
| FIO | 4K Random Read | TBD |
| FIO | 4K Random Write | TBD |
| FIO | 4K Random Read | TBD |
| FIO | 4K Random Write | TBD |
| IOZone | 4K Read | TBD |
| IOZone | 4K Write | TBD |
| IOZone | 4K Random Read | TBD |
| IOZone | 4K Random Write | TBD |
| **Score** | | TBD |

## Jeff Geerling

Credit: [Jeff Geerling](https://www.jeffgeerling.com/) ([source](https://raw.githubusercontent.com/geerlingguy/pi-cluster/master/benchmarks/disk-benchmark.sh))

<details>
  <summary>Click here to expand...</summary>
  
  ```
  # DEVICE_UNDER_TEST=/dev/nvme0n1 ./disk-benchmark.sh

  Raspberry Pi disk benchmarks
  Running fio sequential read test...
  fio-rand-read-sequential: (g=0): rw=read, bs=(R) 1024KiB-1024KiB, (W) 1024KiB-1024KiB, (T) 1024KiB-1024KiB, ioengine=libaio, iodepth=64
  ...
  fio-3.25
  Starting 4 processes
  Jobs: 4 (f=4): [R(4)][36.4%][r=393MiB/s][r=392 IOPS][eta 00m:07s]
  Jobs: 4 (f=4): [R(4)][54.5%][r=390MiB/s][r=389 IOPS][eta 00m:05s] 
  Jobs: 4 (f=4): [R(4)][63.6%][r=393MiB/s][r=392 IOPS][eta 00m:04s]
  Jobs: 4 (f=4): [R(4)][72.7%][r=391MiB/s][r=390 IOPS][eta 00m:03s]
  Jobs: 4 (f=4): [R(4)][81.8%][r=393MiB/s][r=393 IOPS][eta 00m:02s]
  Jobs: 4 (f=4): [R(4)][90.9%][r=369MiB/s][r=368 IOPS][eta 00m:01s]
  Jobs: 4 (f=4): [R(4)][100.0%][r=384MiB/s][r=384 IOPS][eta 00m:00s]
  fio-rand-read-sequential: (groupid=0, jobs=4): err= 0: pid=609: Sun Feb 19 09:12:33 2023
    read: IOPS=391, BW=392MiB/s (411MB/s)(4011MiB/10243msec)
      slat (usec): min=149, max=49011, avg=9978.00, stdev=15363.86
      clat (msec): min=203, max=1160, avg=635.32, stdev=100.49
      lat (msec): min=238, max=1205, avg=645.30, stdev=102.01
      clat percentiles (msec):
      |  1.00th=[  326],  5.00th=[  472], 10.00th=[  523], 20.00th=[  625],
      | 30.00th=[  625], 40.00th=[  625], 50.00th=[  625], 60.00th=[  634],
      | 70.00th=[  667], 80.00th=[  676], 90.00th=[  676], 95.00th=[  751],
      | 99.00th=[ 1020], 99.50th=[ 1045], 99.90th=[ 1150], 99.95th=[ 1150],
      | 99.99th=[ 1167]
    bw (  KiB/s): min=129024, max=477184, per=95.89%, avg=384499.85, stdev=19064.28, samples=80
    iops        : min=  126, max=  466, avg=375.00, stdev=18.63, samples=80
    lat (msec)   : 250=0.17%, 500=7.75%, 750=87.09%, 1000=3.81%, 2000=1.17%
    cpu          : usr=0.13%, sys=4.21%, ctx=6788, majf=0, minf=65636
    IO depths    : 1=0.1%, 2=0.2%, 4=0.4%, 8=0.8%, 16=1.6%, 32=3.2%, >=64=93.7%
      submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
      complete  : 0=0.0%, 4=99.9%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.1%, >=64=0.0%
      issued rwts: total=4011,0,0,0 short=0,0,0,0 dropped=0,0,0,0
      latency   : target=0, window=0, percentile=100.00%, depth=64

  Run status group 0 (all jobs):
    READ: bw=392MiB/s (411MB/s), 392MiB/s-392MiB/s (411MB/s-411MB/s), io=4011MiB (4206MB), run=10243-10243msec

  Disk stats (read/write):
    nvme0n1: ios=31820/563, merge=0/16, ticks=9580809/134478, in_queue=9715599, util=99.31%

  Running iozone 1024K random read and write tests...
    Iozone: Performance Test of File I/O
            Version $Revision: 3.492 $
      Compiled for 64 bit mode.
      Build: linux-arm 

    Contributors:William Norcott, Don Capps, Isom Crawford, Kirby Collins
                Al Slater, Scott Rhine, Mike Wisner, Ken Goss
                Steve Landherr, Brad Smith, Mark Kelly, Dr. Alain CYR,
                Randy Dunlap, Mark Montague, Dan Million, Gavin Brebner,
                Jean-Marc Zucconi, Jeff Blomberg, Benny Halevy, Dave Boone,
                Erik Habbinga, Kris Strecker, Walter Wong, Joshua Root,
                Fabrice Bacchella, Zhenghua Xue, Qin Li, Darren Sawyer,
                Vangel Bojaxhi, Ben England, Vikentsi Lapa,
                Alexey Skidanov, Sudhir Kumar.

    Run began: Sun Feb 19 09:12:33 2023

    Include fsync in write timing
    O_DIRECT feature enabled
    Auto Mode
    File size set to 102400 kB
    Record Size 1024 kB
    Command line used: ./iozone -e -I -a -s 100M -r 1024k -i 0 -i 2 -f /mnt/sda1/iozone
    Output is in kBytes/sec
    Time Resolution = 0.000001 seconds.
    Processor cache size set to 1024 kBytes.
    Processor cache line size set to 32 bytes.
    File stride size set to 17 * record size.
                                                                random    random     bkwd    record    stride                                    
                kB  reclen    write  rewrite    read    reread    read     write     read   rewrite      read   fwrite frewrite    fread  freread
            102400    1024   340558   339409                     357029   342908                                                                

  iozone test complete.

  Running iozone 4K random read and write tests...
    Iozone: Performance Test of File I/O
            Version $Revision: 3.492 $
      Compiled for 64 bit mode.
      Build: linux-arm 

    Contributors:William Norcott, Don Capps, Isom Crawford, Kirby Collins
                Al Slater, Scott Rhine, Mike Wisner, Ken Goss
                Steve Landherr, Brad Smith, Mark Kelly, Dr. Alain CYR,
                Randy Dunlap, Mark Montague, Dan Million, Gavin Brebner,
                Jean-Marc Zucconi, Jeff Blomberg, Benny Halevy, Dave Boone,
                Erik Habbinga, Kris Strecker, Walter Wong, Joshua Root,
                Fabrice Bacchella, Zhenghua Xue, Qin Li, Darren Sawyer,
                Vangel Bojaxhi, Ben England, Vikentsi Lapa,
                Alexey Skidanov, Sudhir Kumar.

    Run began: Sun Feb 19 09:12:35 2023

    Include fsync in write timing
    O_DIRECT feature enabled
    Auto Mode
    File size set to 102400 kB
    Record Size 4 kB
    Command line used: ./iozone -e -I -a -s 100M -r 4k -i 0 -i 2 -f /mnt/sda1/iozone
    Output is in kBytes/sec
    Time Resolution = 0.000001 seconds.
    Processor cache size set to 1024 kBytes.
    Processor cache line size set to 32 bytes.
    File stride size set to 17 * record size.
                                                                random    random     bkwd    record    stride                                    
                kB  reclen    write  rewrite    read    reread    read     write     read   rewrite      read   fwrite frewrite    fread  freread
            102400       4    48232    75104                      44986    71600                                                                

  iozone test complete.

  Disk benchmark complete!
  ```
</details>

# Boot Information

## Device Name(s)

```
# lsblk | grep nvme[01]
nvme0n1     259:0    0 238.5G  0 disk 
├─nvme0n1p1 259:1    0   256M  0 part /boot
└─nvme0n1p2 259:2    0 238.2G  0 part /
```

## Disk Information

```
# fdisk -l /dev/nvme0n1
Disk /dev/nvme0n1: 238.47 GiB, 256060514304 bytes, 500118192 sectors
Disk model: H10 HBRPEKNX0101A NVMe INTEL 256GB      
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0x3bf763bb

Device         Boot  Start       End   Sectors   Size Id Type
/dev/nvme0n1p1        8192    532479    524288   256M  c W95 FAT32 (LBA)
/dev/nvme0n1p2      532480 500118191 499585712 238.2G 83 Linux
```

## Bootloader Version

```
# vcgencmd bootloader_version
2023/01/11 17:40:52
version 8ba17717fbcedd4c3b6d4bce7e50c7af4155cba9 (release)
timestamp 1673458852
update-time 1676831636
capabilities 0x0000007f
```

## Bootloader Configuration

```
# vcgencmd bootloader_config
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

## `nvme` Output

<details>
  <summary>Click here to expand...</summary>
    
  ```
  # nvme version
  nvme version 1.12
  ```

  ```
  # nvme list
  Node             SN                   Model                                    Namespace Usage                      Format           FW Rev  
  ---------------- -------------------- ---------------------------------------- --------- -------------------------- ---------------- --------
  /dev/nvme0n1     BTTE90320FNS256D-1   H10 HBRPEKNX0101A NVMe INTEL 256GB       1         256.06  GB / 256.06  GB    512   B +  0 B   7002    
  ```

  ```
  # nvme list-subsys
  nvme-subsys0 - NQN=nqn.2019-03.com.intel:nvm-subsystem-sn-btte90320fns256d-1
  \
  +- nvme0 pcie 0000:01:00.0 live 
  ```

  ```
  # nvme id-ctrl -H /dev/nvme0n1
  NVME Identify Controller:
  vid       : 0x8086
  ssvid     : 0x8086
  sn        : BTTE90320FNS256D-1  
  mn        : H10 HBRPEKNX0101A NVMe INTEL 256GB      
  fr        : 7002    
  rab       : 6
  ieee      : 5cd2e4
  cmic      : 0
    [3:3] : 0	ANA not supported
    [2:2] : 0	PCI
    [1:1] : 0	Single Controller
    [0:0] : 0	Single Port

  mdts      : 5
  cntlid    : 0x1
  ver       : 0x10300
  rtd3r     : 0x7a120
  rtd3e     : 0x1e8480
  oaes      : 0x200
  [14:14] : 0	Endurance Group Event Aggregate Log Page Change Notice Not Supported
  [13:13] : 0	LBA Status Information Notices Not Supported
  [12:12] : 0	Predictable Latency Event Aggregate Log Change Notices Not Supported
  [11:11] : 0	Asymmetric Namespace Access Change Notices Not Supported
    [9:9] : 0x1	Firmware Activation Notices Supported
    [8:8] : 0	Namespace Attribute Changed Event Not Supported

  ctratt    : 0x2
    [9:9] : 0	UUID List Not Supported
    [7:7] : 0	Namespace Granularity Not Supported
    [5:5] : 0	Predictable Latency Mode Not Supported
    [4:4] : 0	Endurance Groups Not Supported
    [3:3] : 0	Read Recovery Levels Not Supported
    [2:2] : 0	NVM Sets Not Supported
    [1:1] : 0x1	Non-Operational Power State Permissive Supported
    [0:0] : 0	128-bit Host Identifier Not Supported

  rrls      : 0
  cntrltype : 0
    [7:2] : 0	Reserved
    [1:0] : 0	Controller type not reported
  fguid     : 
  crdt1     : 0
  crdt2     : 0
  crdt3     : 0
  oacs      : 0x16
    [9:9] : 0	Get LBA Status Capability Not Supported
    [8:8] : 0	Doorbell Buffer Config Not Supported
    [7:7] : 0	Virtualization Management Not Supported
    [6:6] : 0	NVMe-MI Send and Receive Not Supported
    [5:5] : 0	Directives Not Supported
    [4:4] : 0x1	Device Self-test Supported
    [3:3] : 0	NS Management and Attachment Not Supported
    [2:2] : 0x1	FW Commit and Download Supported
    [1:1] : 0x1	Format NVM Supported
    [0:0] : 0	Security Send and Receive Not Supported

  acl       : 3
  aerl      : 7
  frmw      : 0x14
    [4:4] : 0x1	Firmware Activate Without Reset Supported
    [3:1] : 0x2	Number of Firmware Slots
    [0:0] : 0	Firmware Slot 1 Read/Write

  lpa       : 0xf
    [4:4] : 0	Persistent Event log Not Supported
    [3:3] : 0x1	Telemetry host/controller initiated log page Supported
    [2:2] : 0x1	Extended data for Get Log Page Supported
    [1:1] : 0x1	Command Effects Log Page Supported
    [0:0] : 0x1	SMART/Health Log Page per NS Supported

  elpe      : 255
  npss      : 4
  avscc     : 0
    [0:0] : 0	Admin Vendor Specific Commands uses Vendor Specific Format

  apsta     : 0x1
    [0:0] : 0x1	Autonomous Power State Transitions Supported

  wctemp    : 350
  cctemp    : 353
  mtfa      : 50
  hmpre     : 0
  hmmin     : 0
  tnvmcap   : 0
  unvmcap   : 0
  rpmbs     : 0
  [31:24]: 0	Access Size
  [23:16]: 0	Total Size
    [5:3] : 0	Authentication Method
    [2:0] : 0	Number of RPMB Units

  edstt     : 5
  dsto      : 1
  fwug      : 0
  kas       : 0
  hctma     : 0x1
    [0:0] : 0x1	Host Controlled Thermal Management Supported

  mntmt     : 303
  mxtmt     : 348
  sanicap   : 0x3
    [31:30] : 0	Additional media modification after sanitize operation completes successfully is not defined
    [29:29] : 0	No-Deallocate After Sanitize bit in Sanitize command Supported
      [2:2] : 0	Overwrite Sanitize Operation Not Supported
      [1:1] : 0x1	Block Erase Sanitize Operation Supported
      [0:0] : 0x1	Crypto Erase Sanitize Operation Supported

  hmminds   : 0
  hmmaxd    : 0
  nsetidmax : 0
  endgidmax : 0
  anatt     : 0
  anacap    : 0
    [7:7] : 0	Non-zero group ID Not Supported
    [6:6] : 0	Group ID does not change
    [4:4] : 0	ANA Change state Not Supported
    [3:3] : 0	ANA Persistent Loss state Not Supported
    [2:2] : 0	ANA Inaccessible state Not Supported
    [1:1] : 0	ANA Non-optimized state Not Supported
    [0:0] : 0	ANA Optimized state Not Supported

  anagrpmax : 0
  nanagrpid : 0
  pels      : 0
  sqes      : 0x66
    [7:4] : 0x6	Max SQ Entry Size (64)
    [3:0] : 0x6	Min SQ Entry Size (64)

  cqes      : 0x44
    [7:4] : 0x4	Max CQ Entry Size (16)
    [3:0] : 0x4	Min CQ Entry Size (16)

  maxcmd    : 0
  nn        : 1
  oncs      : 0x5f
    [7:7] : 0	Verify Not Supported
    [6:6] : 0x1	Timestamp Supported
    [5:5] : 0	Reservations Not Supported
    [4:4] : 0x1	Save and Select Supported
    [3:3] : 0x1	Write Zeroes Supported
    [2:2] : 0x1	Data Set Management Supported
    [1:1] : 0x1	Write Uncorrectable Supported
    [0:0] : 0x1	Compare Supported

  fuses     : 0
    [0:0] : 0	Fused Compare and Write Not Supported

  fna       : 0x4
    [2:2] : 0x1	Crypto Erase Supported as part of Secure Erase
    [1:1] : 0	Crypto Erase Applies to Single Namespace(s)
    [0:0] : 0	Format Applies to Single Namespace(s)

  vwc       : 0x1
    [2:1] : 0	Support for the NSID field set to FFFFFFFFh is not indicated
    [0:0] : 0x1	Volatile Write Cache Present

  awun      : 0
  awupf     : 0
  nvscc     : 0
    [0:0] : 0	NVM Vendor Specific Commands uses Vendor Specific Format

  nwpc      : 0
    [2:2] : 0	Permanent Write Protect Not Supported
    [1:1] : 0	Write Protect Until Power Supply Not Supported
    [0:0] : 0	No Write Protect and Write Protect Namespace Not Supported

  acwu      : 0
  sgls      : 0
  [1:0]  : 0	Scatter-Gather Lists Not Supported

  mnan      : 0
  subnqn    : nqn.2019-03.com.intel:nvm-subsystem-sn-btte90320fns256d-1
  ioccsz    : 0
  iorcsz    : 0
  icdoff    : 0
  ctrattr   : 0
    [0:0] : 0	Dynamic Controller Model

  msdbd     : 0
  ps    0 : mp:3.50W operational enlat:0 exlat:0 rrt:0 rrl:0
            rwt:0 rwl:0 idle_power:- active_power:-
  ps    1 : mp:2.70W operational enlat:0 exlat:0 rrt:1 rrl:1
            rwt:1 rwl:1 idle_power:- active_power:-
  ps    2 : mp:2.00W operational enlat:0 exlat:0 rrt:2 rrl:2
            rwt:2 rwl:2 idle_power:- active_power:-
  ps    3 : mp:0.0250W non-operational enlat:2000 exlat:5000 rrt:3 rrl:3
            rwt:3 rwl:3 idle_power:- active_power:-
  ps    4 : mp:0.0040W non-operational enlat:5000 exlat:9000 rrt:4 rrl:4
            rwt:4 rwl:4 idle_power:- active_power:-
  ```

  ```
  # nvme list-ns /dev/nvme0n1
  [   0]:0x1
  ```

  ```
  # nvme id-ns -H /dev/nvme0n1 --namespace-id=1
  NVME Identify Namespace 1:
  nsze    : 0x1dcf32b0
  ncap    : 0x1dcf32b0
  nuse    : 0x1dcf32b0
  nsfeat  : 0
    [4:4] : 0	NPWG, NPWA, NPDG, NPDA, and NOWS are Not Supported
    [2:2] : 0	Deallocated or Unwritten Logical Block error Not Supported
    [1:1] : 0	Namespace uses AWUN, AWUPF, and ACWU
    [0:0] : 0	Thin Provisioning Not Supported

  nlbaf   : 0
  flbas   : 0
    [4:4] : 0	Metadata Transferred in Separate Contiguous Buffer
    [3:0] : 0	Current LBA Format Selected

  mc      : 0
    [1:1] : 0	Metadata Pointer Not Supported
    [0:0] : 0	Metadata as Part of Extended Data LBA Not Supported

  dpc     : 0
    [4:4] : 0	Protection Information Transferred as Last 8 Bytes of Metadata Not Supported
    [3:3] : 0	Protection Information Transferred as First 8 Bytes of Metadata Not Supported
    [2:2] : 0	Protection Information Type 3 Not Supported
    [1:1] : 0	Protection Information Type 2 Not Supported
    [0:0] : 0	Protection Information Type 1 Not Supported

  dps     : 0
    [3:3] : 0	Protection Information is Transferred as Last 8 Bytes of Metadata
    [2:0] : 0	Protection Information Disabled

  nmic    : 0
    [0:0] : 0	Namespace Multipath Not Capable

  rescap  : 0
    [6:6] : 0	Exclusive Access - All Registrants Not Supported
    [5:5] : 0	Write Exclusive - All Registrants Not Supported
    [4:4] : 0	Exclusive Access - Registrants Only Not Supported
    [3:3] : 0	Write Exclusive - Registrants Only Not Supported
    [2:2] : 0	Exclusive Access Not Supported
    [1:1] : 0	Write Exclusive Not Supported
    [0:0] : 0	Persist Through Power Loss Not Supported

  fpi     : 0x80
    [7:7] : 0x1	Format Progress Indicator Supported
    [6:0] : 0	Format Progress Indicator (Remaining 0%)

  dlfeat  : 1
    [4:4] : 0	Guard Field of Deallocated Logical Blocks is set to 0xFFFF
    [3:3] : 0	Deallocate Bit in the Write Zeroes Command is Not Supported
    [2:0] : 0x1	Bytes Read From a Deallocated Logical Block and its Metadata are 0x00

  nawun   : 0
  nawupf  : 0
  nacwu   : 0
  nabsn   : 0
  nabo    : 0
  nabspf  : 0
  noiob   : 0
  nvmcap  : 0
  nsattr	: 0
  nvmsetid: 0
  anagrpid: 0
  endgid  : 0
  nguid   : 00000000000000000000000000000000
  eui64   : 5cd2e45391b0236a
  LBA Format  0 : Metadata Size: 0   bytes - Data Size: 512 bytes - Relative Performance: 0 Best (in use)
  ```
</details>
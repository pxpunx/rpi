# Product Information

| Product | [Intel® Optane™ Memory M10 Series](https://ark.intel.com/content/www/us/en/ark/products/135581/intel-optane-memory-m10-series-16gb-m-2-80mm-pcie-3-0-20nm-3d-xpoint.html) |
|:-|:-|
|----|----|
| *Name* | Intel Optane M10 |
| *Model* | MEMPEK1J032GAD |
| *Capacity* | 32GB |
| *Form Factor* | M.2 2280 |
| *Key* | M + B |
| *Interface* | NVMe |
| *Bootable* | NO (see below) |
| *Benchmark(s)* | [pibenchmarks.com #67410](https://pibenchmarks.com/benchmark/67410/), local (below) |

This device will not boot a CM4 installed on a Compute Blade. Compare **Boot Information** below with the same for the [Intel Optane H10][intel_optane_h10_16+256.md].

# Device Name

```
# lsblk | grep nvme[01]
nvme0n1     259:0    0 27.3G  0 disk 
```

# Device Information

<details>
  <summary>Click here to expand...</summary>

  ```
  # lspci -vvv -s 01:00.0
  01:00.0 Non-Volatile memory controller: Intel Corporation NVMe Optane Memory Series (prog-if 02 [NVM Express])
    Subsystem: Intel Corporation Optane Memory M10 16GB
    Control: I/O- Mem+ BusMaster+ SpecCycle- MemWINV- VGASnoop- ParErr- Stepping- SERR- FastB2B- DisINTx+
    Status: Cap+ 66MHz- UDF- FastB2B- ParErr- DEVSEL=fast >TAbort- <TAbort- <MAbort- >SERR- <PERR- INTx-
    Latency: 0
    Interrupt: pin A routed to IRQ 63
    Region 0: Memory at 600000000 (64-bit, non-prefetchable) [size=16K]
    Capabilities: [40] Power Management version 3
      Flags: PMEClk- DSI- D1- D2- AuxCurrent=0mA PME(D0-,D1-,D2-,D3hot-,D3cold-)
      Status: D0 NoSoftRst+ PME-Enable- DSel=0 DScale=0 PME-
    Capabilities: [50] MSI-X: Enable+ Count=9 Masked-
      Vector table: BAR=0 offset=00002000
      PBA: BAR=0 offset=00003000
    Capabilities: [60] Express (v2) Endpoint, MSI 00
      DevCap:	MaxPayload 256 bytes, PhantFunc 0, Latency L0s unlimited, L1 unlimited
        ExtTag+ AttnBtn- AttnInd- PwrInd- RBE+ FLReset+ SlotPowerLimit 0.000W
      DevCtl:	CorrErr- NonFatalErr- FatalErr- UnsupReq-
        RlxdOrd+ ExtTag+ PhantFunc- AuxPwr- NoSnoop+ FLReset-
        MaxPayload 128 bytes, MaxReadReq 512 bytes
      DevSta:	CorrErr- NonFatalErr- FatalErr- UnsupReq- AuxPwr- TransPend-
      LnkCap:	Port #0, Speed 8GT/s, Width x2, ASPM L1, Exit Latency L1 unlimited
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
    Capabilities: [a0] MSI: Enable- Count=1/16 Maskable+ 64bit+
      Address: 0000000000000000  Data: 0000
      Masking: 00000000  Pending: 00000000
    Capabilities: [100 v1] Advanced Error Reporting
      UESta:	DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
      UEMsk:	DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
      UESvrt:	DLP+ SDES+ TLP- FCP+ CmpltTO- CmpltAbrt- UnxCmplt- RxOF+ MalfTLP+ ECRC- UnsupReq- ACSViol-
      CESta:	RxErr- BadTLP- BadDLLP- Rollover- Timeout- AdvNonFatalErr-
      CEMsk:	RxErr- BadTLP- BadDLLP- Rollover- Timeout- AdvNonFatalErr+
      AERCap:	First Error Pointer: 00, ECRCGenCap+ ECRCGenEn- ECRCChkCap+ ECRCChkEn-
        MultHdrRecCap- MultHdrRecEn- TLPPfxPres- HdrLogCap-
      HeaderLog: 00000000 00000000 00000000 00000000
    Capabilities: [150 v1] Virtual Channel
      Caps:	LPEVC=0 RefClk=100ns PATEntryBits=1
      Arb:	Fixed- WRR32- WRR64- WRR128-
      Ctrl:	ArbSelect=Fixed
      Status:	InProgress-
      VC0:	Caps:	PATOffset=00 MaxTimeSlots=1 RejSnoopTrans-
        Arb:	Fixed- WRR32- WRR64- WRR128- TWRR128- WRR256-
        Ctrl:	Enable+ ID=0 ArbSelect=Fixed TC/VC=ff
        Status:	NegoPending- InProgress-
    Capabilities: [180 v1] Power Budgeting <?>
    Capabilities: [190 v1] Alternative Routing-ID Interpretation (ARI)
      ARICap:	MFVC- ACS-, Next Function: 0
      ARICtl:	MFVC- ACS-, Function Group: 0
    Capabilities: [2a0 v1] Secondary PCI Express
      LnkCtl3: LnkEquIntrruptEn- PerformEqu-
      LaneErrStat: 0
    Capabilities: [2d0 v1] Latency Tolerance Reporting
      Max snoop latency: 0ns
      Max no snoop latency: 0ns
    Capabilities: [310 v1] L1 PM Substates
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
Disk /dev/nvme0n1: 27.25 GiB, 29260513280 bytes, 57149440 sectors
Disk model: INTEL MEMPEK1J032GAD                    
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
```

# Filesystem Information

```
# df -Th /dev/nvme0n1
Filesystem     Type  Size  Used Avail Use% Mounted on
/dev/nvme0n1   ext4   27G   24K   26G   1% /mnt/sda1
```

# Local Benchmark

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
  Jobs: 4 (f=4): [R(4)][30.0%][r=393MiB/s][r=393 IOPS][eta 00m:07s]
  Jobs: 4 (f=4): [R(4)][50.0%][r=394MiB/s][r=394 IOPS][eta 00m:05s] 
  Jobs: 4 (f=4): [R(4)][63.6%][r=393MiB/s][r=392 IOPS][eta 00m:04s]
  Jobs: 4 (f=4): [R(4)][81.8%][r=395MiB/s][r=395 IOPS][eta 00m:02s] 
  Jobs: 4 (f=4): [R(4)][100.0%][r=393MiB/s][r=393 IOPS][eta 00m:00s]
  fio-rand-read-sequential: (groupid=0, jobs=4): err= 0: pid=603: Sun Feb 19 09:03:11 2023
    read: IOPS=393, BW=393MiB/s (412MB/s)(3981MiB/10125msec)
      slat (usec): min=143, max=40659, avg=10033.88, stdev=3854.63
      clat (msec): min=113, max=1063, avg=626.74, stdev=230.94
      lat (msec): min=124, max=1078, avg=636.78, stdev=234.20
      clat percentiles (msec):
      |  1.00th=[  211],  5.00th=[  456], 10.00th=[  481], 20.00th=[  481],
      | 30.00th=[  481], 40.00th=[  481], 50.00th=[  481], 60.00th=[  481],
      | 70.00th=[  919], 80.00th=[  961], 90.00th=[  961], 95.00th=[  961],
      | 99.00th=[  995], 99.50th=[  995], 99.90th=[ 1045], 99.95th=[ 1062],
      | 99.99th=[ 1062]
    bw (  KiB/s): min=108544, max=421888, per=96.42%, avg=388209.18, stdev=19895.35, samples=78
    iops        : min=  106, max=  412, avg=379.11, stdev=19.43, samples=78
    lat (msec)   : 250=1.36%, 500=61.99%, 750=5.33%, 1000=31.00%, 2000=0.33%
    cpu          : usr=0.08%, sys=4.03%, ctx=7873, majf=0, minf=65637
    IO depths    : 1=0.1%, 2=0.2%, 4=0.4%, 8=0.8%, 16=1.6%, 32=3.2%, >=64=93.7%
      submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
      complete  : 0=0.0%, 4=99.9%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.1%, >=64=0.0%
      issued rwts: total=3981,0,0,0 short=0,0,0,0 dropped=0,0,0,0
      latency   : target=0, window=0, percentile=100.00%, depth=64

  Run status group 0 (all jobs):
    READ: bw=393MiB/s (412MB/s), 393MiB/s-393MiB/s (412MB/s-412MB/s), io=3981MiB (4174MB), run=10125-10125msec

  Disk stats (read/write):
    nvme0n1: ios=31096/1, merge=0/3, ticks=3656526/1, in_queue=3656526, util=99.12%

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

    Run began: Sun Feb 19 09:03:11 2023

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
            102400    1024   342985   349514                     386450   347952                                                                

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

    Run began: Sun Feb 19 09:03:12 2023

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
            102400       4    55800    87648                      92701    84338                                                                

  iozone test complete.

  Disk benchmark complete!
  ```
</details>

# Boot Information

## Console Output

```
RPi: BOOTLOADER release VERSION:8ba17717 DATE: 2023/01/11 TIME: 17:40:52
BOOTMODE: 0x06 partition 0 build-ts BUILD_TIMESTAMP=1673458852 serial 7ffae053 boardrev d03140 stc 478906
PM_RSTS: 0x00001000
part 00000000 reset_info 00000000
uSD voltage 3.3V
Initialising SDRAM 'Micron' 32Gb x2 total-size: 64 Gbit 3200
DDR 3200 1 0 64 152

Boot mode: NVME (06) order f1
Failed to open device: 'nvme'
Retry NVME 1
Failed to open device: 'nvme'
Boot mode: SD (01) order f
SD HOST: 200000000 CTL0: 0x00800000 BUS: 400000 Hz actual: 390625 HZ div: 512 (256) status: 0x1fff0000 delay: 276
SD HOST: 200000000 CTL0: 0x00800f00 BUS: 400000 Hz actual: 390625 HZ div: 512 (256) status: 0x1fff0000 delay: 276
EMMC
SD retry 1 oc 0
SD HOST: 200000000 CTL0: 0x00800000 BUS: 400000 Hz actual: 390625 HZ div: 512 (256) status: 0x1fff0000 delay: 276
SD retry 2 oc 0
SD HOST: 200000000 CTL0: 0x00800000 BUS: 400000 Hz actual: 390625 HZ div: 512 (256) status: 0x1fff0000 delay: 276
SDV1
SD CMD: 0x371a0010 (55) 0x0 0x1fff0001
Failed to open device: 'sdcard' (cmd 371a0010 status 1fff0001)
Retry SD 1
SD HOST: 200000000 CTL0: 0x00800000 BUS: 400000 Hz actual: 390625 HZ div: 512 (256) status: 0x1fff0000 delay: 276
SD HOST: 200000000 CTL0: 0x00800f00 BUS: 400000 Hz actual: 390625 HZ div: 512 (256) status: 0x1fff0000 delay: 276
EMMC
SD retry 1 oc 0
SD HOST: 200000000 CTL0: 0x00800000 BUS: 400000 Hz actual: 390625 HZ div: 512 (256) status: 0x1fff0000 delay: 276
SD retry 2 oc 0
SD HOST: 200000000 CTL0: 0x00800000 BUS: 400000 Hz actual: 390625 HZ div: 512 (256) status: 0x1fff0000 delay: 276
SDV1
SD CMD: 0x371a0010 (55) 0x0 0x1fff0001
Failed to open device: 'sdcard' (cmd 371a0010 status 1fff0001)
Boot mode: RESTART (0f) order 0
Restart 0 max -1

< repeats from 'Boot mode: NVME (06) order f1' >
```

## Device Name(s)

```
# lsblk | grep nvme[01]
nvme0n1     259:0    0 27.3G  0 disk 
├─nvme0n1p1 259:1    0  256M  0 part 
└─nvme0n1p2 259:2    0  1.6G  0 part 
```

# Disk Information

```
# fdisk -l /dev/nvme0n1
Disk /dev/nvme0n1: 27.25 GiB, 29260513280 bytes, 57149440 sectors
Disk model: INTEL MEMPEK1J032GAD                    
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0x21e60f8c

Device         Boot  Start     End Sectors  Size Id Type
/dev/nvme0n1p1        8192  532479  524288  256M  c W95 FAT32 (LBA)
/dev/nvme0n1p2      532480 3923967 3391488  1.6G 83 Linux
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
  /dev/nvme0n1     PHBT9135037D032P     INTEL MEMPEK1J032GAD                     1          29.26  GB /  29.26  GB    512   B +  0 B   K4110440
  ```

  ```
  # nvme list-subsys
  nvme-subsys0 - NQN=nqn.2014.08.org.nvmexpress:80868086PHBT9135037D032P    INTEL MEMPEK1J032GAD                    
  \
  +- nvme0 pcie 0000:01:00.0 live 
  ```

  ```
  # nvme id-ctrl -H /dev/nvme0n1
  NVME Identify Controller:
  vid       : 0x8086
  ssvid     : 0x8086
  sn        : PHBT9135037D032P    
  mn        : INTEL MEMPEK1J032GAD                    
  fr        : K4110440
  rab       : 0
  ieee      : 5cd2e4
  cmic      : 0
    [3:3] : 0	ANA not supported
    [2:2] : 0	PCI
    [1:1] : 0	Single Controller
    [0:0] : 0	Single Port

  mdts      : 5
  cntlid    : 0
  ver       : 0
  rtd3r     : 0
  rtd3e     : 0
  oaes      : 0
  [14:14] : 0	Endurance Group Event Aggregate Log Page Change Notice Not Supported
  [13:13] : 0	LBA Status Information Notices Not Supported
  [12:12] : 0	Predictable Latency Event Aggregate Log Change Notices Not Supported
  [11:11] : 0	Asymmetric Namespace Access Change Notices Not Supported
    [9:9] : 0	Firmware Activation Notices Not Supported
    [8:8] : 0	Namespace Attribute Changed Event Not Supported

  ctratt    : 0
    [9:9] : 0	UUID List Not Supported
    [7:7] : 0	Namespace Granularity Not Supported
    [5:5] : 0	Predictable Latency Mode Not Supported
    [4:4] : 0	Endurance Groups Not Supported
    [3:3] : 0	Read Recovery Levels Not Supported
    [2:2] : 0	NVM Sets Not Supported
    [1:1] : 0	Non-Operational Power State Permissive Not Supported
    [0:0] : 0	128-bit Host Identifier Not Supported

  rrls      : 0
  cntrltype : 0
    [7:2] : 0	Reserved
    [1:0] : 0	Controller type not reported
  fguid     : 
  crdt1     : 0
  crdt2     : 0
  crdt3     : 0
  oacs      : 0x6
    [9:9] : 0	Get LBA Status Capability Not Supported
    [8:8] : 0	Doorbell Buffer Config Not Supported
    [7:7] : 0	Virtualization Management Not Supported
    [6:6] : 0	NVMe-MI Send and Receive Not Supported
    [5:5] : 0	Directives Not Supported
    [4:4] : 0	Device Self-test Not Supported
    [3:3] : 0	NS Management and Attachment Not Supported
    [2:2] : 0x1	FW Commit and Download Supported
    [1:1] : 0x1	Format NVM Supported
    [0:0] : 0	Security Send and Receive Not Supported

  acl       : 3
  aerl      : 3
  frmw      : 0x2
    [4:4] : 0	Firmware Activate Without Reset Not Supported
    [3:1] : 0x1	Number of Firmware Slots
    [0:0] : 0	Firmware Slot 1 Read/Write

  lpa       : 0x2
    [4:4] : 0	Persistent Event log Not Supported
    [3:3] : 0	Telemetry host/controller initiated log page Not Supported
    [2:2] : 0	Extended data for Get Log Page Not Supported
    [1:1] : 0x1	Command Effects Log Page Supported
    [0:0] : 0	SMART/Health Log Page per NS Not Supported

  elpe      : 63
  npss      : 3
  avscc     : 0
    [0:0] : 0	Admin Vendor Specific Commands uses Vendor Specific Format

  apsta     : 0x1
    [0:0] : 0x1	Autonomous Power State Transitions Supported

  wctemp    : 0
  cctemp    : 0
  mtfa      : 0
  hmpre     : 0
  hmmin     : 0
  tnvmcap   : 0
  unvmcap   : 0
  rpmbs     : 0
  [31:24]: 0	Access Size
  [23:16]: 0	Total Size
    [5:3] : 0	Authentication Method
    [2:0] : 0	Number of RPMB Units

  edstt     : 0
  dsto      : 0
  fwug      : 0
  kas       : 0
  hctma     : 0
    [0:0] : 0	Host Controlled Thermal Management Not Supported

  mntmt     : 0
  mxtmt     : 0
  sanicap   : 0
    [31:30] : 0	Additional media modification after sanitize operation completes successfully is not defined
    [29:29] : 0	No-Deallocate After Sanitize bit in Sanitize command Supported
      [2:2] : 0	Overwrite Sanitize Operation Not Supported
      [1:1] : 0	Block Erase Sanitize Operation Not Supported
      [0:0] : 0	Crypto Erase Sanitize Operation Not Supported

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
  oncs      : 0x46
    [7:7] : 0	Verify Not Supported
    [6:6] : 0x1	Timestamp Supported
    [5:5] : 0	Reservations Not Supported
    [4:4] : 0	Save and Select Not Supported
    [3:3] : 0	Write Zeroes Not Supported
    [2:2] : 0x1	Data Set Management Supported
    [1:1] : 0x1	Write Uncorrectable Supported
    [0:0] : 0	Compare Not Supported

  fuses     : 0
    [0:0] : 0	Fused Compare and Write Not Supported

  fna       : 0x3
    [2:2] : 0	Crypto Erase Not Supported as part of Secure Erase
    [1:1] : 0x1	Crypto Erase Applies to All Namespace(s)
    [0:0] : 0x1	Format Applies to All Namespace(s)

  vwc       : 0
    [2:1] : 0	Support for the NSID field set to FFFFFFFFh is not indicated
    [0:0] : 0	Volatile Write Cache Not Present

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
  subnqn    : 
  ioccsz    : 0
  iorcsz    : 0
  icdoff    : 0
  ctrattr   : 0
    [0:0] : 0	Dynamic Controller Model

  msdbd     : 0
  ps    0 : mp:2.80W operational enlat:1000000 exlat:30000 rrt:0 rrl:0
            rwt:0 rwl:0 idle_power:- active_power:-
  ps    1 : mp:2.20W operational enlat:1000000 exlat:30000 rrt:1 rrl:0
            rwt:1 rwl:0 idle_power:- active_power:-
  ps    2 : mp:1.80W operational enlat:1000000 exlat:30000 rrt:2 rrl:0
            rwt:2 rwl:0 idle_power:- active_power:-
  ps    3 : mp:0.0080W non-operational enlat:1150000 exlat:30000 rrt:0 rrl:0
            rwt:0 rwl:0 idle_power:- active_power:-
  ```

  ```
  # nvme list-ns /dev/nvme0n1
  [   0]:0x1
  ```

  ```
  # nvme id-ns -H /dev/nvme0n1 --namespace-id=1
  NVME Identify Namespace 1:
  nsze    : 0x3680800
  ncap    : 0x3680800
  nuse    : 0x3680800
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

  fpi     : 0
    [7:7] : 0	Format Progress Indicator Not Supported

  dlfeat  : 0
    [4:4] : 0	Guard Field of Deallocated Logical Blocks is set to 0xFFFF
    [3:3] : 0	Deallocate Bit in the Write Zeroes Command is Not Supported
    [2:0] : 0	Bytes Read From a Deallocated Logical Block and its Metadata are Not Reported

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
  eui64   : 5cd2e46a1bd10100
  LBA Format  0 : Metadata Size: 0   bytes - Data Size: 512 bytes - Relative Performance: 0x2 Good (in use)
  ```
</details>
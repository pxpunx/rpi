# Product Information

| Product | [NV2 PCIe 4.0 NVMe SSD 250GB – 2TB - Kingston Technology](https://www.kingston.com/en/ssd/nv2-nvme-pcie-ssd) |
|:-|:-|
|----|----|
| *Name* | Kingston NV2 |
| *Model* | SNV2S/250G |
| *Capacity* | 250GB |
| *Form Factor* | M.2 2280 |
| *Key* | M |
| *Interface* | NVMe |
| *Controller* | Varies <sup>1</sup> |
| *NAND* | Varies <sup>1</sup> |
| *DRAM* | - |
| *Bootable* | :white_check_mark: |

 <sup>1</sup> *Controller and NAND varies, apparently even between different batches of the same capacity drives.*

* [Kingston NV2 SSD Review: Cheap But Risky](https://www.tomshardware.com/reviews/kingston-nv2-ssd)

# Device Name

```
# lsblk | grep nvme[01]
nvme0n1     259:0    0 232.9G  0 disk
```

# Device Information

<details>
  <summary>Click here to expand...</summary>
  
  ```
  # lspci -vvv -s 01:00.0
  01:00.0 Non-Volatile memory controller: Kingston Technology Company, Inc. Device 5017 (rev 03) (prog-if 02 [NVM Express])
    Subsystem: Kingston Technology Company, Inc. Device 5017
    Control: I/O- Mem+ BusMaster+ SpecCycle- MemWINV- VGASnoop- ParErr- Stepping- SERR- FastB2B- DisINTx+
    Status: Cap+ 66MHz- UDF- FastB2B- ParErr- DEVSEL=fast >TAbort- <TAbort- <MAbort- >SERR- <PERR- INTx-
    Latency: 0
    Interrupt: pin A routed to IRQ 63
    Region 0: Memory at 600000000 (64-bit, non-prefetchable) [size=16K]
    Capabilities: [40] Power Management version 3
      Flags: PMEClk- DSI- D1- D2- AuxCurrent=0mA PME(D0-,D1-,D2-,D3hot-,D3cold-)
      Status: D0 NoSoftRst+ PME-Enable- DSel=0 DScale=0 PME-
    Capabilities: [50] MSI: Enable- Count=1/8 Maskable+ 64bit+
      Address: 0000000000000000  Data: 0000
      Masking: 00000000  Pending: 00000000
    Capabilities: [70] Express (v2) Endpoint, MSI 00
      DevCap:	MaxPayload 128 bytes, PhantFunc 0, Latency L0s unlimited, L1 unlimited
        ExtTag- AttnBtn- AttnInd- PwrInd- RBE+ FLReset+ SlotPowerLimit 0.000W
      DevCtl:	CorrErr- NonFatalErr- FatalErr- UnsupReq-
        RlxdOrd+ ExtTag- PhantFunc- AuxPwr- NoSnoop- FLReset-
        MaxPayload 128 bytes, MaxReadReq 256 bytes
      DevSta:	CorrErr- NonFatalErr- FatalErr- UnsupReq- AuxPwr- TransPend-
      LnkCap:	Port #0, Speed 16GT/s, Width x4, ASPM not supported
        ClockPM+ Surprise- LLActRep- BwNot- ASPMOptComp+
      LnkCtl:	ASPM Disabled; RCB 64 bytes, Disabled- CommClk-
        ExtSynch- ClockPM- AutWidDis- BWInt- AutBWInt-
      LnkSta:	Speed 5GT/s (downgraded), Width x1 (downgraded)
        TrErr- Train- SlotClk+ DLActive- BWMgmt- ABWMgmt-
      DevCap2: Completion Timeout: Range ABCD, TimeoutDis+ NROPrPrP- LTR+
        10BitTagComp+ 10BitTagReq- OBFF Via message, ExtFmt- EETLPPrefix-
        EmergencyPowerReduction Not Supported, EmergencyPowerReductionInit-
        FRS- TPHComp- ExtTPHComp-
        AtomicOpsCap: 32bit- 64bit- 128bitCAS-
      DevCtl2: Completion Timeout: 50us to 50ms, TimeoutDis- LTR+ OBFF Disabled,
        AtomicOpsCtl: ReqEn-
      LnkCap2: Supported Link Speeds: 2.5-16GT/s, Crosslink- Retimer+ 2Retimers+ DRS-
      LnkCtl2: Target Link Speed: 16GT/s, EnterCompliance- SpeedDis-
        Transmit Margin: Normal Operating Range, EnterModifiedCompliance- ComplianceSOS-
        Compliance De-emphasis: -6dB
      LnkSta2: Current De-emphasis Level: -3.5dB, EqualizationComplete- EqualizationPhase1-
        EqualizationPhase2- EqualizationPhase3- LinkEqualizationRequest-
        Retimer- 2Retimers- CrosslinkRes: Upstream Port
    Capabilities: [b0] MSI-X: Enable+ Count=16 Masked-
      Vector table: BAR=0 offset=00002000
      PBA: BAR=0 offset=00002100
    Capabilities: [100 v2] Advanced Error Reporting
      UESta:	DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
      UEMsk:	DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
      UESvrt:	DLP+ SDES+ TLP- FCP+ CmpltTO- CmpltAbrt- UnxCmplt- RxOF+ MalfTLP+ ECRC- UnsupReq- ACSViol-
      CESta:	RxErr- BadTLP- BadDLLP- Rollover- Timeout- AdvNonFatalErr-
      CEMsk:	RxErr- BadTLP- BadDLLP- Rollover- Timeout- AdvNonFatalErr+
      AERCap:	First Error Pointer: 00, ECRCGenCap+ ECRCGenEn- ECRCChkCap+ ECRCChkEn-
        MultHdrRecCap- MultHdrRecEn- TLPPfxPres- HdrLogCap-
      HeaderLog: 00000000 00000000 00000000 00000000
    Capabilities: [158 v1] Secondary PCI Express
      LnkCtl3: LnkEquIntrruptEn- PerformEqu-
      LaneErrStat: 0
    Capabilities: [178 v1] Physical Layer 16.0 GT/s <?>
    Capabilities: [19c v1] Lane Margining at the Receiver <?>
    Capabilities: [1b4 v1] Latency Tolerance Reporting
      Max snoop latency: 0ns
      Max no snoop latency: 0ns
    Capabilities: [1bc v1] L1 PM Substates
      L1SubCap: PCI-PM_L1.2- PCI-PM_L1.1- ASPM_L1.2- ASPM_L1.1- L1_PM_Substates-
      L1SubCtl1: PCI-PM_L1.2- PCI-PM_L1.1- ASPM_L1.2- ASPM_L1.1-
      L1SubCtl2:
    Kernel driver in use: nvme
  ```
</details>

# Disk Information

```
# fdisk -l /dev/nvme0n1
Disk /dev/nvme0n1: 232.89 GiB, 250059350016 bytes, 488397168 sectors
Disk model: KINGSTON SNV2S250G                      
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
```

# Filesystem Information

```
# df -Th /dev/nvme0n1
Filesystem     Type  Size  Used Avail Use% Mounted on
/dev/nvme0n1   ext4  229G   28K  217G   1% /mnt/sda1
```

# Benchmarks

## PiBenchmarks.com

Credit: [James C. Chambers](https://jamesachambers.com/) ([source](https://raw.githubusercontent.com/TheRemote/PiBenchmarks/master/Storage.sh))

Full benchmark: [pibenchmarks.com #67389](https://pibenchmarks.com/benchmark/67389/)

| Category | Test | Result |
|:-|:-|:-|
| DD | Disk Write | 129 MB/s |
| HDParm | Disk Read | 364.92 MB/s |
| HDParm | Cached Disk Read | 362.09 MB/s |
| FIO | 4K Random Read | 12,397 IOPS |
| FIO | 4K Random Write | 42,845 IOPS |
| FIO | 4K Random Read | 49,588 KB/s |
| FIO | 4K Random Write | 171,380 KB/s |
| IOZone | 4K Read | 100,133 KB/s |
| IOZone | 4K Write | 57,832 KB/s |
| IOZone | 4K Random Read | 46,770 KB/s |
| IOZone | 4K Random Write | 89,629 KB/s |
| **Score** | | 16,687 |

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
  Jobs: 4 (f=4): [R(4)][30.0%][r=382MiB/s][r=382 IOPS][eta 00m:07s]
  Jobs: 4 (f=4): [R(4)][50.0%][r=394MiB/s][r=394 IOPS][eta 00m:05s] 
  Jobs: 4 (f=4): [R(4)][63.6%][r=393MiB/s][r=393 IOPS][eta 00m:04s]
  Jobs: 4 (f=4): [R(4)][72.7%][r=391MiB/s][r=391 IOPS][eta 00m:03s]
  Jobs: 4 (f=4): [R(4)][81.8%][r=333MiB/s][r=332 IOPS][eta 00m:02s]
  Jobs: 4 (f=4): [R(4)][90.9%][r=386MiB/s][r=385 IOPS][eta 00m:01s]
  Jobs: 4 (f=4): [R(4)][100.0%][r=384MiB/s][r=384 IOPS][eta 00m:00s]
  fio-rand-read-sequential: (groupid=0, jobs=4): err= 0: pid=587: Sat Feb 18 19:26:28 2023
    read: IOPS=390, BW=390MiB/s (409MB/s)(4031MiB/10331msec)
      slat (usec): min=119, max=132998, avg=9792.26, stdev=23442.09
      clat (msec): min=108, max=1328, avg=637.81, stdev=238.48
      lat (msec): min=111, max=1329, avg=647.60, stdev=241.66
      clat percentiles (msec):
      |  1.00th=[  150],  5.00th=[  326], 10.00th=[  397], 20.00th=[  481],
      | 30.00th=[  485], 40.00th=[  485], 50.00th=[  584], 60.00th=[  642],
      | 70.00th=[  743], 80.00th=[  961], 90.00th=[  978], 95.00th=[ 1045],
      | 99.00th=[ 1133], 99.50th=[ 1200], 99.90th=[ 1301], 99.95th=[ 1318],
      | 99.99th=[ 1334]
    bw (  KiB/s): min=219136, max=536576, per=96.76%, avg=386588.90, stdev=22041.92, samples=80
    iops        : min=  214, max=  524, avg=376.40, stdev=21.51, samples=80
    lat (msec)   : 250=3.67%, 500=41.73%, 750=25.33%, 1000=23.37%, 2000=5.90%
    cpu          : usr=0.15%, sys=4.22%, ctx=3876, majf=0, minf=65639
    IO depths    : 1=0.1%, 2=0.2%, 4=0.4%, 8=0.8%, 16=1.6%, 32=3.2%, >=64=93.7%
      submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
      complete  : 0=0.0%, 4=99.9%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.1%, >=64=0.0%
      issued rwts: total=4031,0,0,0 short=0,0,0,0 dropped=0,0,0,0
      latency   : target=0, window=0, percentile=100.00%, depth=64

  Run status group 0 (all jobs):
    READ: bw=390MiB/s (409MB/s), 390MiB/s-390MiB/s (409MB/s-409MB/s), io=4031MiB (4227MB), run=10331-10331msec

  Disk stats (read/write):
    nvme0n1: ios=15828/182, merge=0/3, ticks=7187344/60250, in_queue=7248074, util=99.22%

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

    Run began: Sat Feb 18 19:26:28 2023

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
            102400    1024   337889   338181                     352902   325248                                                                

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

    Run began: Sat Feb 18 19:26:30 2023

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
            102400       4    53423    87693                      42929    83166                                                                

  iozone test complete.

  Disk benchmark complete!
  ```
</details>
# Product Information

| Product | [Crucial P3 NVMe SSD](https://www.crucial.com/products/ssd/crucial-p3-ssd) |
|:-|:-|
|----|----|
| *Name* | Crucial P3 |
| *Model* | CT500P3SSD8 |
| *Capacity* | 500GB |
| *Form Factor* | M.2 2280 |
| *Key* | M |
| *Interface* | NVMe |
| *Bootable* | YES |

# Device Name

```
root@default-pi:~# lsblk | grep nvme[01]
nvme0n1     259:0    0 465.8G  0 disk 
```

# Device Information

<details>
  <summary>Click here to expand...</summary>
  
  ```
  root@default-pi:~# lspci -vvv -s 01:00.0
  01:00.0 Non-Volatile memory controller: Micron/Crucial Technology Device 540a (rev 01) (prog-if 02 [NVM Express])
    Subsystem: Micron/Crucial Technology Device 5021
    Control: I/O- Mem+ BusMaster+ SpecCycle- MemWINV- VGASnoop- ParErr- Stepping- SERR- FastB2B- DisINTx+
    Status: Cap+ 66MHz- UDF- FastB2B- ParErr- DEVSEL=fast >TAbort- <TAbort- <MAbort- >SERR- <PERR- INTx-
    Latency: 0
    Interrupt: pin A routed to IRQ 63
    Region 0: Memory at 600000000 (64-bit, non-prefetchable) [size=16K]
    Capabilities: [80] Express (v2) Endpoint, MSI 00
      DevCap:	MaxPayload 512 bytes, PhantFunc 0, Latency L0s unlimited, L1 unlimited
        ExtTag+ AttnBtn- AttnInd- PwrInd- RBE+ FLReset+ SlotPowerLimit 0.000W
      DevCtl:	CorrErr- NonFatalErr- FatalErr- UnsupReq-
        RlxdOrd+ ExtTag+ PhantFunc- AuxPwr- NoSnoop+ FLReset-
        MaxPayload 128 bytes, MaxReadReq 512 bytes
      DevSta:	CorrErr- NonFatalErr- FatalErr- UnsupReq- AuxPwr- TransPend-
      LnkCap:	Port #1, Speed 8GT/s, Width x4, ASPM L1, Exit Latency L1 unlimited
        ClockPM- Surprise- LLActRep- BwNot- ASPMOptComp+
      LnkCtl:	ASPM Disabled; RCB 64 bytes, Disabled- CommClk+
        ExtSynch- ClockPM- AutWidDis- BWInt- AutBWInt-
      LnkSta:	Speed 5GT/s (downgraded), Width x1 (downgraded)
        TrErr- Train- SlotClk+ DLActive- BWMgmt- ABWMgmt-
      DevCap2: Completion Timeout: Range ABCD, TimeoutDis+ NROPrPrP- LTR+
        10BitTagComp- 10BitTagReq- OBFF Not Supported, ExtFmt+ EETLPPrefix-
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
    Capabilities: [d0] MSI-X: Enable+ Count=9 Masked-
      Vector table: BAR=0 offset=00002000
      PBA: BAR=0 offset=00003000
    Capabilities: [e0] MSI: Enable- Count=1/8 Maskable+ 64bit+
      Address: 0000000000000000  Data: 0000
      Masking: 00000000  Pending: 00000000
    Capabilities: [f8] Power Management version 3
      Flags: PMEClk- DSI- D1- D2- AuxCurrent=0mA PME(D0-,D1-,D2-,D3hot-,D3cold-)
      Status: D0 NoSoftRst+ PME-Enable- DSel=0 DScale=0 PME-
    Capabilities: [100 v1] Latency Tolerance Reporting
      Max snoop latency: 0ns
      Max no snoop latency: 0ns
    Capabilities: [110 v1] L1 PM Substates
      L1SubCap: PCI-PM_L1.2+ PCI-PM_L1.1+ ASPM_L1.2+ ASPM_L1.1+ L1_PM_Substates+
          PortCommonModeRestoreTime=10us PortTPowerOnTime=300us
      L1SubCtl1: PCI-PM_L1.2- PCI-PM_L1.1- ASPM_L1.2- ASPM_L1.1-
          T_CommonMode=0us LTR1.2_Threshold=294912ns
      L1SubCtl2: T_PwrOn=300us
    Capabilities: [128 v1] Alternative Routing-ID Interpretation (ARI)
      ARICap:	MFVC- ACS-, Next Function: 0
      ARICtl:	MFVC- ACS-, Function Group: 0
    Capabilities: [1e0 v1] Data Link Feature <?>
    Capabilities: [200 v2] Advanced Error Reporting
      UESta:	DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
      UEMsk:	DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
      UESvrt:	DLP+ SDES- TLP- FCP+ CmpltTO- CmpltAbrt- UnxCmplt- RxOF+ MalfTLP+ ECRC- UnsupReq- ACSViol-
      CESta:	RxErr- BadTLP- BadDLLP- Rollover- Timeout- AdvNonFatalErr-
      CEMsk:	RxErr- BadTLP- BadDLLP- Rollover- Timeout- AdvNonFatalErr+
      AERCap:	First Error Pointer: 00, ECRCGenCap- ECRCGenEn- ECRCChkCap+ ECRCChkEn-
        MultHdrRecCap- MultHdrRecEn- TLPPfxPres- HdrLogCap-
      HeaderLog: 00000000 00000000 00000000 00000000
    Capabilities: [300 v1] Secondary PCI Express
      LnkCtl3: LnkEquIntrruptEn- PerformEqu-
      LaneErrStat: 0
    Kernel driver in use: nvme
  ```
</details>

# Disk Information

```
root@default-pi:~# fdisk -l /dev/nvme0n1
Disk /dev/nvme0n1: 465.76 GiB, 500107862016 bytes, 976773168 sectors
Disk model: CT500P3SSD8                             
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
```

# Filesystem Information

```
root@default-pi:~# df -Th /dev/nvme0n1
Filesystem     Type  Size  Used Avail Use% Mounted on
/dev/nvme0n1   ext4  458G   28K  435G   1% /mnt/sda1
```

# Benchmarks

## PiBenchmarks.com

Credit: [James C. Chambers](https://jamesachambers.com/) ([source](https://raw.githubusercontent.com/TheRemote/PiBenchmarks/master/Storage.sh))

Full benchmark: [pibenchmarks.com #67377](https://pibenchmarks.com/benchmark/67377/)

| Category | Test | Result |
|:-|:-|:-|
| DD | Disk Write | 132 MB/s |
| HDParm | Disk Read | 352.04 MB/s |
| HDParm | Cached Disk Read | 349.51 MB/s |
| FIO | 4k Random Read | 12,132 IOPS |
| FIO | 4k Random Write | 41,967 IOPS |
| FIO | 4k Random Read | 48,530 KB/s |
| FIO | 4k Random Write | 167,868 KB/s |
| IOZone | 4k Read | 90,193 KB/s |
| IOZone | 4k Write | 57,748 KB/s |
| IOZone | 4k Random Read | 43,397 KB/s |
| IOZone | 4k Random Write | 89,487 KB/s |
| **Score** | | 16,407 |

## Jeff Geerling

Credit: [Jeff Geerling](https://www.jeffgeerling.com/) ([source](https://raw.githubusercontent.com/geerlingguy/pi-cluster/master/benchmarks/disk-benchmark.sh))

<details>
  <summary>Click here to expand...</summary>

  ```
  root@default-pi:~# DEVICE_UNDER_TEST=/dev/nvme0n1 ./disk-benchmark.sh

  Raspberry Pi disk benchmarks
  Running fio sequential read test...
  fio-rand-read-sequential: (g=0): rw=read, bs=(R) 1024KiB-1024KiB, (W) 1024KiB-1024KiB, (T) 1024KiB-1024KiB, ioengine=libaio, iodepth=64
  ...
  fio-3.25
  Starting 4 processes
  Jobs: 4 (f=4): [R(4)][36.4%][r=379MiB/s][r=378 IOPS][eta 00m:07s]
  Jobs: 4 (f=4): [R(4)][45.5%][r=378MiB/s][r=377 IOPS][eta 00m:06s]
  Jobs: 4 (f=4): [R(4)][54.5%][r=372MiB/s][r=371 IOPS][eta 00m:05s]
  Jobs: 4 (f=4): [R(4)][63.6%][r=379MiB/s][r=379 IOPS][eta 00m:04s]
  Jobs: 4 (f=4): [R(4)][72.7%][r=382MiB/s][r=382 IOPS][eta 00m:03s]
  Jobs: 4 (f=4): [R(4)][81.8%][r=361MiB/s][r=360 IOPS][eta 00m:02s]
  Jobs: 4 (f=4): [R(4)][90.9%][r=357MiB/s][r=356 IOPS][eta 00m:01s]
  Jobs: 4 (f=4): [R(4)][100.0%][r=357MiB/s][r=356 IOPS][eta 00m:00s]
  fio-rand-read-sequential: (groupid=0, jobs=4): err= 0: pid=611: Sat Feb 18 17:00:17 2023
    read: IOPS=369, BW=370MiB/s (388MB/s)(3965MiB/10721msec)
      slat (usec): min=119, max=5501, avg=445.07, stdev=785.47
      clat (msec): min=34, max=1776, avg=676.75, stdev=254.69
      lat (msec): min=34, max=1777, avg=677.20, stdev=254.39
      clat percentiles (msec):
      |  1.00th=[  140],  5.00th=[  271], 10.00th=[  359], 20.00th=[  489],
      | 30.00th=[  667], 40.00th=[  676], 50.00th=[  676], 60.00th=[  676],
      | 70.00th=[  676], 80.00th=[  701], 90.00th=[ 1070], 95.00th=[ 1083],
      | 99.00th=[ 1552], 99.50th=[ 1653], 99.90th=[ 1754], 99.95th=[ 1770],
      | 99.99th=[ 1770]
    bw (  KiB/s): min=116537, max=552960, per=98.21%, avg=371942.09, stdev=29226.31, samples=82
    iops        : min=  111, max=  540, avg=362.50, stdev=28.60, samples=82
    lat (msec)   : 50=0.13%, 100=0.25%, 250=4.26%, 500=15.56%, 750=61.51%
    lat (msec)   : 1000=4.54%, 2000=13.75%
    cpu          : usr=0.10%, sys=4.62%, ctx=4014, majf=0, minf=65639
    IO depths    : 1=0.1%, 2=0.2%, 4=0.4%, 8=0.8%, 16=1.6%, 32=3.2%, >=64=93.6%
      submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
      complete  : 0=0.0%, 4=99.9%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.1%, >=64=0.0%
      issued rwts: total=3965,0,0,0 short=0,0,0,0 dropped=0,0,0,0
      latency   : target=0, window=0, percentile=100.00%, depth=64

  Run status group 0 (all jobs):
    READ: bw=370MiB/s (388MB/s), 370MiB/s-370MiB/s (388MB/s-388MB/s), io=3965MiB (4158MB), run=10721-10721msec

  Disk stats (read/write):
    nvme0n1: ios=15773/222, merge=0/2, ticks=10327768/48223, in_queue=10376230, util=99.16%

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

    Run began: Sat Feb 18 17:00:17 2023

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
            102400    1024   241174   243971                     330626   297308                                                                

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

    Run began: Sat Feb 18 17:00:19 2023

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
            102400       4    36369    54729                      40086    56902                                                                

  iozone test complete.

  Disk benchmark complete!
  ```
</details>
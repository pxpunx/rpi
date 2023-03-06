# Product Information

| Product | [WD_BLACK SN770 NVMe™ SSD](https://www.westerndigital.com/products/internal-drives/wd-black-sn770-nvme-ssd) |
|:-|:-|
|----|----|
| *Name* | WD Black SN770 |
| *Model* | WDS250G3X0E |
| *Capacity* | 250GB |
| *Form Factor* | M.2 2280 |
| *Key* | M |
| *Interface* | NVMe |
| *Controller* | Custom SanDisk |
| *NAND* | 112L BiCS 5 3D TLC |
| *DRAM* | - |
| *Boot Disk* | :white_check_mark: |
| *Non-Boot Disk* | :white_check_mark: |
| *Adapter* | Ableconn M2MN-151M |

* [Western Digital Introduces WD_BLACK SN770: A DRAM-less PCIe 4.0 M.2 NVMe SSD](https://www.anandtech.com/show/17238/western-digital-introduces-wd_black-sn770-a-dramless-pcie-40-m2-nvme-ssd)

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
  01:00.0 Non-Volatile memory controller: Sandisk Corp Device 5017 (rev 01) (prog-if 02 [NVM Express])
    Subsystem: Sandisk Corp Device 5017
    Control: I/O- Mem+ BusMaster+ SpecCycle- MemWINV- VGASnoop- ParErr- Stepping- SERR- FastB2B- DisINTx+
    Status: Cap+ 66MHz- UDF- FastB2B- ParErr- DEVSEL=fast >TAbort- <TAbort- <MAbort- >SERR- <PERR- INTx-
    Latency: 0
    Interrupt: pin A routed to IRQ 63
    Region 0: Memory at 600000000 (64-bit, non-prefetchable) [size=16K]
    Capabilities: [80] Power Management version 3
      Flags: PMEClk- DSI- D1- D2- AuxCurrent=0mA PME(D0-,D1-,D2-,D3hot-,D3cold-)
      Status: D0 NoSoftRst+ PME-Enable- DSel=0 DScale=0 PME-
    Capabilities: [90] MSI: Enable- Count=1/32 Maskable- 64bit+
      Address: 0000000000000000  Data: 0000
    Capabilities: [b0] MSI-X: Enable+ Count=65 Masked-
      Vector table: BAR=0 offset=00003000
      PBA: BAR=0 offset=00002000
    Capabilities: [c0] Express (v2) Endpoint, MSI 00
      DevCap:	MaxPayload 512 bytes, PhantFunc 0, Latency L0s <1us, L1 unlimited
        ExtTag- AttnBtn- AttnInd- PwrInd- RBE+ FLReset+ SlotPowerLimit 0.000W
      DevCtl:	CorrErr- NonFatalErr- FatalErr- UnsupReq-
        RlxdOrd+ ExtTag+ PhantFunc- AuxPwr- NoSnoop+ FLReset-
        MaxPayload 128 bytes, MaxReadReq 512 bytes
      DevSta:	CorrErr- NonFatalErr- FatalErr- UnsupReq- AuxPwr- TransPend-
      LnkCap:	Port #0, Speed 16GT/s, Width x4, ASPM L1, Exit Latency L1 <8us
        ClockPM+ Surprise- LLActRep- BwNot- ASPMOptComp+
      LnkCtl:	ASPM Disabled; RCB 64 bytes, Disabled- CommClk+
        ExtSynch+ ClockPM- AutWidDis- BWInt- AutBWInt-
      LnkSta:	Speed 5GT/s (downgraded), Width x1 (downgraded)
        TrErr- Train- SlotClk+ DLActive- BWMgmt- ABWMgmt-
      DevCap2: Completion Timeout: Range B, TimeoutDis+ NROPrPrP- LTR+
        10BitTagComp+ 10BitTagReq- OBFF Not Supported, ExtFmt+ EETLPPrefix-
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
        Retimer- 2Retimers- CrosslinkRes: unsupported
    Capabilities: [100 v2] Advanced Error Reporting
      UESta:	DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
      UEMsk:	DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
      UESvrt:	DLP+ SDES- TLP- FCP+ CmpltTO- CmpltAbrt- UnxCmplt- RxOF+ MalfTLP+ ECRC- UnsupReq- ACSViol-
      CESta:	RxErr- BadTLP- BadDLLP- Rollover- Timeout- AdvNonFatalErr-
      CEMsk:	RxErr- BadTLP- BadDLLP- Rollover- Timeout- AdvNonFatalErr+
      AERCap:	First Error Pointer: 00, ECRCGenCap+ ECRCGenEn- ECRCChkCap+ ECRCChkEn-
        MultHdrRecCap- MultHdrRecEn- TLPPfxPres- HdrLogCap-
      HeaderLog: 00000000 00000000 00000000 00000000
    Capabilities: [1b8 v1] Latency Tolerance Reporting
      Max snoop latency: 0ns
      Max no snoop latency: 0ns
    Capabilities: [300 v1] Secondary PCI Express
      LnkCtl3: LnkEquIntrruptEn- PerformEqu-
      LaneErrStat: 0
    Capabilities: [900 v1] L1 PM Substates
      L1SubCap: PCI-PM_L1.2+ PCI-PM_L1.1+ ASPM_L1.2+ ASPM_L1.1- L1_PM_Substates+
          PortCommonModeRestoreTime=32us PortTPowerOnTime=10us
      L1SubCtl1: PCI-PM_L1.2- PCI-PM_L1.1- ASPM_L1.2- ASPM_L1.1-
          T_CommonMode=0us LTR1.2_Threshold=32768ns
      L1SubCtl2: T_PwrOn=10us
    Capabilities: [910 v1] Data Link Feature <?>
    Capabilities: [920 v1] Lane Margining at the Receiver <?>
    Capabilities: [9c0 v1] Physical Layer 16.0 GT/s <?>
    Kernel driver in use: nvme
  ```
</details>

# Disk Information

```
# fdisk -l /dev/nvme0n1
Disk /dev/nvme0n1: 232.89 GiB, 250059350016 bytes, 488397168 sectors
Disk model: WD_BLACK SN770 250GB                    
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

Full benchmark: [pibenchmarks.com #67927](https://pibenchmarks.com/benchmark/67927/)

| Category | Test | Result |
|:-|:-|:-|
| DD | Disk Write | 133 MB/s |
| HDParm | Disk Read | 290.97 MB/s |
| HDParm | Cached Disk Read | 293.72 MB/s |
| FIO | 4k Random Read | 40960 IOPS |
| FIO | 4k Random Write | 12427 IOPS |
| FIO | 4k Random Read | 163840 KB/s |
| FIO | 4k Random Write | 49708 KB/s |
| IOZone | 4k Read | 91316 KB/s |
| IOZone | 4k Write | 58522 KB/s |
| IOZone | 4k Random Read | 53852 KB/s |
| IOZone | 4k Random Write | 92104 KB/s |
| **Score** | | 17105 |

## Jeff Geerling

Credit: [Jeff Geerling](https://www.jeffgeerling.com/) ([source](https://raw.githubusercontent.com/geerlingguy/pi-cluster/master/benchmarks/disk-benchmark.sh))

<details>
  <summary>Click here to expand...</summary>

  ```
  Raspberry Pi disk benchmarks
  Running fio sequential read test...
  fio-rand-read-sequential: (g=0): rw=read, bs=(R) 1024KiB-1024KiB, (W) 1024KiB-1024KiB, (T) 1024KiB-1024KiB, ioengine=libaio, iodepth=64
  ...
  fio-3.25
  Starting 4 processes
  Jobs: 4 (f=4): [R(4)][36.4%][r=398MiB/s][r=398 IOPS][eta 00m:07s]
  Jobs: 4 (f=4): [R(4)][54.5%][r=399MiB/s][r=398 IOPS][eta 00m:05s] 
  Jobs: 4 (f=4): [R(4)][63.6%][r=398MiB/s][r=397 IOPS][eta 00m:04s]
  Jobs: 4 (f=4): [R(4)][72.7%][r=397MiB/s][r=397 IOPS][eta 00m:03s]
  Jobs: 4 (f=4): [R(4)][81.8%][r=399MiB/s][r=398 IOPS][eta 00m:02s]
  Jobs: 4 (f=4): [R(4)][90.9%][r=399MiB/s][r=398 IOPS][eta 00m:01s]
  Jobs: 4 (f=4): [R(4)][100.0%][r=398MiB/s][r=397 IOPS][eta 00m:00s]
  fio-rand-read-sequential: (groupid=0, jobs=4): err= 0: pid=1178: Sun Mar  5 12:33:53 2023
    read: IOPS=397, BW=398MiB/s (417MB/s)(4231MiB/10641msec)
      slat (usec): min=121, max=6202, avg=371.29, stdev=574.69
      clat (msec): min=124, max=1270, avg=637.10, stdev=144.41
      lat (msec): min=126, max=1270, avg=637.48, stdev=144.05
      clat percentiles (msec):
      |  1.00th=[  146],  5.00th=[  393], 10.00th=[  514], 20.00th=[  642],
      | 30.00th=[  642], 40.00th=[  642], 50.00th=[  642], 60.00th=[  642],
      | 70.00th=[  642], 80.00th=[  642], 90.00th=[  743], 95.00th=[  860],
      | 99.00th=[ 1167], 99.50th=[ 1217], 99.90th=[ 1250], 99.95th=[ 1267],
      | 99.99th=[ 1267]
    bw (  KiB/s): min=288472, max=526336, per=100.00%, avg=407286.20, stdev=12484.54, samples=80
    iops        : min=  280, max=  514, avg=397.10, stdev=12.20, samples=80
    lat (msec)   : 250=3.17%, 500=6.29%, 750=80.71%, 1000=7.35%, 2000=2.48%
    cpu          : usr=0.15%, sys=4.15%, ctx=4247, majf=0, minf=65638
    IO depths    : 1=0.1%, 2=0.2%, 4=0.4%, 8=0.8%, 16=1.5%, 32=3.0%, >=64=94.0%
      submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
      complete  : 0=0.0%, 4=99.9%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.1%, >=64=0.0%
      issued rwts: total=4231,0,0,0 short=0,0,0,0 dropped=0,0,0,0
      latency   : target=0, window=0, percentile=100.00%, depth=64

  Run status group 0 (all jobs):
    READ: bw=398MiB/s (417MB/s), 398MiB/s-398MiB/s (417MB/s-417MB/s), io=4231MiB (4437MB), run=10641-10641msec

  Disk stats (read/write):
    nvme0n1: ios=16560/4, merge=0/0, ticks=10163954/6, in_queue=10163967, util=99.16%

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

    Run began: Sun Mar  5 12:33:53 2023

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
            102400    1024   388250   392446                     290025   392099                                                                

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

    Run began: Sun Mar  5 12:33:55 2023

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
            102400       4    56018    87989                      51728    85463                                                                

  iozone test complete.

  Disk benchmark complete!
  ```
</details>
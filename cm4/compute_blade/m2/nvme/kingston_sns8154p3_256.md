# Product Information

| Product | [Kingston Design-In SSDs (PDF)](https://media.kingston.com/pdfs/emmc/MKF-815_design-in_SSD_lr.pdf) |
|:-|:-|
|----|----|
| *Name* | Kingston SNS8154P3 |
| *Model* | RBUSNS8154P3256GJ1 |
| *Capacity* | 256GB |
| *Form Factor* | M.2 2280 |
| *Key* | M + B |
| *Interface* | NVMe |
| *Controller* | Phison PS5008-E8-10 |
| *NAND* | 96L 3D TLC |
| *DRAM* | - |
| *Boot Disk* | :white_check_mark: |
| *Non-Boot Disk* | :white_check_mark: |
| *Adapter* | Ableconn M2MN-151M |

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
  01:00.0 Non-Volatile memory controller: Kingston Technology Company, Inc. U-SNS8154P3 NVMe SSD (rev 01) (prog-if 02 [NVM Express])
    Subsystem: Kingston Technology Company, Inc. U-SNS8154P3 NVMe SSD
    Control: I/O- Mem+ BusMaster+ SpecCycle- MemWINV- VGASnoop- ParErr- Stepping- SERR- FastB2B- DisINTx+
    Status: Cap+ 66MHz- UDF- FastB2B- ParErr- DEVSEL=fast >TAbort- <TAbort- <MAbort- >SERR- <PERR- INTx-
    Latency: 0
    Interrupt: pin A routed to IRQ 63
    Region 0: Memory at 600000000 (64-bit, non-prefetchable) [size=16K]
    Region 2: I/O ports at <unassigned> [disabled]
    Capabilities: [80] Express (v2) Endpoint, MSI 00
      DevCap:	MaxPayload 128 bytes, PhantFunc 0, Latency L0s <64ns, L1 unlimited
        ExtTag+ AttnBtn- AttnInd- PwrInd- RBE+ FLReset+ SlotPowerLimit 0.000W
      DevCtl:	CorrErr- NonFatalErr- FatalErr- UnsupReq-
        RlxdOrd+ ExtTag+ PhantFunc- AuxPwr- NoSnoop+ FLReset-
        MaxPayload 128 bytes, MaxReadReq 512 bytes
      DevSta:	CorrErr- NonFatalErr- FatalErr- UnsupReq- AuxPwr- TransPend-
      LnkCap:	Port #1, Speed 8GT/s, Width x2, ASPM L0s L1, Exit Latency L0s unlimited, L1 unlimited
        ClockPM- Surprise- LLActRep- BwNot- ASPMOptComp+
      LnkCtl:	ASPM Disabled; RCB 64 bytes, Disabled- CommClk-
        ExtSynch- ClockPM- AutWidDis- BWInt- AutBWInt-
      LnkSta:	Speed 5GT/s (downgraded), Width x1 (downgraded)
        TrErr- Train- SlotClk- DLActive- BWMgmt- ABWMgmt-
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
    Capabilities: [e0] MSI: Enable- Count=1/8 Maskable- 64bit+
      Address: 0000000000000000  Data: 0000
    Capabilities: [f8] Power Management version 3
      Flags: PMEClk- DSI- D1- D2- AuxCurrent=0mA PME(D0-,D1-,D2-,D3hot-,D3cold-)
      Status: D0 NoSoftRst+ PME-Enable- DSel=0 DScale=0 PME-
    Capabilities: [100 v1] Vendor Specific Information: ID=1556 Rev=1 Len=008 <?>
    Capabilities: [108 v1] Latency Tolerance Reporting
      Max snoop latency: 0ns
      Max no snoop latency: 0ns
    Capabilities: [110 v1] L1 PM Substates
      L1SubCap: PCI-PM_L1.2+ PCI-PM_L1.1+ ASPM_L1.2+ ASPM_L1.1+ L1_PM_Substates+
          PortCommonModeRestoreTime=10us PortTPowerOnTime=200us
      L1SubCtl1: PCI-PM_L1.2- PCI-PM_L1.1- ASPM_L1.2- ASPM_L1.1-
          T_CommonMode=0us LTR1.2_Threshold=196608ns
      L1SubCtl2: T_PwrOn=200us
    Capabilities: [128 v1] Alternative Routing-ID Interpretation (ARI)
      ARICap:	MFVC- ACS-, Next Function: 0
      ARICtl:	MFVC- ACS-, Function Group: 0
    Capabilities: [200 v1] Advanced Error Reporting
      UESta:	DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
      UEMsk:	DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
      UESvrt:	DLP+ SDES- TLP- FCP+ CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP+ ECRC- UnsupReq- ACSViol-
      CESta:	RxErr+ BadTLP- BadDLLP- Rollover- Timeout- AdvNonFatalErr+
      CEMsk:	RxErr- BadTLP- BadDLLP- Rollover- Timeout- AdvNonFatalErr+
      AERCap:	First Error Pointer: 00, ECRCGenCap- ECRCGenEn- ECRCChkCap+ ECRCChkEn-
        MultHdrRecCap- MultHdrRecEn- TLPPfxPres- HdrLogCap-
      HeaderLog: 00000001 0000030f f800001c 4397938e
    Capabilities: [300 v1] Secondary PCI Express
      LnkCtl3: LnkEquIntrruptEn- PerformEqu-
      LaneErrStat: 0
    Kernel driver in use: nvme
  ```
</details>

# Disk Information

```
# fdisk -l /dev/nvme0n1
Disk /dev/nvme0n1: 238.47 GiB, 256060514304 bytes, 500118192 sectors
Disk model: KINGSTON RBUSNS8154P3256GJ1             
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: gpt
Disk identifier: A4DE8108-F405-44F9-AB90-7B518FF5735A
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

Full benchmark: [pibenchmarks.com #67931](https://pibenchmarks.com/benchmark/67931/)

| Category | Test | Result |
|:-|:-|:-|
| DD | Disk Write | 95.9 MB/s |
| HDParm | Disk Read | 331.25 MB/s |
| HDParm | Cached Disk Read | 330.07 MB/s |
| FIO | 4k Random Read | 37647 IOPS |
| FIO | 4k Random Write | 6240 IOPS |
| FIO | 4k Random Read | 150588 KB/s |
| FIO | 4k Random Write | 24960 KB/s |
| IOZone | 4k Read | 68147 KB/s |
| IOZone | 4k Write | 44630 KB/s |
| IOZone | 4k Random Read | 29787 KB/s |
| IOZone | 4k Random Write | 58216 KB/s |
| **Score** | | 11252 |

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
  Jobs: 4 (f=4): [R(4)][36.4%][r=396MiB/s][r=396 IOPS][eta 00m:07s]
  Jobs: 4 (f=4): [R(4)][54.5%][r=396MiB/s][r=395 IOPS][eta 00m:05s] 
  Jobs: 4 (f=4): [R(4)][63.6%][r=397MiB/s][r=396 IOPS][eta 00m:04s]
  Jobs: 4 (f=4): [R(4)][72.7%][r=410MiB/s][r=410 IOPS][eta 00m:03s]
  Jobs: 4 (f=4): [R(4)][81.8%][r=396MiB/s][r=396 IOPS][eta 00m:02s]
  Jobs: 4 (f=4): [R(4)][90.9%][r=391MiB/s][r=391 IOPS][eta 00m:01s]
  Jobs: 4 (f=4): [R(4)][100.0%][r=396MiB/s][r=396 IOPS][eta 00m:00s]
  fio-rand-read-sequential: (groupid=0, jobs=4): err= 0: pid=1255: Sun Mar  5 13:18:53 2023
    read: IOPS=395, BW=396MiB/s (415MB/s)(4210MiB/10636msec)
      slat (usec): min=119, max=4518, avg=368.25, stdev=568.86
      clat (msec): min=123, max=5629, avg=640.20, stdev=360.95
      lat (msec): min=125, max=5629, avg=640.57, stdev=360.84
      clat percentiles (msec):
      |  1.00th=[  146],  5.00th=[  401], 10.00th=[  477], 20.00th=[  481],
      | 30.00th=[  485], 40.00th=[  609], 50.00th=[  609], 60.00th=[  609],
      | 70.00th=[  617], 80.00th=[  651], 90.00th=[  944], 95.00th=[  978],
      | 99.00th=[ 1452], 99.50th=[ 3071], 99.90th=[ 5604], 99.95th=[ 5604],
      | 99.99th=[ 5604]
    bw (  KiB/s): min=302846, max=495046, per=99.89%, avg=404891.15, stdev=16932.52, samples=80
    iops        : min=  294, max=  482, avg=393.80, stdev=16.56, samples=80
    lat (msec)   : 250=3.11%, 500=27.67%, 750=51.88%, 1000=14.30%, 2000=2.40%
    lat (msec)   : >=2000=0.64%
    cpu          : usr=0.18%, sys=4.11%, ctx=4228, majf=0, minf=65644
    IO depths    : 1=0.1%, 2=0.2%, 4=0.4%, 8=0.8%, 16=1.5%, 32=3.0%, >=64=94.0%
      submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
      complete  : 0=0.0%, 4=99.9%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.1%, >=64=0.0%
      issued rwts: total=4210,0,0,0 short=0,0,0,0 dropped=0,0,0,0
      latency   : target=0, window=0, percentile=100.00%, depth=64

  Run status group 0 (all jobs):
    READ: bw=396MiB/s (415MB/s), 396MiB/s-396MiB/s (415MB/s-415MB/s), io=4210MiB (4415MB), run=10636-10636msec

  Disk stats (read/write):
    nvme0n1: ios=16487/4, merge=0/0, ticks=9834853/1, in_queue=9834855, util=99.16%

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

    Run began: Sun Mar  5 13:18:53 2023

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
            102400    1024   363580   349013                     358376   363713                                                                

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

    Run began: Sun Mar  5 13:18:54 2023

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
            102400       4    47395    73554                      32022    50023                                                                

  iozone test complete.

  Disk benchmark complete!
  ```
</details>
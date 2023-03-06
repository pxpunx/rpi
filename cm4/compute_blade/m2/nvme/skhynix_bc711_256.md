# Product Information

| Product | |
|:-|:-|
|----|----|
| *Name* | SK hynix BC711 |
| *Model* | HFM256GD3JX016N |
| *Capacity* | 256GB |
| *Form Factor* | M.2 2280 |
| *Key* | M |
| *Interface* | NVMe |
| *Controller* | TBD |
| *NAND* | TBD |
| *DRAM* | TBD |
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
  01:00.0 Non-Volatile memory controller: SK hynix Device 174a (prog-if 02 [NVM Express])
    Subsystem: SK hynix Device 174a
    Control: I/O- Mem+ BusMaster+ SpecCycle- MemWINV- VGASnoop- ParErr- Stepping- SERR- FastB2B- DisINTx+
    Status: Cap+ 66MHz- UDF- FastB2B- ParErr- DEVSEL=fast >TAbort- <TAbort- <MAbort- >SERR- <PERR- INTx-
    Latency: 0
    Interrupt: pin A routed to IRQ 63
    Region 0: Memory at 600000000 (64-bit, non-prefetchable) [size=16K]
    Region 2: Memory at 600004000 (32-bit, non-prefetchable) [size=4K]
    Region 3: Memory at 600005000 (32-bit, non-prefetchable) [size=4K]
    Capabilities: [80] Power Management version 3
      Flags: PMEClk- DSI- D1- D2- AuxCurrent=0mA PME(D0-,D1-,D2-,D3hot-,D3cold-)
      Status: D0 NoSoftRst+ PME-Enable- DSel=0 DScale=0 PME-
    Capabilities: [90] MSI: Enable- Count=1/16 Maskable+ 64bit+
      Address: 0000000000000000  Data: 0000
      Masking: 00000000  Pending: 00000000
    Capabilities: [b0] MSI-X: Enable+ Count=33 Masked-
      Vector table: BAR=0 offset=00002000
      PBA: BAR=0 offset=00003000
    Capabilities: [c0] Express (v2) Endpoint, MSI 00
      DevCap:	MaxPayload 512 bytes, PhantFunc 0, Latency L0s unlimited, L1 unlimited
        ExtTag- AttnBtn- AttnInd- PwrInd- RBE+ FLReset+ SlotPowerLimit 0.000W
      DevCtl:	CorrErr- NonFatalErr- FatalErr- UnsupReq-
        RlxdOrd+ ExtTag- PhantFunc- AuxPwr- NoSnoop+ FLReset-
        MaxPayload 128 bytes, MaxReadReq 512 bytes
      DevSta:	CorrErr- NonFatalErr- FatalErr- UnsupReq- AuxPwr- TransPend-
      LnkCap:	Port #0, Speed 8GT/s, Width x4, ASPM L1, Exit Latency L1 <64us
        ClockPM+ Surprise- LLActRep- BwNot- ASPMOptComp+
      LnkCtl:	ASPM Disabled; RCB 64 bytes, Disabled- CommClk+
        ExtSynch- ClockPM- AutWidDis- BWInt- AutBWInt-
      LnkSta:	Speed 5GT/s (downgraded), Width x1 (downgraded)
        TrErr- Train- SlotClk+ DLActive- BWMgmt- ABWMgmt-
      DevCap2: Completion Timeout: Range B, TimeoutDis+ NROPrPrP- LTR+
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
    Capabilities: [100 v2] Advanced Error Reporting
      UESta:	DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
      UEMsk:	DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
      UESvrt:	DLP+ SDES+ TLP- FCP+ CmpltTO- CmpltAbrt- UnxCmplt- RxOF+ MalfTLP+ ECRC- UnsupReq- ACSViol-
      CESta:	RxErr- BadTLP- BadDLLP- Rollover- Timeout- AdvNonFatalErr-
      CEMsk:	RxErr- BadTLP- BadDLLP- Rollover- Timeout- AdvNonFatalErr-
      AERCap:	First Error Pointer: 00, ECRCGenCap+ ECRCGenEn- ECRCChkCap+ ECRCChkEn-
        MultHdrRecCap- MultHdrRecEn- TLPPfxPres- HdrLogCap-
      HeaderLog: 00000000 00000000 00000000 00000000
    Capabilities: [150 v1] Device Serial Number 00-00-00-00-00-00-00-00
    Capabilities: [160 v1] Power Budgeting <?>
    Capabilities: [1b8 v1] Latency Tolerance Reporting
      Max snoop latency: 0ns
      Max no snoop latency: 0ns
    Capabilities: [300 v1] Secondary PCI Express
      LnkCtl3: LnkEquIntrruptEn- PerformEqu-
      LaneErrStat: 0
    Capabilities: [400 v1] Vendor Specific Information: ID=0001 Rev=1 Len=010 <?>
    Capabilities: [900 v1] L1 PM Substates
      L1SubCap: PCI-PM_L1.2+ PCI-PM_L1.1+ ASPM_L1.2+ ASPM_L1.1+ L1_PM_Substates+
          PortCommonModeRestoreTime=24us PortTPowerOnTime=44us
      L1SubCtl1: PCI-PM_L1.2- PCI-PM_L1.1- ASPM_L1.2- ASPM_L1.1-
          T_CommonMode=0us LTR1.2_Threshold=65536ns
      L1SubCtl2: T_PwrOn=44us
    Kernel driver in use: nvme
  ```
</details>

# Disk Information

```
# fdisk -l /dev/nvme0n1
Disk /dev/nvme0n1: 238.47 GiB, 256060514304 bytes, 500118192 sectors
Disk model: HFM256GD3JX016N                         
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0xd0b8e129
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

Full benchmark: [pibenchmarks.com #67925](https://pibenchmarks.com/benchmark/67925/)

| Category | Test | Result |
|:-|:-|:-|
| DD | Disk Write | 131 MB/s |
| HDParm | Disk Read | 360.95 MB/s |
| HDParm | Cached Disk Read | 355.99 MB/s |
| FIO | 4k Random Read | 40960 IOPS |
| FIO | 4k Random Write | 12480 IOPS |
| FIO | 4k Random Read | 163840 KB/s |
| FIO | 4k Random Write | 49920 KB/s |
| IOZone | 4k Read | 89780 KB/s |
| IOZone | 4k Write | 54503 KB/s |
| IOZone | 4k Random Read | 49070 KB/s |
| IOZone | 4k Random Write | 82352 KB/s |
| **Score** | | 15868 |

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
  Jobs: 4 (f=4): [R(4)][27.3%][r=397MiB/s][r=396 IOPS][eta 00m:08s]
  Jobs: 4 (f=4): [R(4)][36.4%][r=398MiB/s][r=397 IOPS][eta 00m:07s]
  Jobs: 4 (f=4): [R(4)][45.5%][r=398MiB/s][r=397 IOPS][eta 00m:06s]
  Jobs: 4 (f=4): [R(4)][54.5%][r=398MiB/s][r=397 IOPS][eta 00m:05s]
  Jobs: 4 (f=4): [R(4)][63.6%][r=397MiB/s][r=397 IOPS][eta 00m:04s]
  Jobs: 4 (f=4): [R(4)][72.7%][r=398MiB/s][r=397 IOPS][eta 00m:03s]
  Jobs: 4 (f=4): [R(4)][81.8%][r=398MiB/s][r=397 IOPS][eta 00m:02s]
  Jobs: 4 (f=4): [R(4)][90.9%][r=398MiB/s][r=397 IOPS][eta 00m:01s]
  Jobs: 4 (f=4): [R(4)][100.0%][r=398MiB/s][r=397 IOPS][eta 00m:00s]
  fio-rand-read-sequential: (groupid=0, jobs=4): err= 0: pid=1179: Sun Mar  5 12:05:00 2023
    read: IOPS=397, BW=397MiB/s (416MB/s)(4227MiB/10647msec)
      slat (usec): min=122, max=4453, avg=403.13, stdev=670.86
      clat (msec): min=130, max=1587, avg=632.61, stdev=194.07
      lat (msec): min=134, max=1587, avg=633.02, stdev=193.74
      clat percentiles (msec):
      |  1.00th=[  155],  5.00th=[  376], 10.00th=[  481], 20.00th=[  485],
      | 30.00th=[  489], 40.00th=[  642], 50.00th=[  642], 60.00th=[  642],
      | 70.00th=[  642], 80.00th=[  651], 90.00th=[  969], 95.00th=[  969],
      | 99.00th=[ 1267], 99.50th=[ 1435], 99.90th=[ 1552], 99.95th=[ 1569],
      | 99.99th=[ 1586]
    bw (  KiB/s): min=335602, max=479232, per=100.00%, avg=406877.00, stdev=16440.18, samples=80
    iops        : min=  326, max=  468, avg=396.70, stdev=16.07, samples=80
    lat (msec)   : 250=3.43%, 500=26.99%, 750=53.39%, 1000=14.34%, 2000=1.85%
    cpu          : usr=0.15%, sys=4.51%, ctx=4230, majf=0, minf=65642
    IO depths    : 1=0.1%, 2=0.2%, 4=0.4%, 8=0.8%, 16=1.5%, 32=3.0%, >=64=94.0%
      submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
      complete  : 0=0.0%, 4=99.9%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.1%, >=64=0.0%
      issued rwts: total=4227,0,0,0 short=0,0,0,0 dropped=0,0,0,0
      latency   : target=0, window=0, percentile=100.00%, depth=64

  Run status group 0 (all jobs):
    READ: bw=397MiB/s (416MB/s), 397MiB/s-397MiB/s (416MB/s-416MB/s), io=4227MiB (4432MB), run=10647-10647msec

  Disk stats (read/write):
    nvme0n1: ios=16547/4, merge=0/0, ticks=10128242/1, in_queue=10128244, util=99.15%

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

    Run began: Sun Mar  5 12:05:00 2023

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
            102400    1024   379304   383401                     375988   383204                                                                

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

    Run began: Sun Mar  5 12:05:02 2023

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
            102400       4    56873    91821                      51164    88255                                                                

  iozone test complete.

  Disk benchmark complete!
  ```
</details>
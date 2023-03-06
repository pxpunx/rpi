# Product Information

| Product | [P41 Plus Series](https://www.solidigm.com/products/client/d6/p41.html) |
|:-|:-|
|----|----|
| *Name* | Solidigm P41 Plus |
| *Model* | SSDPFKNU512GZ |
| *Capacity* | 512GB |
| *Form Factor* | M.2 2280 |
| *Key* | M |
| *Interface* | NVMe |
| *Controller* | Silicon Motion SM2269XT |
| *NAND* | 144L 3D QLC |
| *DRAM* | - |
| *Boot Disk* | :white_check_mark: |
| *Non-Boot Disk* | :white_check_mark: |
| *Adapter* | Ableconn M2MN-151M |

* [Solidigm Announces P41 Plus SSD: Taking Another Shot at QLC With Cache Tiering](https://www.anandtech.com/show/17522/solidigm-announces-p41-plus-ssd-taking-another-shot-at-qlc-with-cache-tiering)
* [Solidigm P41 Plus SSD Review: Born in the Purple (Updated)](https://www.tomshardware.com/reviews/solidigm-p41-plus-ssd-review)

# Device Name

```
# lsblk | grep nvme[01]
nvme0n1     259:0    0 476.9G  0 disk
```

# Device Information

<details>
  <summary>Click here to expand...</summary>
  
  ```
  # lspci -vvv -s 01:00.0
  01:00.0 Non-Volatile memory controller: Device 025e:f1ab (rev 03) (prog-if 02 [NVM Express])
    Subsystem: Device 025e:3910
    Control: I/O- Mem+ BusMaster+ SpecCycle- MemWINV- VGASnoop- ParErr- Stepping- SERR- FastB2B- DisINTx+
    Status: Cap+ 66MHz- UDF- FastB2B- ParErr- DEVSEL=fast >TAbort- <TAbort- <MAbort- >SERR- <PERR- INTx-
    Latency: 0
    Interrupt: pin A routed to IRQ 63
    Region 0: Memory at 600000000 (64-bit, non-prefetchable) [size=16K]
    Capabilities: [40] Power Management version 3
      Flags: PMEClk- DSI- D1- D2- AuxCurrent=0mA PME(D0-,D1-,D2-,D3hot-,D3cold-)
      Status: D0 NoSoftRst+ PME-Enable- DSel=0 DScale=0 PME-
    Capabilities: [50] MSI: Enable- Count=1/16 Maskable+ 64bit+
      Address: 0000000000000000  Data: 0000
      Masking: 00000000  Pending: 00000000
    Capabilities: [70] Express (v2) Endpoint, MSI 00
      DevCap:	MaxPayload 512 bytes, PhantFunc 0, Latency L0s unlimited, L1 unlimited
        ExtTag- AttnBtn- AttnInd- PwrInd- RBE+ FLReset+ SlotPowerLimit 0.000W
      DevCtl:	CorrErr- NonFatalErr- FatalErr- UnsupReq-
        RlxdOrd+ ExtTag- PhantFunc- AuxPwr- NoSnoop- FLReset-
        MaxPayload 128 bytes, MaxReadReq 512 bytes
      DevSta:	CorrErr+ NonFatalErr- FatalErr- UnsupReq- AuxPwr+ TransPend-
      LnkCap:	Port #0, Speed 16GT/s, Width x4, ASPM L1, Exit Latency L1 <8us
        ClockPM+ Surprise- LLActRep- BwNot- ASPMOptComp+
      LnkCtl:	ASPM Disabled; RCB 64 bytes, Disabled- CommClk+
        ExtSynch- ClockPM- AutWidDis- BWInt- AutBWInt-
      LnkSta:	Speed 5GT/s (downgraded), Width x1 (downgraded)
        TrErr- Train- SlotClk+ DLActive- BWMgmt- ABWMgmt-
      DevCap2: Completion Timeout: Range ABCD, TimeoutDis+ NROPrPrP- LTR+
        10BitTagComp+ 10BitTagReq- OBFF Not Supported, ExtFmt- EETLPPrefix-
        EmergencyPowerReduction Not Supported, EmergencyPowerReductionInit-
        FRS+ TPHComp- ExtTPHComp-
        AtomicOpsCap: 32bit- 64bit- 128bitCAS-
      DevCtl2: Completion Timeout: 50us to 50ms, TimeoutDis- LTR+ OBFF Disabled,
        AtomicOpsCtl: ReqEn-
      LnkCap2: Supported Link Speeds: 2.5-16GT/s, Crosslink- Retimer+ 2Retimers+ DRS+
      LnkCtl2: Target Link Speed: 16GT/s, EnterCompliance- SpeedDis-
        Transmit Margin: Normal Operating Range, EnterModifiedCompliance- ComplianceSOS-
        Compliance De-emphasis: -6dB
      LnkSta2: Current De-emphasis Level: -3.5dB, EqualizationComplete- EqualizationPhase1-
        EqualizationPhase2- EqualizationPhase3- LinkEqualizationRequest-
        Retimer- 2Retimers- CrosslinkRes: Upstream Port
    Capabilities: [b0] MSI-X: Enable+ Count=16 Masked-
      Vector table: BAR=0 offset=00002000
      PBA: BAR=0 offset=00003000
    Capabilities: [100 v2] Advanced Error Reporting
      UESta:	DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
      UEMsk:	DLP- SDES- TLP- FCP- CmpltTO- CmpltAbrt- UnxCmplt- RxOF- MalfTLP- ECRC- UnsupReq- ACSViol-
      UESvrt:	DLP+ SDES+ TLP- FCP+ CmpltTO- CmpltAbrt- UnxCmplt- RxOF+ MalfTLP+ ECRC- UnsupReq- ACSViol-
      CESta:	RxErr- BadTLP- BadDLLP- Rollover- Timeout+ AdvNonFatalErr-
      CEMsk:	RxErr- BadTLP- BadDLLP- Rollover- Timeout- AdvNonFatalErr+
      AERCap:	First Error Pointer: 00, ECRCGenCap+ ECRCGenEn- ECRCChkCap+ ECRCChkEn-
        MultHdrRecCap- MultHdrRecEn- TLPPfxPres- HdrLogCap-
      HeaderLog: 00000000 00000000 00000000 00000000
    Capabilities: [148 v1] Power Budgeting <?>
    Capabilities: [158 v1] Alternative Routing-ID Interpretation (ARI)
      ARICap:	MFVC- ACS-, Next Function: 0
      ARICtl:	MFVC- ACS-, Function Group: 0
    Capabilities: [168 v1] Secondary PCI Express
      LnkCtl3: LnkEquIntrruptEn- PerformEqu-
      LaneErrStat: 0
    Capabilities: [188 v1] Physical Layer 16.0 GT/s <?>
    Capabilities: [1ac v1] Lane Margining at the Receiver <?>
    Capabilities: [204 v1] Latency Tolerance Reporting
      Max snoop latency: 0ns
      Max no snoop latency: 0ns
    Capabilities: [20c v1] L1 PM Substates
      L1SubCap: PCI-PM_L1.2+ PCI-PM_L1.1+ ASPM_L1.2+ ASPM_L1.1+ L1_PM_Substates+
          PortCommonModeRestoreTime=10us PortTPowerOnTime=10us
      L1SubCtl1: PCI-PM_L1.2- PCI-PM_L1.1- ASPM_L1.2- ASPM_L1.1-
          T_CommonMode=0us LTR1.2_Threshold=25600ns
      L1SubCtl2: T_PwrOn=10us
    Kernel driver in use: nvme
  ```
</details>

# Disk Information

```
# fdisk -l /dev/nvme0n1
Disk /dev/nvme0n1: 476.94 GiB, 512110190592 bytes, 1000215216 sectors
Disk model: SOLIDIGM SSDPFKNU512GZ                  
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
```

# Filesystem Information

```
# df -Th /dev/nvme0n1
Filesystem     Type  Size  Used Avail Use% Mounted on
/dev/nvme0n1   ext4  469G   28K  445G   1% /mnt/sda1
```

# Benchmarks

## PiBenchmarks.com

Credit: [James C. Chambers](https://jamesachambers.com/) ([source](https://raw.githubusercontent.com/TheRemote/PiBenchmarks/master/Storage.sh))

Full benchmark: [pibenchmarks.com #xxxx](xxxx)

| Category | Test | Result |
|:-|:-|:-|
| DD | Disk Write | 130 MB/s |
| HDParm | Disk Read | 361.23 MB/s |
| HDParm | Cached Disk Read | 359.30 MB/s |
| FIO | 4k Random Read | 41710 IOPS |
| FIO | 4k Random Write | 12047 IOPS |
| FIO | 4k Random Read | 166843 KB/s |
| FIO | 4k Random Write | 48188 KB/s |
| IOZone | 4k Read | 73291 KB/s |
| IOZone | 4k Write | 53677 KB/s |
| IOZone | 4k Random Read | 48961 KB/s |
| IOZone | 4k Random Write | 78979 KB/s |
| **Score** | | 15330 |

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
  Jobs: 4 (f=4): [R(4)][54.5%][r=370MiB/s][r=370 IOPS][eta 00m:05s] 
  Jobs: 4 (f=4): [R(4)][72.7%][r=397MiB/s][r=397 IOPS][eta 00m:03s] 
  Jobs: 4 (f=4): [R(4)][90.9%][eta 00m:01s]                         
  Jobs: 4 (f=4): [R(4)][6.3%][eta 02m:59s]   
  Jobs: 4 (f=4): [R(4)][6.2%][eta 03m:31s] 
  Jobs: 4 (f=4): [R(4)][6.2%][eta 04m:04s] 
  Jobs: 4 (f=4): [R(4)][6.1%][eta 04m:36s] 
  Jobs: 4 (f=4): [R(4)][6.1%][eta 05m:09s] 
  Jobs: 4 (f=4): [R(4)][6.1%][eta 05m:41s] 
  Jobs: 4 (f=4): [R(4)][6.0%][eta 06m:14s] 
  Jobs: 4 (f=4): [R(4)][6.0%][eta 06m:47s] 
  Jobs: 4 (f=4): [R(4)][6.0%][eta 07m:19s] 
  Jobs: 4 (f=4): [R(4)][6.0%][eta 07m:52s] 
  Jobs: 4 (f=4): [R(4)][6.0%][eta 08m:24s] 
  Jobs: 4 (f=4): [R(4)][6.0%][eta 08m:57s] 
  Jobs: 4 (f=4): [R(4)][6.0%][eta 09m:29s] 
  Jobs: 4 (f=4): [R(4)][5.9%][eta 10m:02s] 
  Jobs: 4 (f=4): [R(4)][5.9%][eta 10m:35s] 
  Jobs: 4 (f=4): [R(4)][5.9%][eta 10m:51s]
  Jobs: 4 (f=4): [R(4)][5.9%][eta 11m:23s] 
  Jobs: 4 (f=4): [R(4)][5.9%][eta 11m:56s] 
  Jobs: 4 (f=4): [R(4)][5.9%][eta 12m:29s] 
  Jobs: 4 (f=4): [R(4)][5.9%][eta 13m:01s] 
  Jobs: 4 (f=4): [R(4)][5.9%][eta 13m:34s] 
  Jobs: 4 (f=4): [R(4)][5.9%][eta 14m:06s] 
  Jobs: 4 (f=4): [R(4)][5.9%][eta 14m:39s] 
  Jobs: 4 (f=4): [R(4)][5.9%][eta 15m:11s] 
  Jobs: 4 (f=4): [R(4)][5.9%][eta 15m:44s] 
  Jobs: 4 (f=4): [R(4)][5.9%][eta 16m:16s] 
  Jobs: 4 (f=4): [R(4)][5.9%][eta 16m:49s] 
  Jobs: 4 (f=4): [R(4)][5.9%][eta 17m:22s] 
  Jobs: 4 (f=4): [R(4)][5.9%][r=1024KiB/s][r=1 IOPS][eta 17m:33s]
  fio-rand-read-sequential: (groupid=0, jobs=4): err= 0: pid=1189: Sun Mar  5 12:45:06 2023
    read: IOPS=45, BW=45.0MiB/s (47.2MB/s)(2930MiB/65060msec)
      slat (usec): min=118, max=61686k, avg=88576.98, stdev=2222624.08
      clat (msec): min=11, max=62612, avg=5587.04, stdev=16885.66
      lat (msec): min=132, max=62643, avg=5675.62, stdev=17006.02
      clat percentiles (msec):
      |  1.00th=[  146],  5.00th=[  157], 10.00th=[  159], 20.00th=[  161],
      | 30.00th=[  292], 40.00th=[  326], 50.00th=[  393], 60.00th=[  468],
      | 70.00th=[  502], 80.00th=[  659], 90.00th=[ 1083], 95.00th=[17113],
      | 99.00th=[17113], 99.50th=[17113], 99.90th=[17113], 99.95th=[17113],
      | 99.99th=[17113]
    bw (  KiB/s): min=208896, max=819200, per=100.00%, avg=474137.99, stdev=73019.70, samples=40
    iops        : min=  204, max=  800, avg=462.66, stdev=71.33, samples=40
    lat (msec)   : 20=0.03%, 250=28.29%, 500=41.54%, 750=11.81%, 1000=6.18%
    lat (msec)   : 2000=3.55%, >=2000=8.60%
    cpu          : usr=0.01%, sys=0.47%, ctx=2717, majf=0, minf=65648
    IO depths    : 1=0.1%, 2=0.3%, 4=0.5%, 8=1.1%, 16=2.2%, 32=4.4%, >=64=91.4%
      submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
      complete  : 0=0.0%, 4=99.9%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.1%, >=64=0.0%
      issued rwts: total=2930,0,0,0 short=0,0,0,0 dropped=0,0,0,0
      latency   : target=0, window=0, percentile=100.00%, depth=64

  Run status group 0 (all jobs):
    READ: bw=45.0MiB/s (47.2MB/s), 45.0MiB/s-45.0MiB/s (47.2MB/s-47.2MB/s), io=2930MiB (3072MB), run=65060-65060msec

  Disk stats (read/write):
    nvme0n1: ios=11488/35, merge=0/1, ticks=5643650/16211, in_queue=5659861, util=100.00%

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

    Run began: Sun Mar  5 12:45:06 2023

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
            102400    1024   357808   366741                     370983   391250                                                                

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

    Run began: Sun Mar  5 12:45:08 2023

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
            102400       4    53689    85053                      48391    79435                                                                

  iozone test complete.

  Disk benchmark complete!
  ```
</details>

# Boot Informatiob

Raspberry Pi Imager was unable to complete post-imaging verification on this drive; stuck on `Verifying... 0%`. Made multiple attempts.



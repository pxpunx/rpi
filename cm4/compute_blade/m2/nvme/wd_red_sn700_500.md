# Product Information

| Product | [WD Red SN700 NVMe™ SSD](https://www.westerndigital.com/products/internal-drives/wd-red-sn700-nvme-ssd#WDS250G1R0C) |
|-|-|
| **Name** | Western Digital Red SN700 |
| **Model** | WDS250G1R0C |
| **Capacity** | 500GB |
| **Form Factor** | M.2 2280 |
| **Key** | M |
| **Interface** | NVMe |
| **Bootable** | YES |
| **Benchmark(s)** | JG (below) |

# Device Name

```
root@default-pi:~# lsblk | grep nvme[01]
nvme0n1     259:0    0 465.8G  0 disk 
```

# Device Information

```
root@default-pi:~# lspci -vvv -s 01:00.0
01:00.0 Non-Volatile memory controller: Sandisk Corp WD Black SN750 / PC SN730 NVMe SSD (prog-if 02 [NVM Express])
	Subsystem: Sandisk Corp WD Black 2019/PC SN750 NVMe SSD
	Control: I/O- Mem+ BusMaster+ SpecCycle- MemWINV- VGASnoop- ParErr- Stepping- SERR- FastB2B- DisINTx+
	Status: Cap+ 66MHz- UDF- FastB2B- ParErr- DEVSEL=fast >TAbort- <TAbort- <MAbort- >SERR- <PERR- INTx-
	Latency: 0
	Interrupt: pin A routed to IRQ 63
	Region 0: Memory at 600000000 (64-bit, non-prefetchable) [size=16K]
	Region 4: Memory at 600004000 (64-bit, non-prefetchable) [size=256]
	Capabilities: [80] Power Management version 3
		Flags: PMEClk- DSI- D1- D2- AuxCurrent=0mA PME(D0-,D1-,D2-,D3hot-,D3cold-)
		Status: D0 NoSoftRst+ PME-Enable- DSel=0 DScale=0 PME-
	Capabilities: [90] MSI: Enable- Count=1/32 Maskable- 64bit+
		Address: 0000000000000000  Data: 0000
	Capabilities: [b0] MSI-X: Enable+ Count=65 Masked-
		Vector table: BAR=0 offset=00002000
		PBA: BAR=4 offset=00000000
	Capabilities: [c0] Express (v2) Endpoint, MSI 00
		DevCap:	MaxPayload 256 bytes, PhantFunc 0, Latency L0s <1us, L1 unlimited
			ExtTag- AttnBtn- AttnInd- PwrInd- RBE+ FLReset+ SlotPowerLimit 0.000W
		DevCtl:	CorrErr- NonFatalErr- FatalErr- UnsupReq-
			RlxdOrd+ ExtTag- PhantFunc- AuxPwr- NoSnoop+ FLReset-
			MaxPayload 128 bytes, MaxReadReq 512 bytes
		DevSta:	CorrErr- NonFatalErr- FatalErr- UnsupReq- AuxPwr- TransPend-
		LnkCap:	Port #0, Speed 8GT/s, Width x4, ASPM L1, Exit Latency L1 <8us
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
		CEMsk:	RxErr- BadTLP- BadDLLP- Rollover- Timeout- AdvNonFatalErr+
		AERCap:	First Error Pointer: 00, ECRCGenCap+ ECRCGenEn- ECRCChkCap+ ECRCChkEn-
			MultHdrRecCap- MultHdrRecEn- TLPPfxPres- HdrLogCap-
		HeaderLog: 00000000 00000000 00000000 00000000
	Capabilities: [150 v1] Device Serial Number 00-00-00-00-00-00-00-00
	Capabilities: [1b8 v1] Latency Tolerance Reporting
		Max snoop latency: 0ns
		Max no snoop latency: 0ns
	Capabilities: [300 v1] Secondary PCI Express
		LnkCtl3: LnkEquIntrruptEn- PerformEqu-
		LaneErrStat: 0
	Capabilities: [900 v1] L1 PM Substates
		L1SubCap: PCI-PM_L1.2+ PCI-PM_L1.1- ASPM_L1.2+ ASPM_L1.1- L1_PM_Substates+
			  PortCommonModeRestoreTime=32us PortTPowerOnTime=150us
		L1SubCtl1: PCI-PM_L1.2- PCI-PM_L1.1- ASPM_L1.2- ASPM_L1.1-
			   T_CommonMode=0us LTR1.2_Threshold=163840ns
		L1SubCtl2: T_PwrOn=150us
	Kernel driver in use: nvme
```

# Disk Information

```
root@default-pi:~# fdisk -l /dev/nvme0n1
Disk /dev/nvme0n1: 465.76 GiB, 500107862016 bytes, 976773168 sectors
Disk model: WD Red SN700 500GB                      
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0x21e60f8c
```

# Filesystem Information

```
root@default-pi:~# df -Th /dev/nvme0n1
Filesystem     Type  Size  Used Avail Use% Mounted on
/dev/nvme0n1   ext4  458G   28K  435G   1% /mnt/sda1
```

# Jeff Geerling Benchmark

```
root@default-pi:~# DEVICE_UNDER_TEST=/dev/nvme0n1 ./disk-benchmark.sh

Raspberry Pi disk benchmarks
Running fio sequential read test...
fio-rand-read-sequential: (g=0): rw=read, bs=(R) 1024KiB-1024KiB, (W) 1024KiB-1024KiB, (T) 1024KiB-1024KiB, ioengine=libaio, iodepth=64
...
fio-3.25
Starting 4 processes
Jobs: 4 (f=4): [R(4)][36.4%][r=396MiB/s][r=396 IOPS][eta 00m:07s]
Jobs: 4 (f=4): [R(4)][54.5%][r=397MiB/s][r=397 IOPS][eta 00m:05s] 
Jobs: 4 (f=4): [R(4)][63.6%][r=396MiB/s][r=395 IOPS][eta 00m:04s]
Jobs: 4 (f=4): [R(4)][72.7%][r=394MiB/s][r=393 IOPS][eta 00m:03s]
Jobs: 4 (f=4): [R(4)][81.8%][r=395MiB/s][r=394 IOPS][eta 00m:02s]
Jobs: 4 (f=4): [R(4)][90.9%][r=393MiB/s][r=392 IOPS][eta 00m:01s]
Jobs: 4 (f=4): [R(4)][100.0%][r=395MiB/s][r=394 IOPS][eta 00m:00s]
fio-rand-read-sequential: (groupid=0, jobs=4): err= 0: pid=669: Sat Feb 18 15:43:50 2023
  read: IOPS=394, BW=395MiB/s (414MB/s)(4204MiB/10647msec)
    slat (usec): min=125, max=4468, avg=417.45, stdev=590.34
    clat (msec): min=128, max=1605, avg=636.94, stdev=276.74
     lat (msec): min=131, max=1606, avg=637.36, stdev=276.53
    clat percentiles (msec):
     |  1.00th=[  150],  5.00th=[  326], 10.00th=[  326], 20.00th=[  326],
     | 30.00th=[  481], 40.00th=[  493], 50.00th=[  542], 60.00th=[  651],
     | 70.00th=[  885], 80.00th=[  961], 90.00th=[  978], 95.00th=[  978],
     | 99.00th=[ 1385], 99.50th=[ 1485], 99.90th=[ 1569], 99.95th=[ 1586],
     | 99.99th=[ 1603]
   bw (  KiB/s): min=272384, max=550912, per=100.00%, avg=404684.80, stdev=27839.32, samples=80
   iops        : min=  266, max=  538, avg=395.20, stdev=27.19, samples=80
  lat (msec)   : 250=3.16%, 500=40.63%, 750=21.15%, 1000=32.25%, 2000=2.81%
  cpu          : usr=0.17%, sys=4.62%, ctx=4217, majf=0, minf=65641
  IO depths    : 1=0.1%, 2=0.2%, 4=0.4%, 8=0.8%, 16=1.5%, 32=3.0%, >=64=94.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=99.9%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.1%, >=64=0.0%
     issued rwts: total=4204,0,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=64

Run status group 0 (all jobs):
   READ: bw=395MiB/s (414MB/s), 395MiB/s-395MiB/s (414MB/s-414MB/s), io=4204MiB (4408MB), run=10647-10647msec

Disk stats (read/write):
  nvme0n1: ios=16441/1109, merge=0/12, ticks=10114646/48010, in_queue=10162944, util=99.27%

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

	Run began: Sat Feb 18 15:43:50 2023

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
          102400    1024   360823   362512                     378122   364339                                                                

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

	Run began: Sat Feb 18 15:43:51 2023

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
          102400       4    55888    87999                      39331    85134                                                                

iozone test complete.

Disk benchmark complete!
```
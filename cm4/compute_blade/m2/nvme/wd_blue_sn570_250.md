# Product Information

| Name | Model | Capacity | Form Factor | Key | Interface | Bootable | Benchmark(s) |
|-|-|-|-|-|-|-|-|
| Western Digital Blue SN570 | WDS250G3B0C | 250GB | M.2 2280 | M | NVMe | YES | [PiB #67387](https://pibenchmarks.com/benchmark/67387/), JG (below) |

Product brief: [WD Blue SN570 NVMe™ SSD](https://www.westerndigital.com/products/internal-drives/wd-blue-sn570-nvme-ssd)

# Device Name

```
root@default-pi:~# lsblk | grep nvme[01]
nvme0n1     259:0    0 232.9G  0 disk 
```

# Device Information

```
root@default-pi:~# lspci -vvv -s 01:00.0
01:00.0 Non-Volatile memory controller: Sandisk Corp Device 501a (prog-if 02 [NVM Express])
	Subsystem: Sandisk Corp Device 501a
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
	Capabilities: [b0] MSI-X: Enable+ Count=17 Masked-
		Vector table: BAR=0 offset=00002000
		PBA: BAR=4 offset=00000000
	Capabilities: [c0] Express (v2) Endpoint, MSI 00
		DevCap:	MaxPayload 512 bytes, PhantFunc 0, Latency L0s <1us, L1 unlimited
			ExtTag- AttnBtn- AttnInd- PwrInd- RBE+ FLReset+ SlotPowerLimit 0.000W
		DevCtl:	CorrErr- NonFatalErr- FatalErr- UnsupReq-
			RlxdOrd+ ExtTag+ PhantFunc- AuxPwr- NoSnoop+ FLReset-
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
			  PortCommonModeRestoreTime=32us PortTPowerOnTime=10us
		L1SubCtl1: PCI-PM_L1.2- PCI-PM_L1.1- ASPM_L1.2- ASPM_L1.1-
			   T_CommonMode=0us LTR1.2_Threshold=32768ns
		L1SubCtl2: T_PwrOn=10us
	Kernel driver in use: nvme
```

# Disk Information

```
root@default-pi:~# fdisk -l /dev/nvme0n1
Disk /dev/nvme0n1: 232.89 GiB, 250059350016 bytes, 488397168 sectors
Disk model: WD Blue SN570 250GB                     
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
```

# Filesystem Information

```
root@default-pi:~# df -Th /dev/nvme0n1
Filesystem     Type  Size  Used Avail Use% Mounted on
/dev/nvme0n1   ext4  229G   28K  217G   1% /mnt/sda1
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
Jobs: 4 (f=4): [R(4)][54.5%][r=397MiB/s][r=396 IOPS][eta 00m:05s] 
Jobs: 4 (f=4): [R(4)][63.6%][r=397MiB/s][r=397 IOPS][eta 00m:04s]
Jobs: 4 (f=4): [R(4)][72.7%][r=396MiB/s][r=396 IOPS][eta 00m:03s]
Jobs: 4 (f=4): [R(4)][81.8%][r=397MiB/s][r=396 IOPS][eta 00m:02s]
Jobs: 4 (f=4): [R(4)][90.9%][r=397MiB/s][r=396 IOPS][eta 00m:01s]
Jobs: 4 (f=4): [R(4)][100.0%][r=396MiB/s][r=395 IOPS][eta 00m:00s]
fio-rand-read-sequential: (groupid=0, jobs=4): err= 0: pid=595: Sat Feb 18 19:06:30 2023
  read: IOPS=395, BW=396MiB/s (415MB/s)(4215MiB/10646msec)
    slat (usec): min=121, max=5089, avg=437.15, stdev=777.76
    clat (msec): min=121, max=1353, avg=637.82, stdev=174.33
     lat (msec): min=125, max=1353, avg=638.26, stdev=173.90
    clat percentiles (msec):
     |  1.00th=[  150],  5.00th=[  351], 10.00th=[  481], 20.00th=[  506],
     | 30.00th=[  634], 40.00th=[  642], 50.00th=[  642], 60.00th=[  642],
     | 70.00th=[  651], 80.00th=[  659], 90.00th=[  911], 95.00th=[  961],
     | 99.00th=[ 1183], 99.50th=[ 1234], 99.90th=[ 1318], 99.95th=[ 1334],
     | 99.99th=[ 1351]
   bw (  KiB/s): min=327680, max=481071, per=100.00%, avg=405688.85, stdev=14746.09, samples=80
   iops        : min=  320, max=  469, avg=395.70, stdev=14.40, samples=80
  lat (msec)   : 250=3.65%, 500=15.16%, 750=66.50%, 1000=12.03%, 2000=2.66%
  cpu          : usr=0.14%, sys=4.81%, ctx=4234, majf=0, minf=65644
  IO depths    : 1=0.1%, 2=0.2%, 4=0.4%, 8=0.8%, 16=1.5%, 32=3.0%, >=64=94.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=99.9%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.1%, >=64=0.0%
     issued rwts: total=4215,0,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=64

Run status group 0 (all jobs):
   READ: bw=396MiB/s (415MB/s), 396MiB/s-396MiB/s (415MB/s-415MB/s), io=4215MiB (4420MB), run=10646-10646msec

Disk stats (read/write):
  nvme0n1: ios=16486/385, merge=0/6, ticks=10105635/68886, in_queue=10175007, util=99.24%

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

	Run began: Sat Feb 18 19:06:30 2023

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
          102400    1024   385198   389054                     379221   387988                                                                

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

	Run began: Sat Feb 18 19:06:31 2023

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
          102400       4    55217    87290                      43020    81960                                                                

iozone test complete.

Disk benchmark complete!
```
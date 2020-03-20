---
layout: post
title:  "BTEC Networking and Architecture cheatsheet"
date:   2020-03-15 +0100
categories: IT
published: true
---

The purpose of these notes is to provide a concise reference to each
item for the BTEC Networking and Architecture exam.  As much as
possible, the items are listed in the same order as in the exam
specifications.

This list is under construction and definitely not complete.  

---

### References
- [BTEC Specialist qualifications
  Networking and Architecture (Level 3):
  Specifications](https://qualifications.pearson.com/en/qualifications/btec-specialist-and-professional-qualifications/it-telecoms-and-digital-industries/btec-specialist-networking-and-architecture-l3.html)

When not explicitly mentioned, it should be assumed that the
information originates from the following sources:  
- [Netacad (Cisco)](https://www.netacad.com)
- Wikipedia

## Acronyms

| CPU       | Central Processing Unit                       |
| RAM       | Random Access Memory                          |
| BIOS      | Basic Input/Output System                     |
| PCI/PCIe  | Peripheral Component Interconnect/PCI Express |
| I/O       | Input/Output                                  |
| FAT/FAT32 | File Allocation Table/FAT 32-bit              |
| NTFS      | New Technology File System                    |
| exFAT     | EXtended FAT                                  |
| NFS       | Network File System                           |
| APIPA     | Automatic Private IP Addressing               |




## Basic hardware components

### Components
	
| CPU                        | interprets and executes commands, outputs information                             | <img src="{{site.baseurl}}/assets/netacad-it-essentials/cpu-or-processor.jpg" width="200">                    |
| RAM                        | temporary location to store data and applications                                 | <img src="{{site.baseurl}}/assets/netacad-it-essentials/ram-memory-module.jpg" width="200">                   |
| BIOS/UEFI                  | boots computer, performs power-on self-test                                       | <img src="{{site.baseurl}}/assets/netacad-it-essentials/rom-bios-firmware.jpg" width="200">                   |
| motherboard                |                                                                                   | <img src="{{site.baseurl}}/assets/netacad-it-essentials/motherboard-red.jpg" width="200">                     |
| system bus<br>architecture |                                                                                   | <img src="{{site.baseurl}}/assets/netacad-it-essentials/system-bus-architecture.svg" width="200">             |
| PCI                        | local computer bus, mostly obsolete                                               | <img src="{{site.baseurl}}/assets/netacad-it-essentials/expansion-slot-pci.jpg" width="200">                  |
| PCIe                       | connects to a serial bus, much faster                                             | <img src="{{site.baseurl}}/assets/netacad-it-essentials/expansion-slot-pcie-x1-through-x16.jpeg" width="200"> |
| magnetic hard drive        | provides non-volatile storage of data<br>low cost, low efficiency, high capacity  | <img src="{{site.baseurl}}/assets/netacad-it-essentials/storage-hdd-form-factors.jpg" width="200">            |
| solid-state drive          | provides non-volatile storage of data<br>high cost, more reliable, lower capacity | <img src="{{site.baseurl}}/assets/netacad-it-essentials/storage-ssd-form-factors.jpg" width="200">            |
| firmware                   | programming that allows a computer operating system to control the hardware       |                                                                                                               |

_References_:  
- [overclock.net](https://www.overclock.net/forum/355-ssd/1489684-ssd-interface-comparison-pci-express-vs-sata.html)

### CPU
<img src="{{site.baseurl}}/assets/netacad-it-essentials/multicore-processors.jpg" width="800">





### Types of devices

- Servers (email, file, web, print)
  - strictly speaking, a program (not a device) or program stored on a
    dedicated device, providing functionality, to serve other
    programs; can serve multiple clients
- Desktop
- Mobile devices
  - Laptops
  - Tablets
  - Smartphones
  - Wearables
- Terminals

### Laptop and desktop design comparison
<img src="{{site.baseurl}}/assets/netacad-it-essentials/laptop-and-desktop-design-comparison.jpg" width="600">



## Basic software elements
### Operating systems
#### Kernel
- connects hardware and application software
- allocates resources
- manages processes, memory, I/O devices, etc.

#### File systems
Links:
- [techcifferences.com](https://techdifferences.com/difference-between-fat32-and-ntfs.html)
- [diffen.com](https://www.diffen.com/difference/FAT32_vs_NTFS)
- [IT Free Training](http://itfreetraining.com/handouts/server/file-systems.pdf)

Types of file systems:
- FAT32
- NTFS
- exFAT (FAT64): optimized for flash drives
- Compact Disc File System: specifically for optical disk media
- NFS: allows file access over network


FAT32 vs NTFS:

|                      | FAT32        | NTFS                         | exFAT        |
|----------------------|--------------|------------------------------|--------------|
| introduced           | 1977         | 1993                         | 2006         |
| max. file size       | 4 GB         | 16 EB                        | 16 EB        |
| max. volume size     | 2 TB         | 16 EB                        | 127 PB       |
| max file name length | 8.3          | 255                          | 255          |
| encryption           | no           | yes                          | no           |
| security             | network      | local and network            | ?            |
| compression          | no           | yes                          | no           |
| journaling           | no           | yes                          | ?            |
| fault tolerance      | no           | automatic<br>troubleshooting | ?            |
| OS support           | XP and older | XP and newer                 | XP and newer |

### Applications
- databases
- security utilities (anti-virus, firewall)

## Networking addressing: IP Addresses

### IP addresses

IP address = network portion + host portion

Subnet masks are used to differentiate network from host portions.  
Alternatively, the "slash" or CIDR notation indicates the number of
bits (starting from the most significant bit, i.e. "from the left")
used to identify the network portion of the IP address.

### IPv4 vs IPv6

| version | length   | format                      |
|---------|----------|-----------------------------|
| IPv4    | 32 bits  | dotted decimal              |
| IPv6    | 128 bits | colon-separated hexadecimal |

### IPv6 notatiom compressio rules
1. Omit leading `0`s.
2. Omit contiguous all-`0` segments.



###  IPv4 classful addressing
_References_:  
- [List of assigned `/8` IPv4 address
  blocks](https://en.wikipedia.org/wiki/List_of_assigned_/8_IPv4_address_blocks) (wikipedia)

| class | leading<br>bit(s) | public range  | private range     | subnet mask   |
|-------|-------------------|---------------|-------------------|---------------|
| A     | 0                 | 1 - 126 (127) | 10                | 255.0.0.0     |
| B     | 10                | 128 - 191     | 172.16 - 172.31   | 255.255.0.0   |
| C     | 110               | 192 - 223     | 192.168 - 192.168 | 255.255.255.0 |
| D     | 1110              | 224 - 239     |                   | undefined     |
| E     | 1111              | 240 - 255     |                   | undefined     |



![]({{site.baseurl}}/assets/netacad-it-essentials/ipv4-classful-network-addressing.png)

_References_:  
- [The TCP/IP guide](http://www.tcpipguide.com/free/t_IPClassfulAddressingNetworkandHostIdentificationan-3.htm)

### Subnetting

| class      | number of subnets                    | number of hosts per subnet   |
|------------|--------------------------------------|------------------------------|
| class A    | `126` (i.e. 2^(8-1) - 2)             | `16,777,214` (i.e. 2^24 - 2) |
| class B    | `16,384` (i.e. 2^14, 14 = 16 - 2)    | `65,534` (i.e. 2^16 - 2)     |
| class C    | `2,097,152` (i.e. 2^21, 21 = 24 - 3) | `254` (i.e. 2^8 - 2)         |
| class D, E | not defined                          | not defined                  |

  


### Public and private addresses

| public                      | private                              |
|-----------------------------|--------------------------------------|
| required to access internet |                                      |
| must be unique              | can be translated to access internet |
| routable on internet        | not routable on internet             |
| assigned by IANA/RIR        | administrator can assign             |



_References_:  
- [video by IT free
  training](https://www.youtube.com/watch?v=WsgK08FyoRk)


### Link-local addresses:  

| version | slash/CIDR block<br>notation | range                                                                           |
|---------|------------------------------|---------------------------------------------------------------------------------|
| IPv4    | 169.254.0.0/16               | 169.254<br>reserved: 169.254.0, 169.254.255<br>effective: 169.254.1-169.254.254 |
| IPv6    | fe80::/10                    | fe80:: to febf::                                                                |

### Address categories

| default gateway   | a router interface connected to the local network that sends packets out of the local network                                    |
| loopback address  | `127.0.0.1`; used to test the communication or transportation medium on a local network card or for testing network applications |
| broadcast address | used to address **all** devices on subnet<br>IP address in subnet with host bits all set to `1`                                  |
| network address   | IP address in subnet with host bits all set to `0`                                                                               |
| multicast address | used to address a specific group of devices                                                                                      |


## Cabling

| twisted-pair (unshielded)    | <img src="{{site.baseurl}}/assets/netacad-it-essentials/network-cables-twisted-pair-unshielded.jpg" width="400">   |
| twisted-pair (shielded)      | <img src="{{site.baseurl}}/assets/netacad-it-essentials/network-cables-twisted-pair-shielded.jpg" width="400">     |
| coaxial                      | <img src="{{site.baseurl}}/assets/netacad-it-essentials/network-cables-coaxial-cable.jpg" width="400">             |
| fiber optic                  | <img src="{{site.baseurl}}/assets/netacad-it-essentials/network-cables-fiber-optic-diagram.jpg" width="400">       |
| fiber optic<br>cross section | <img src="{{site.baseurl}}/assets/netacad-it-essentials/network-cables-fiber-optic-cross-section.jpg" width="400"> |
| fiber optic<br>single-mode   | <img src="{{site.baseurl}}/assets/netacad-it-essentials/network-cables-fiber-optic-single-mode.jpg" width="400">   |
| fiber optic<br>multi-mode    | <img src="{{site.baseurl}}/assets/netacad-it-essentials/network-cables-fiber-optic-multimode.jpg" width="400">     |


## Wiring

| straight through | <img src="{{site.baseurl}}/assets/netacad-it-essentials/wiring-straight-through.jpg" width="400"> |
| crossover        | <img src="{{site.baseurl}}/assets/netacad-it-essentials/wiring-crossover.jpg" width="400">        |
| rollover         | <img src="{{site.baseurl}}/assets/netacad-it-essentials/wiring-rollover.jpg" width="400">         |
| patch cable      | ?                                                                                                  |

_Reference_:  
- [Straight through, crossover and
rollover
wiring](https://www.computercablestore.com/straight-through-crossover-and-rollover-wiring)


## Twisted-pair category ratings

A twisted pair reduces electromagnetic radiation from the pair and
**crosstalk** between neighboring pairs and improves rejection of
external electromagnetic interference.


The short list:

| cable<br>category    | protection | max speed           | maximum<br>distance |
|----------------------|------------|---------------------|---------------------|
| cat3                 | unshielded | 10 Mbps             | 100 m               |
| cat5                 | unshielded | 100 Mpbs            | 100 m               |
| cat5e<br>(enhanced)  | shielded   | 1 Gbps              | 100 m               |
| cat6                 | shielded   | 10 Gbps<br>(1 Gbps) | 37-55 m<br>(100 m)  |
| cat6a<br>(augmented) | shielded   | 10 Gbps             | 100 m               |

More details:

| cable<br>category    | protection | max speed           | usage                     | maximum<br>distance | max<br>bandwidth |
|----------------------|------------|---------------------|---------------------------|---------------------|------------------|
| cat1                 | unshielded | 1 Mbps              | phone, data               | 100 m               | 1 MHz            |
| cat2                 | unshielded | 4 Mbps              | phone, data               | 100 m               | 4 MHz            |
| cat3                 | unshielded | 10 Mbps             | 10BASE-T                  | 100 m               | 16 MHz           |
| cat4                 | unshielded | 16 Mbps             | token ring<br>10BASE-T    | 100 m               | 20 MHz           |
| cat5                 | unshielded | 100 Mpbs            | 100BASE-TX<br>1000BASE-T  | 100 m               | 100 MHz          |
| cat5e<br>(enhanced)  | shielded   | 1 Gbps              | 1000BASE-TX<br>1000BASE-T | 100 m               | 100 MHz          |
| cat6                 | shielded   | 10 Gbps<br>(1 Gbps) | 10GBASE-T                 | 37-55 m<br>(100 m)  | 250 MHz          |
| cat6a<br>(augmented) | shielded   | 10 Gbps             | 10GBASE-T                 | 100 m               | 500 MHz          |


_References_:  
- [Copper cable
  certification](https://en.wikipedia.org/wiki/Copper_cable_certification) (wikipedia)
- [Twisted pair](https://en.wikipedia.org/wiki/Twisted_pair) (wikipedia)
- [Category 1 cable](https://en.wikipedia.org/wiki/Category_1_cable) (wikipedia)
- [Category 2 cable](https://en.wikipedia.org/wiki/Category_2_cable) (wikipedia)
- [Category 3 cable](https://en.wikipedia.org/wiki/Category_3_cable)
  (wikipedia)
- [Category 5 cable](https://en.wikipedia.org/wiki/Category_5_cable)
  (wikipedia)
- [Category 6 cable](https://en.wikipedia.org/wiki/Category_6_cable) (wikipedia)
- [CCNA: network media types](https://www.ciscopress.com/articles/article.asp?p=31276)
- [Professor Messer's 220-901 video
  Network cabling](https://www.youtube.com/watch?v=RWCiqUm34Bc&list=PLG49S3nxzAnmlC1ZsppuM7yleDuYCMHrv&index=44&t=05m18s
  "Professor Messer")


### Ethernet standards

- "Ethernet over twisted pair"
- All standards use RF-46 (aka 8P8C), cables range from cat3 to cat8.
- `10BASE-T`, `100BASE-TX`, etc.
  - `10`, `100`, etc. refer to transmission speed of `10 Mbps`, `100 Mbps`, etc.
  -  `T` stands for "twisted pair"", while `F` refers to "fiber"
  - `TX` or `T4` refers to encoding or number of lanes.
  - `BASE` refers to baseband signalling.
- Cables for Ethernet may be wired to either the T568A or T568B
  termination standards (see below) at both ends of the cable.

| standard                         | speed    | max length   | cable<br>category |
|----------------------------------|----------|--------------|-------------------|
| 10BASE-T                         | 10 Mbps  | 100 m        | &#8805; 3         |
| 100BASE-TX<br>(Fast Ethernet)    | 100 Mbps | 100 m        | &#8805; 5         |
| 1000BASE-T<br>(Gigabit Ethernet) | 1 Gbps   | 100 m        | &#8805; 5         |
| 10GBASE-T                        | 10 Gbps  | 100 m (55 m) | 6a (6)            |
|                                  |          |              |                   |

| port      | <img src="{{site.baseurl}}/assets/netacad-it-essentials/ethernet-port.jpg" width="200">                                                                                        |
| connector | <img src="{{site.baseurl}}/assets/netacad-it-essentials/10baset-jack.png" width="200"> <img src="{{site.baseurl}}/assets/netacad-it-essentials/rj45plug-8p8c.png" width="200"> |
| T568A  scheme       | <img src="{{site.baseurl}}/assets/netacad-it-essentials/network-cables-T568A.jpg" width="400">                                                                                 |
| T568B scheme       | <img src="{{site.baseurl}}/assets/netacad-it-essentials/network-cables-T568B.jpg" width="400">                                                                                 |



_References_:  
- [Ethernet](https://en.wikipedia.org/wiki/Ethernet) (wikipedia)
- [Ethernet over twisted
  pair](https://en.wikipedia.org/wiki/Ethernet_over_twisted_pair)
  (wikipedia)
- [Fast Ethernet:
  100BASE-TX](https://en.wikipedia.org/wiki/Fast_Ethernet#100BASE-TX) (wikipedia)
- [Gigabit Ethernet](https://en.wikipedia.org/wiki/Gigabit_Ethernet)
  (wikipedia)
- [Gigabit Ethernet:
  1000BASE-T](https://en.wikipedia.org/wiki/Gigabit_Ethernet#1000BASE-T)
  (wikipedia)
- [10GBASE-T](https://en.wikipedia.org/wiki/10_Gigabit_Ethernet#10GBASE-T) (wikipedia)


### Plenum-rated cables
Plenum-rated cables are made from a special plastic that retards fire
and produces less smoke than other cable types.

## Fiber optic
### Fiber optic connectors
<img src="{{site.baseurl}}/assets/netacad-it-essentials/connectors-fiber-optic.jpg" width="600">

## USB and Thunderbolt

**USB** (Universal Serial Bus) is a series of standards that specify
how cables connect, communicate and exchange power with electronic
devices and related peripherals.

**Thunderbolt** is an interface technology protocol designed for
high-speed transfer of all types of data along a single
cable. Thunderbolt cables do not have their own connector designs,
relying instead on existing types in the market.


### USB (and Thunderbolt) standards

#### Data rates


<table>
  <tr>
    <th>stand.</th>
	<td>USB 1.0</td>
	<td>USB 2.0</td>
	<td>USB 3.0</td>
	<td>USB 3.1</td>
	<td>USB 3.2</td>
	<td>USB 4</td>
  </tr>
  <tr>
    <th>data<br> rate</th>
	<td>1.5&#160;Mbps<br>(low&#160;speed)<br><br>
	    12&#160;Mpbs<br>(full&#160;speed)
	</td>
	<td>1.5&#160;Mbps<br>(low&#160;speed)<br><br>
	    12&#160;Mpbs<br>(full&#160;speed)<br><br>
		480&#160;Mpbs<br>(high&#160;speed)
	</td>
	<td>5&#160;Gpbs<br>(SuperSpeed)</td>
	<td>10&#160;Gpbs<br>(SuperSpeed+)</td>
	<td>20&#160;Gpbs<br>(SuperSpeed+)</td>
	<td>40&#160;Gpbs<br>(SuperSpeed+<br>&amp;&#160;Thunderbolt&#160;3)</td>
	
  </tr>
</table>

#### More details

| standard               | max data<br>transfer speed | connector type                               | cable length | max power |
|------------------------|----------------------------|----------------------------------------------|--------------|-----------|
| USB 1.1                | 12 Mbps                    | USB-A<br>USB-B                               | 3 m          | 2.5 W     |
| USB 2.0                | 480 Mbps                   | USB-A<br>USB-B<br>USB Micro-A<br>USB Micro-B | 5 m          | 2.5 W     |
| USB 3.2 Gen 1          | 5 Gbps                     | USB-A<br>USB-B<br>USB Micro-B<br>USB-C       | 3 m          | 4.5 W     |
| USB 3.2 Gen 1          | 10 Gbps                    | USB-A<br>USB-B<br>USB Micro-B<br>USB-C       | 3 m          | 100 W     |
| USB 3.2 Gen 2&#10005;2 | 20 Gbps                    | USB-C                                        | 3 m          | 100 W     |
| Thunderbolt 2          | 20 Gbps                    | Mini DisplayPort                             | 3 m          | 10 W      |
| Thuderbolt 3           | 20/40 Gbps                 | USB-C                                        | 0.5 m - 2 m  | 100 W     |
| USB 4                  | up too 40 Gbps             | USB-C                                        | -            | 100 W     |




### USB connector standards
Maximum number of USB devices that can be connected to a single USB
host controller: 127	
	
| connector | USB 1.0                          | USB 2.0                                             | USB 3.0                | USB 3.1                  | USB 3.2                  | USB 4   |
| data rate | 1.5 Mbps (low)<br>12 Mbps (full) | 1.5 Mbps (low)<br>12 Mbps (full)<br>480 Mbps (high) | 5 Gbps<br>(SuperSpeed) | 10 Gbps<br>(SuperSpeed+) | 20 Gbps<br>(SuperSpeed+) | 40 Gpbs |

<table>
  <tr>
    <td>USB type-A</td>
	<td><img src="{{site.baseurl}}/assets/netacad-it-essentials/usb-connector-type-a.png" width="100">
        <img src="{{site.baseurl}}/assets/netacad-it-essentials/usb-connector-type-a-reversible.png" width="100">
    </td>
  </tr>
  <tr>
	<td>USB type-B</td>
	<td><img src="{{site.baseurl}}/assets/netacad-it-essentials/usb-connector-type-b.png" width="100">
        <img src="{{site.baseurl}}/assets/netacad-it-essentials/usb-connector-type-b3.png" width="100">
    </td>
  </tr>
  <tr>
	<td>USB mini-B</td>
	<td><img src="{{site.baseurl}}/assets/netacad-it-essentials/usb-connector-mini-b-4pin.png" width="100">
        <img src="{{site.baseurl}}/assets/netacad-it-essentials/usb-connector-mini-b-5pin.png" width="100">
    </td>
  </tr>
  <tr>
	<td>USB micro-B</td>
	<td><img src="{{site.baseurl}}/assets/netacad-it-essentials/usb-connector-micro-b2.png" width="100">
        <img src="{{site.baseurl}}/assets/netacad-it-essentials/usb-connector-micro-b3.png" width="100">
    </td>
  </tr>
  <tr>
	<td>USB type-C</td>
	<td><img src="{{site.baseurl}}/assets/netacad-it-essentials/usb-connector-type-c.png" width="100">
    </td>
  </tr>
</table>

### Thunderbolt

- Maximum allowable length: 3 m
- Fiber-optic Thunderbolt interfaces have a maximum cable length of 60 m
- Thunderbolt 1:
  - Data transfer rate of up to 20 Gbps
  - Mini DisplayPort (MDP) connector
  - Capability to send PCIe/DisplayPort data and power over single cable
  - Support for up to 6 devices on a single port
- Thunderbolt 2
  - Support for up to 6 devices on a single port
  - Capability to send PCIe/DisplayPort data and power over single cable
  - Mini DisplayPort (MDP) connector
  - Data transfer rate of up to 20 Gbps
- Thunderbolt 3:
  - Provides support for up to 6 devices on a single port
  - Enables data transfer rate of up to 40 Gbps
  - Uses USB-C connector
  - Provides the capability to send PCIe/DisplayPort data and power over single cable


_References_:  
- [Understanding USB and Thunbderbolt:
  Speed, connectors and
  functionality](https://www.tripplite.com/products/usb-connectivity-types-standards)
  (TrippLite)
- [USB](https://en.wikipedia.org/wiki/USB) (wikipedia)
- examcompass.com


## Wireless systems, antennas, and devices

MIMO: Multiple Input / Multiple 
- a wireless technology that allows for significant increase in data
  throughput due to the use of multiple antennas and multiple data
  streams


_References_:  

- [Point-to-point and
  point-to-mulitpoint
  wireless](https://www.cablefree.net/wireless-technology/difference-point-point-point-multipoint/)
  (cablefree.net)
- [MIMO](https://en.wikipedia.org/wiki/MIMO) (wikipedia)






## Bluetooth

- Short-range wireless interconnetion of mobile phones, computers and
  other electronic devices.
- Devices operate in the 2.4 to 2.485 GHz radio frequency range and is
  typically used for PANs.


| physical level           | protocol level    |
|--------------------------|-------------------|
| radio frequency standard | Bluetooth pairing |

### Bluetooth classification

|                          | max. permitted power | approximate distance |
|--------------------------|----------------------|----------------------|
| class 1                  | 100 mW               | ~330 ft (100 m)      |
| class 2<br>(most common) | 2.5 mW               | ~30 ft (10 m)        |
| class 3                  | 1 mW                 | ~3 ft (1 m)          |

### Bluetooth specifications

| specification | version    | data transfer rate                 |
|---------------|------------|------------------------------------|
| 1.0           | v1.2       | 1 Mbps                             |
| 2.0           | v2.0 + EDR | 3 Mbps                             |
| 3.0           | v3.0 + HS  | 24 Mbps                            |
| 4.0           | v4.0 + LE  | 1 Mbps                             |
| 5.0           | v5.0 + LE  | 125 Kbps, 500 Kbps, 1 Mbps, 2 Mbps |

## IEEE 802.11 for WLAN



| standard                  | frequency          | max speed                      | max<br>indoor<br>range | bandwidth              | backwards<br>compatibility |
|---------------------------|--------------------|--------------------------------|------------------------|------------------------|----------------------------|
| 802.11**a**               | 5.0 GHz            | 54 Mbps                        | 35 m                   | 20 MHz                 | -                          |
| 802.11**b**               | 2.4 GHz            | 11 Mbps                        | 35 m                   | 22 MHz                 | -                          |
| 802.11**g**               | 2.4 GHz            | 54 Mbps                        | 38 m                   | 20 MHz                 | 802.11**b**                |
| 802.11**n**<br>(MIMO)     | 2.4 GHz<br>5.0 GHz | 600 Mbps<br>(4 &#10005; 150)   | 70 m                   | 24, 40 MHz             | 802.11**a**/**b**/**g**    |
| 802.11**ac**<br>(MU-MIMO) | 5.0 GHz            | 1.3 Gbps<br>(8 &#10005; 866.7) | 35 m                   | 20, 40,<br>80, 160 MHz | 802.11**a**/**n**          |

_References_:  
- [Professor Messer video CompTIA A+ 220-901: Wireless
  standards](https://www.youtube.com/watch?v=dORMbdIMd5s&list=PLG49S3nxzAnmlC1ZsppuM7yleDuYCMHrv&index=50)


# Security: wireless encryption

| WEP         | RC4 stream cipher; 64- and 128-bit key size                                                                                                                                                                                                                                                                                         |
| WPA         | RC4 with TKIP (temporal key integrity protocol)                                                                                                                                                                                                                                                                                     |
| WPA2 (2004) | AES with CCMP: counter Mode with cipher block chaining  message authentication code protocol                                                                                                                                                                                                                                        |
| WPS         | Wi-Fi Protected Setup (WPS) simplifies the configuration of new wireless networks by enabling non-technical users to easily set up new networks, configure network security settings and add new devices to an existing network. However, due to its known security vulnerabilities, WPS is not recommended and should be disabled. |




## Frequency ranges

| protocol  | frequency range   |
|-----------|-------------------|
| Bluetooth | 2.4 - 2.485 GHz    |
| RFID      | 125 MHz - 960 MHz |
| NFC       | 13.56 MHz         |

	
## Equipment for wired and wireless networks
### Test equipment

| network cable tester                                                                          | <img src="{{site.baseurl}}/assets/netacad-it-essentials/tool-cable-tester.jpg" height="100">                 |
| toner and probe                                                                               | <img src="{{site.baseurl}}/assets/netacad-it-essentials/tool-tone-generator-and-probe.jpg" height="100">     |
| multimeter                                                                                    | <img src="{{site.baseurl}}/assets/netacad-it-essentials/tool-multimeter.jpg" height="100">                   |
| loopback adpater/plug                                                                         | <img src="{{site.baseurl}}/assets/netacad-it-essentials/adapter-loopback.jpg" height="100">                  |
| wifi analyzer                                                                                 | <img src="{{site.baseurl}}/assets/netacad-it-essentials/tool-wifi-analyzer.jpg" height="100">                |
| optical time domain reflectometer<br>(OTDR)<br>(to find breaks in fiber-optic network cables) | <img src="{{site.baseurl}}/assets/netacad-it-essentials/optical-time-domain-reflectometer.jpg" height="100"> |




### Tools

| wire cutter/side cutter | <img src="{{site.baseurl}}/assets/netacad-it-essentials/tool-wire-cutter.jpg" height="100">     |
| wire stripper           | <img src="{{site.baseurl}}/assets/netacad-it-essentials/tool-wire-stripper.jpg" height="100">   |
| punch down tool         | <img src="{{site.baseurl}}/assets/netacad-it-essentials/tool-punch-down-tool.jpg" height="100"> |
| crimper                 | <img src="{{site.baseurl}}/assets/netacad-it-essentials/tool-crimper.jpg" height="100">         |


## Networking devices
Host/end devices vs intermediary devices

### Intermediary devices

| repeater (extender)         | regenerates weak signals                                                                                                           |
| hub                         | (**legacy**) connects devices in a LAN<br>- receives data one port, sends to all other ports<br>- does not segment network traffic |
| bridge                      | (**legacy**) divides LAN into segments                                                                                             |
| switch                      | microsegments LAN<br>filters and segments traffic by sending data only to intended devices                                         |
| wireless access point (WAP) | provides network access to wireless devices                                                                                        |
| router                      | connects networks                                                                                                                  |
| proxy                       | acts as an intermediary between a network host and the Internet                                                                    |
| wireless router             | router + wireless access                                                                                                           |
| domain controller (DC)      | a server computer that responds to security authentication requests within a computer domain                                       |


| switch            | connects multiple devices to the network                                                            |
| router            | forwards traffic between networks                                                                   |
| wireless router   | connects multiple wireless devices to the network and may include a switch to connected wired hosts |
| access point (AP) | connects to wireless router and is used to extend the reach of a wireless network                   |
| modem             | connects a home or small office to the internet                                                     |

### Switches vs bridges

| bridge                                | switch                         |
|---------------------------------------|--------------------------------|
| forwarding decisions made in software | decisions made in hardware     |
| connects fewer network segments       | connects more network segments |
| older and less effective              | newer and more effective       |


### Routers vs switches

| switches | use MAC addresses | to forward traffic | **within** a  network |
| switch   | connect           | computers          | within a network      |
| routers  | use IP addresses  | to forward traffic | to **other** networks |
| routers  | connect           | networks           | to other networks     |




- hub has no routing table or intelligence on where to send
  information and broadcasts all network data across each connection

UPNP: 
- a type of architecture that simplifies networking by allowing
  devices to dynamically join a network, autoconfigure, and learn
  about the presence and capabilities of other devices
- zero-configuration networking


## Security


| firewall                   | placed between internal and external networks, monitors, controls, filters incoming and outgoing traffic        |
| IDS                        | copies traffic and forwards for evaluation                                                                      |
| IPS                        | installed inline, evaluates traffic before forwarding to destination                                            |
| UTM                        | - IDS and IPS functionalities<br>- stateful firewall services<br>- zero-day protection<br>-DoS, DDoS protection |
| Endpoint Management Server | centralizes views of all devices on network for administration with single interface                            |

## Networking technologies

| Active Directory                      | AD   | a directory services implementation providing authentication, group and user management, policy administration, etc.                            |
| Lightweight Directory Access Protocol | LDAP | an open and cross platform protocol used for directory services authentication                                                                  |
| Dynamic Host Configuration Protocol   | DHCP | automatically assigns IP addressing information to hosts                                                                                        |
| Domain Name System                    | DNS  | convert domain names into IP addresses                                                                                                          |
| Network Address Translation           | NAT  | hides internal IP addresses by modifying the IP address information in IP packet headers while it is in transit across a traffic routing device |
| Access control                        |      |                                                                                                                                                 |

## Common networking ports

| FTP     | TCP/20<br>TCP/21 | File Transfer Protocol              | send and receive files between systems                              |
| SSH     | TCP/22           | Secure SHell                        | encrypted console access                                            |
| Telnet  | TCP/23           | Telecommunication Networrk          | insecure consle access                                              |
| SMTP    | TCP/25           | Simple Mail Transfer Protocol       | transfer emails between servers                                     |
| DNS     | UDP/53           | Domain Name System                  | convert domain names into IP addresses                              |
| DHCP    | UDP/67<br>UDP/68 | Dynamic Host Configuration Protocol | automated configuration of IP addresses                             |
| HTTP    | TCP/80           | HyperText Transfer Protocol         | web server communication                                            |
| POP3    | TCP/110          | Post Office Protocol v3             | email client protocol                                               |
| POP3S   | TCP/995          | POP3 Secure                         | email client protocol with encryption                               |
| IMAP4   | TCP/143          | Internet Message Access Protocol v4 | email client protocol                                               |
| IMAPS   | TCP/993          | IMAP Secure                         | email client protocol with encryption                               |
| HTTPS   | TCP/443          | HTTP Secure                         | web server communication with encryption                            |
| NetBIOS | UDP/137          | NetBIOS name service                | register, remove, and find Windows service by name                  |
| NetBIOS | UDP/138          | NetBIOS datagram service            | Windows connection-less data transfer                               |
| NetBIOS | TCP/139          | NetBIOS session service             | Windows connection-oriented data transfer                           |
| SNMP    | UDP/161          | Simple Network Management Protocol  | gather statistics from networks                                     |
|         |                  |                                     | SNMP Agent receives requests on UDP port 161                        |
|         |                  |                                     | SNMP management station receives SNMP notifications on UDP port 162 |
| LDAP    | TCP,UDP/389      | Lightweight Domain Access Protocol  | management and authentication on network                            |
| SLP     | TCP/427,UDP/427  | Service Location Protocol           | (macos?) service discovery                                          |
| SMB     | TCP/445          | Server Message Block                | Windows file transfer and printer sharing                           |
| CIFS    | TCP/445          | Common Internet File System         | Windows file transfer and printer sharing                           |
| AFP     | TCP/548          | Apple Filing Protocol               | macos file transfer                                                 |
| RDP     | TCP/3389         | Remote Desktop Protocol             | graphical display of remote devices                                 |
|         | TCP/9100         |                                     | raw data stream for printing                                        |
| SLP     | UDP/427          | Service Location Protocol           | service discovery protocol                                          |
| AFP     | TCP/548          | Apple File Protocol                 | Apple's proprietary file sharing network protocol                   |
| RADIUS  | TCP,UDP/1812     | Remote Authentication<br>                                    |                                                                     |

_References:_  
- [Professor
  Messer:](https://www.youtube.com/watch?v=MTPTow2PTfY&list=PLG49S3nxzAnmlC1ZsppuM7yleDuYCMHrv&index=48&t=11m10s)


## Management of local storage

### RAID: Redundant Array of Independent Disks

<img src="{{site.baseurl}}/assets/netacad-it-essentials/raid-levels.jpg" width="800">

#### Standard RAID levels


<table>
  <tr>
    <th>RAID 0</th>
    <th>RAID 1</th>
    <th>RAID 5</th>
    <th>RAID 6</th>
  </tr>
  <tr>
    <td><img src="{{site.baseurl}}/assets/netacad-it-essentials/raid-0.svg" height="150"></td>
    <td><img src="{{site.baseurl}}/assets/netacad-it-essentials/raid-1.svg" height="150"></td>
    <td><img src="{{site.baseurl}}/assets/netacad-it-essentials/raid-5.svg" height="150"></td>
    <td><img src="{{site.baseurl}}/assets/netacad-it-essentials/raid-6.svg" height="150"></td>
  </tr>
</table>

Remarks:  
- RAID 0 uses striping and does not use a mirror or parity disk. This
  means corrupted data cannot be recovered and that an issue on one
  disk could cause information on other disks to be unreadable.


#### Nested RAID levels
<table>
  <tr>
	<th>RAID 0 + 1</th>
	<th>RAID 1 + 0</th>
  </tr>
  <tr>
    <`th><img src="{{site.baseurl}}/assets/netacad-it-essentials/raid-01.svg" height="250"></th>
    <th><img src="{{site.baseurl}}/assets/netacad-it-essentials/raid-10.svg" height="250"></th>
  </tr>
</table>


_References_:  

- [Standard RAID
  levels](https://en.wikipedia.org/wiki/Standard_RAID_levels)
  (wikipedia)
- [Nested RAID
  levels](https://en.wikipedia.org/wiki/Nested_RAID_levels) (wikipedia)


## OSI Model


<table>
 <tr>
  <td>7</td>
  <td>Application</td>
  <td>Data</td>
  <td>End user layer:<br>
  program that opens what was sent or creates what is too be sent
  </td>
  <td>serves as the window for users and application processes to
  access the networks services
  </td>
 </tr>
 <tr>
  <td>6</td>
  <td>Presentation</td>
  <td>Data</td>
  <td>
  </td>
  <td>Formats the data to be presented to the application layer. It can be viewed as the “translator” for the network.​
  </td>
 </tr>
</table>



| 7 | Application | Data     |
| 6 | Presetation | Data     |
| 5 | Session     | Data     |
| 4 | Transport   | Segments |
| 3 | Network     | Packets  |
| 2 | Data link   | Frames   |
| 1 | Physical    | Bits     |


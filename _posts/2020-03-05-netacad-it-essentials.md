---
layout: post
title:  "Netacad IT essentials cheatsheet"
date:   2020-03-05 +0100
categories: IT
published: true
---

These are notes, in the form of a cheatsheet, on computer networking
and architecture, chiefly in preparation for CompTIA A+.


Primary source is [Netacad](https://www.netacad.com) (by Cisco), but
other material is also included.

At the moment no attempt has been made at organizing these notes.
These notes are definitely not comprehensive and shouldn't be relied
on. 

---

## CompTIA A+ Exam Objectives
[See this page](https://www.professormesser.com/objectives/ "A+ exam objectives")

## Acronyms
- ESD: ElectroStatic Discharge
- AT: Advanced Technology
- ATX: AT Extended
- PCB: Printed Circuit Board
- CPU: Central Processing Unit
- RAM: Random-Access Memory
- DRAM: Dynamic RAM
- SRAM: Static RAM
- SDRAM: Synchronous Dynamic RAM
- DDR SDRAM: Double-Data Rate SDRAM
- ROM: Read-Only Memory
- BIOS: Basic Input/Output System
- UEFI: Unified Extensible Firmware Interface
- SATA: Serial Advanced Technology Attachment
- PATA: Parallel ATA
- IDE: Integrated Drive Electronics
- EIDE: Enhanced IDE
- ITX: Integrated Technology eXtended
- SSD: Solid-State Device
- POST: Power-On Self-Test
- PGA: Pin Grid Array
- LGA: Land Grid Array
- ZIF: Zero Force Insertion
- ECC: Error-Correcting Code
- DIP: Dual Inline Package
- SIMM: Single Inline Memory Module
- DIMM: Dual 
- SODIMM: Small Outline DIMM
- NIC: Network Interface Card
- USB: Universal Serial Bus
- PCI: Peripheral Component Interconnect
- PCIe: PCI Express
- AGP: Accelerated Graphics Port
- SCSI: Small Computer System Interface
- HDD: Hard Disk Drive
- RPM: Revolutions Per Minute
- NVMe: Non-Volatile Memory Express
- DVI: Digital Visual Interface
- VGA: Video Graphics Array
- RCA: Radio Corporation of America
- PS/2: Personal System 2
- DIN: Deutsches Institut für Normung
- KVM: keyboard, video, and mouse
- NFC: Near Field Communication
- WDM: Wave Division Multiplexing
- NAT: Network Address Translation
- PAT: Port Address Translation
- PSU: Power Supply Unit
- SD: Secure Digital
- DSP: Digital Signal Processor
- SDS: Safety Data Sheet
- UPS: Uninterruptible Power Supply
- SPS: Standby power supply
- RISC: Reduced Instruction Set Computer
- CISC: Complex Instruction Set Computer
- RAID: Redundant Array of Inexpensive/Independent Drives
- DHCP: Dynamic Host Configuration Protocol
- RFID: Radio Frequency IDentification
- NFC: Near Field Communication
- AP: Access Point
- WDM: Wave Division Multiplexing
- IDS: Intrusion Detection System
- IPS: Intruction Prevention System
- UTM: Unified Threat Management
- ACL: Access Control List
- PoS: Point of Sale (device)
- AFH: Adaptive Frequency Hopping
- UTP: Unshielded Twisted Pair
- APIPA: Automatic Private IP Addressing
- ARP: Address Resolution Protocol
- CIDR: Classless Inter-Domain Routing
- WEP: Wired Equivalent Privacy
- WPA: Wifi Protected Access
- TKIP: Temporal Key Integrity Protocol
- AES: Advanced Encryption Standard
- WPS: Wi-Fi Protected Setup
- PLC: Power-Line Communication (Ethernet over Power)
- DMZ: De-Militarized Zone
- UPNP: Universal Plug aNd Play
- QoS: Quality of Service
- LTE: Long-Term Evolution
- FAT: File Allocation Table
- NTFS: New Technology File System
- NFS: Network File System
- LCD: Liquid Crystal Display
- CRU: Customer Replaceable Unit
- FRU: Field Replaceable Unit
- MAPI: Messaging Application Programming Interface (connects
  Microsoft Outlook clients to Exchange servers)
- MIME: Multipurpose Internet Mail Extension
- PPM: Page Per Minute
- DPI: Dots Per Inch
- CMY/CMYK: Cyan Magenta Yellow/CMY Key (black)
- MTBF: Mean Time Between Failures
- TCO: Total Cost of Ownershipe
- ADF: Automatic Document Feeder
- CLI: Command Line Interface
- GUI: Graphical User Interface
- API: Application Programming Interface
- USTM: User State Migration Tool
- PXE: Preboot eXecution Environment
- TPM: Trusted Platform Module

## Glossary  

| expansion slot        | provides locations for connecting additional  components to the motherboard                                             |
| BIOS/UEFI             | boots computer, performs power-on self-test                                                                             |
| RAM                   | temporary location to store data and applications                                                                       |
| chipset               | controls how system hardware interacts with CPU and motherboard                                                         |
| CPU                   | interprets and executes commands, outputs information                                                                   |
| CPU socket            | connection between CPU and motherboard                                                                                  |
| volatile/non-volatile | cotent erased/not erased when power is off                                                                              |
| NIC                   | connects computer to network using cable                                                                                |
| wireless NIC          | connects computer to network using radio frequency                                                                      |
| USB controller card   | provides additional USB ports                                                                                           |
| eSATA card            | provides additional internal and external SATA ports through a single PCIe slot                                         |
| SATA                  | standard defining how data is transferred, transfer rates, physical characteristics of cables and connectors            |
| NVMe                  | specifications for interface between SSD, PCIe bus, and OS                                                              |
| NAT                   | translates the IP addresses of computers in a LAN to a single IP address                                                |
| PAT                   | permits multiple devices on a LAN to be mapped to a single public IP address                                            |
| router                | routes data from a LAN to another network                                                                               |
| switch                | connects multiple computers to a network                                                                                |
| patch panel           |                                                                                                                         |
| DHCP                  |                                                                                                                         |
| broadband, WDM        | uses different frequencies to transmit multiple signals simultaneously over the same medium                             |
| endpoint device       | any internet-capable device that can be connected to a TCP/IP network                                                   |
| power inverter        | power supply for laptop backlight                                                                                       |
| port replicator       |                                                                                                                         |
| tethering             | capability of mobile device to share its internet connection with other devices                                         |
| DMZ                   | a lightly protected subnet consisting of publicly available servers placed on the outside of the company's firewall     |
| file systems          | a set of logical constructs that an operating system can use to track manage files on a disk volume                     |
|                       | provides the directory structure that organizes the user’s operating system, application, configuration, and data files |
| registry              | database containing all the information about a computer (Windows)                                                      |
| driver                |                                                                                                                         |
| API                   | a set of guidelines so that an application be compatible with the OS                                                    |
|                       | allows programs access to ressources managed by OS in a consistent and reliable way                                     |
| TPM                   | chip designed to secure hardware by storing encryption keys, digital certificates, passwords, and data                  |
|                       |                                                                                                                         |


| Windows Internet Name Service            | WINS | a legacy    computer name registration and resolution service that maps computer NetBIOS names to IP addresses       |
| Active Directory                         | AD   | a directory services implementation providing authentication, group and user management, policy administration, etc. |
| Single-SignOn                            | SSO  | a property of access control where a single authentication gives access to multiple services                         |
| Product Release Instruction              | PRI  | used as a reference during a mobile device update process                                                            |
| Preferred Roaming List                   | PRL  | database on a mobile device with service provider details allowing connection                                        |
| International Mobile Equipement Identity | IMEI | a unique identification or serial number that all mobile phones and smartphones have                                 |
| International Mobile Subscriber Identity | IMSI | uniquely identifies a user on a cellular network                                                                     |
| Service Set IDentifiers                  | SSID | names of wireless networks available  to a device.                                                                   |
| User State Migration Tool                | USMT | Windows command line utility to transfer files and settings between Windows PCs                                      |
|                                          |      |                                                                                                                      |


# Protocols

| Internet Control Message Protocol     | ICMP  | used by devices on a network to send control and error messages                                     | internet-layer                                |
| Lightweight Directory Access Protocol | LDAP  | an open and cross platform protocol used for directory services authentication                      | TCP,UDP/389                                   |
| Single Network Management Protocol    | SNMP  | collects and organizes informaion about managed devices on IP networks                              | UDP/161                                       |
| Domain Name System/Server             | DNS   |                                                                                                     | UDP/53                                        |
| Remote Desktop Protcol                | RDP   | provides a user with a graphical interface to connect to another computer over a network connection | TCP,UDP/3389                                  |
| HyperText Transfer Protocol           | HTTP  |                                                                                                     | TCP/80                                        |
| HTTP Secure                           | HTTPS | extension of HTTP for secure communication                                                          | TCP/443                                       |
| Single Mail Transfer Protocol         | SMTP  | email routing between mail servers, or from client to server                                        | TCP/25                                        |
| Post Office Protocol version 3        | POP3  | email retrieval from remote server to local email client<br>typically does not leave copy on server | TCP/110                                       |
| Internet Message Access Protocol      | IMAP  | same as POP3, but allows simultaneous access by multiple clients, synchronizes with server          | TCP/143                                       |
| File Transfer Protocol                | FTP   |                                                                                                     | TCP/20 (active data mode)<br>TCP/21 (control) |
| NetBIOS services                      |       |                                                                                                     | UDP/137,138<br>TCP/139                        |
| Server Message Block                  | SMB   |                                                                                                     |                                               |
| Common Internet File System           | CIFS  | successor to SMB                                                                                    | UDP/137,138<br>TCP/139,445                    |
| Service Location Protocol             | SLP   | a service discovery protocol                                                                        | UDP/427                                       |

| Dynamic Host Configuration Protocol   | DHCP  | automatically assigns IP addressing information to hosts                                            | server: UDP/67<br>client: UDP/68              |
| Secure Shell                          | SSH   | encrypted communication link                                                                        | TCP/22                                        |
| Telnet                                |       | unencrypted communication                                                                           | TCP/23                                        |


With info taken from [Professor
Messer:](https://www.youtube.com/watch?v=MTPTow2PTfY&list=PLG49S3nxzAnmlC1ZsppuM7yleDuYCMHrv&index=48&t=11m10s)

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


## Power and electrical safety

- static electricity
- ESD
  - humans: `3,000V`/`10,000V`
  - computer components: `30V`

# Power fluctuation

| blackout    | complete loss of AC power                                           |
| brownout    | reduced level voltage of AC power                                   |
| noise       | interference from generators and lighting                           |
| spike       | sudden increase in voltage exceeding normal voltage                 |
| power surge | dramatic increase in voltage above normal flow of elecrical current |

# Power protection devices

| surge protector                       | diverts extra electrical voltage to ground        |
| UPS<br>(Uninterruptible Power Supply) | supplies constant level of power                  |
| SPS<br>(Standby Power Supply)         | provides backup battery<br>not as reliable as UPS |




## Types of computer devices
- Desktops
- Laptops
- Tablets
- Smartphones
- Smartwatchs
- Fitness trackers
- VR and AR devices
- other IoT devices

## Types of printers

| inkjet     | electrostatic spray | 
| laser      | imaging drums       | 
| thermal    |                     | 
| dot matrix | impact technology   | 
| 3D         |                     | 

# Types of printer connectors

| serial   | legacy, slow (dot matrix) |
| parallel | legacy                    |


# Steps in laser printing

![]({{site.baseurl}}/assets/netacad-it-essentials/printing-laser-how-it-works.jpg)

1. **Processing.** The data from the source must be converted into a
   printable form. The printer converts data from common languages,
   such as Adobe PostScript (PS) or HP Printer Command Language (PCL),
   to a bitmap image stored in the printer’s memory. Some laser
   printers have built-in Graphical Device Interface (GDI)
   support. GDI is used by Windows applications to display printed
   images on a monitor so there is no need to convert the output to
   another format such as PS or PCL.
2. **Charging.** The image on the drum is removed and the drum is
   conditioned for the new image. A wire, grid, or roller receives a
   charge of approximately -600 volts DC uniformly across the surface
   of the drum. The charged wire or grid is called the primary
   corona. The roller is called a conditioning roller.
3. **Exposing.** To write the image, the photosensitive drum is exposed
   with the laser beam. Every portion of the drum that is scanned with
   the light has the surface charge reduced to about -100 volts
   DC. This electrical charge has a lower negative charge than the
   rest of the drum. As the drum turns, an invisible image is created
   on the drum.
4. **Developing.** The toner is applied to the image on the drum. A
   control blade holds the toner at a microscopic distance from the
   drum. The toner then moves from the control blade to the more
   positively charged image on the drum.
5. **Transferring.** The toner, attached to the image, is transferred to
   the paper. The corona wire places a positive charge on the
   paper. Because the drum was charged negatively, the toner on the
   drum is now attracted to the paper. The image is now on the paper
   and is held in place by the positive charge. Because color printers
   have three cartridges of toner, a colored image must go through
   multiple transfers to be complete. To ensure precise images, some
   color printers write multiple times onto a transfer belt that
   transfers the complete image to paper.
6. **Fusing.**  The toner is permanently fused to the paper. The printing
   paper is rolled between a heated roller and a pressure roller. As
   the paper moves through the rollers, the loose toner is melted and
   fused with the fibers in the paper. The paper is then moved to the
   output tray as a printed page. Laser printers with duplex
   assemblies can print on both sides of a sheet of paper.
7. **Cleaning.**  When an image has been deposited on the paper and the
   drum has separated from the paper, the remaining toner must be
   removed from the drum. A printer might have a blade that scrapes
   the excess toner. Some printers use an AC voltage on a wire that
   removes the charge from the drum surface and allows the excess
   toner to fall away from the drum. The excess toner is stored in a
   used toner container that is either emptied or discarded.


# Printer servers
- Software
- Hardward
- Dedicated

## Troubleshooting
![]({{site.baseurl}}/assets/netacad-it-essentials/troubleshooting-six-steps.jpg)

### Operating systems
![]({{site.baseurl}}/assets/netacad-it-essentials/os-diagram.jpg)

1. **Multi-user.**  Two or more users have individual accounts that allow
   them to work with programs and peripheral devices at the same time.
2. **Multitasking.**  The computer is capable of operating multiple
   applications at the same time.
3. **Multiprocessing.**  The operating system can support two or more
   CPUs.
4. **Multithreading.**  A program can be broken into smaller parts that
   are loaded as needed by the operating system. Multithreading allows
   different parts of a program to be run at the same time.

Basic functions.
- Hardware Access
- File and Folder Management
- User Interface (CLI and GUI)
- Application Management

# 32- and 64-bit processor architecture

| architecture | description                                                                                         | number of addresses              |
|--------------|-----------------------------------------------------------------------------------------------------|----------------------------------|
| 32-bit       | - processes instructions using 32-bit address space<br>- max. 4GB of RAM                                | 4,294,967,295 bytes              |
| 64-bit       | - backward-compatible with 32-bit<br>- additional registers for instructions using 64-bit address space | 18,446,744,073,709,551,615 bytes |

# Hard drive partitioning
- MBR
  - boot loader
- GUID
- GPT

- Primary partition
- Active partition
- Extended partition
- Logical drive
- Basic disk
- Dynamic disk
- Formatting

# File systems

- FAT32
- NTFS
- exFAT (FAT64)
- CDFS
- NFS

|                     | FAT32 | NTFS |
| max filename length | 8.3   | 255  |
|                     |       |      |


# Virtualization and cloud computing
- Virtualization is a technology that enables a single computer to
  host multiple virtual computers that share the same host computer
  hardware.
- Cloud computing is a technology that enables the separation of
  applications from the hardware.
- Virtualization is the foundation which supports cloud computing.
- Cloud computing provides users with on-demand delivery of computer
  services over the Internet.
- Virtualization has many advantages over the traditional use of
  dedicated servers, such as better use of resources, less space
  required, reduced cost, and increased server uptime.
- Types of cloud services:
  - SaaS (services)
  - PaaS (platforms)
  - IaaS (infrastructure)

## Hardware

Links:
- [Main parts of computer hardware and their
  functions](https://www.skillonpage.com/main-parts-of-computer-hardware-and-its-function/)
  
| computer casing                  | ![]({{site.baseurl}}/assets/netacad-it-essentials/computer-casing.jpg)   |
| power supply unit                | ![]({{site.baseurl}}/assets/netacad-it-essentials/power-supply-unit.jpg) |
| motherboard                      | ![]({{site.baseurl}}/assets/netacad-it-essentials/motherboard-red.jpg)   |
| CPU/processor                    | ![]({{site.baseurl}}/assets/netacad-it-essentials/cpu-or-processor.jpg)  |
| chipset                          | ![]({{site.baseurl}}/assets/netacad-it-essentials/chipset.jpg)           |
| RAM                              | ![]({{site.baseurl}}/assets/netacad-it-essentials/ram-memory-module.jpg) |
| video card/GPU/VGA/graphics card | ![]({{site.baseurl}}/assets/netacad-it-essentials/video-card.jpg)        |
| ROM (storing BIOS firmware)      | ![]({{site.baseurl}}/assets/netacad-it-essentials/rom-bios-firmware.jpg) |
| CMOS battery                     | ![]({{site.baseurl}}/assets/netacad-it-essentials/cmos-battery.jpg)      |
| bus                              | ![]({{site.baseurl}}/assets/netacad-it-essentials/bus.jpg)               |
| sound card                       | ![]({{site.baseurl}}/assets/netacad-it-essentials/sound-card.jpg)        |
| HDD or SSD                       | ![]({{site.baseurl}}/assets/netacad-it-essentials/hard-disk.jpg)         |
| optical drive                    | ![]({{site.baseurl}}/assets/netacad-it-essentials/optical-drive.jpg)     |
| keyboard                         | ![]({{site.baseurl}}/assets/netacad-it-essentials/computer-keyboard.jpg) |
| mouse                            | ![]({{site.baseurl}}/assets/netacad-it-essentials/computer-mouse.jpg)    |
| monitor                          | ![]({{site.baseurl}}/assets/netacad-it-essentials/computer-monitor.jpg)  |
|                                  |                                                                          |

# Main parts
# Cases
Also chassis/tower/housing/box.  
Factors in choosing a computer case:  
- model:
  - horizontal case
  - full-size tower
  - compact tower
  - all-in-one
  - super tower, full tower, mid tower, cube base, etc.
- size
- power supply
- appearance
- status display
- vents

# Case fans
Factors to consider when choosing a case fan:
![]({{site.baseurl}}/assets/netacad-it-essentials/case-fan-choice-factors.jpg)

# Power supplies
- Form factors   

  | AT     | obsolete                                          |
  | ATX    | obsolete                                          |
  | ATX12V | most common, second motherboard connector for CPU |
  | EPS12V | network servers, high-end desktops                |

- Voltages
  - digital circuits: `3.3V`, `5V`
  - motors, fans: `12V`

![]({{site.baseurl}}/assets/netacad-it-essentials/power-supply-choice-factors.jpg)

Laptops: power inverter: power supplies for backlight


# Power supply connectors

| ATX 20-/24-pin slotted connector              | motherboard                                   | ![]({{site.baseurl}}/assets/netacad-it-essentials/connector-slotted.jpg)         |
| SATA keyed<br>(power: 15 pins; data: 7 pins)  | hard drives                                   | ![]({{site.baseurl}}/assets/netacad-it-essentials/connector-sata.jpg)            |
| Molex keyed                                   | hard drives, optical drives                   | ![]({{site.baseurl}}/assets/netacad-it-essentials/connector-molex.jpg)           |
| Berg keyed                                    | floppy drives                                 | ![]({{site.baseurl}}/assets/netacad-it-essentials/connector-berg.jpg)            |
| ATX 4- or EPS 8-pin auxiliary power connector |                                               | ![]({{site.baseurl}}/assets/netacad-it-essentials/connector-auxiliary-power.jpg) |
| 6/8-pin PCIe power connector                  | power to internal components                  | ![]({{site.baseurl}}/assets/netacad-it-essentials/connector-pcie-power.jpg)      |
| PATA/IDE/EIDE 34 or 40 pins                   | floppy disks<br>hard drives or optical drives | ![]({{site.baseurl}}/assets/netacad-it-essentials/pata-ide-eide-cable.jpg)       |

	


## Motherboard
Also: system board, main board  

![]({{site.baseurl}}/assets/netacad-it-essentials/motherboard-blue.jpg)


**Main motherboard components**  
- CPU
- RAM
- expansion slots
- chipset
- BIOS or UEFI chip

**Motherboard connectors**

| SATA         | disk drive interface                 | ![]({{site.baseurl}}/assets/netacad-it-essentials/motherboard-connection-sata.png) |
| IDE          | older standard,  `40` pins           | ![]({{site.baseurl}}/assets/netacad-it-essentials/motherboard-connection-ide.png)  |
| internal USB | external USB 3 (USB 1/2 have 9 pins) | ![]({{site.baseurl}}/assets/netacad-it-essentials/motherboard-connection-internal-usb.png)  |

**Connecting drives to motherboard**
| internal drives | connect with SATA                                |
| external drives | - USB, eSATA, Thunderbolt<br>- legacy: IDE, EIDE |

# Motherboard form factors
From [Wikipedia: computer form factor](https://en.wikipedia.org/wiki/Computer_form_factor):
![]({{site.baseurl}}/assets/netacad-it-essentials/motherboard-form-factor-comparison.jpg)



# Installing the motherboard
1. Aign the motherboard in the correct direction.
2. Locate the standoffs.
3. Install standoffs in the computer case.
4. Align I/O plate to the back of computer case.![]({{site.baseurl}}/assets/netacad-it-essentials/io-plate.jpg)

5. Lower motherboard in place.
6. Install the screws into the standoffs.

# Motherboard chipset  

| Northbridge | memory controller hub | high speed access to CPU, RAM, video card                            |
| Southbridge | I/O contoller hub     | slower speed devices (hard drives, USB ports, expansion slots, etc.) |

# Motherboard form factors

| ATX       | `12in x 9.6in`  | most common |
| micro-ATX | `9.6in x 9.6in` | small form factor computers  |
| mini-ITX  | `6.7in x 6.7in` | thin clients; little power, no fan needed, only `1` PCI slot|
| ITX       | `8.5in x 7.5in` |              |

"Amim 12-6":

ATX 12" x 9.6"
Micro ATX 9.6" x 9.6"
ITX 8.5" x 7.5"
Mini ATX 6.7" x 6.7"



# Front panel

| front panel cables<br>(with pin 1 indicator)      | ![]({{site.baseurl}}/assets/netacad-it-essentials/front-panel-cables-pin-1-indicator.jpg)      |
| system panel connectors<br>(with pin 1 indicator) | ![]({{site.baseurl}}/assets/netacad-it-essentials/system-panel-connectors-pin-1-indicator.jpg) |



## CPU  
# Enhancing CPU operation  

| Hyper-threading (Intel) | multiple pieces of code (threads) are executed simultaneously in the CPU |
| HyperTransport (AMD)    | high-speed connection between CPU and Northbridge                        |
| overclocking            | make CPU work at speed faster than specification                         |
| CPU virtualization      | hardware feature enabling CPU to act as multiple processors              |



# CPU sockets

| PGA | contact pins on CPU; ZIF | mainly used by AMD   |
| LGA | contact pins on socket   | mainly used by Intel |

![]({{site.baseurl}}/assets/netacad-it-essentials/cpu-sockets.jpg)

# Installing the CPU
1. Orient the CPU to the CPU slot.
2. Press the CPU into the CPU slot.
3. Lock the CPU into place.
4. Apply thermal paste to the CPU.
5. Install the heatsink.
6. Secure the heatsink.

## Cooling systems

| passive | heat sink |
| active  | fan       |

## Memory  
# Types of memory

| ROM | non-volatile | directly accessed by CPU |
| RAM | volatile     |                          |

# Types of ROM

| ROM    | generic term; written when manufactured                                                   | ![]({{site.baseurl}}/assets/netacad-it-essentials/rom.jpg)        |
| PROM   | Programmable ROM (only once, not erasable)                                                | ![]({{site.baseurl}}/assets/netacad-it-essentials/rom-prom.jpg)   |
| EPROM  | Erasable Programmable ROM (using ultra violet)                                            | ![]({{site.baseurl}}/assets/netacad-it-essentials/rom-eprom.jpg)  |
| EEPROM | Electrically Erasable Programmable ROM (using electical signals); Flash memory; NAND, NOR | ![]({{site.baseurl}}/assets/netacad-it-essentials/rom-eeprom.jpg) |


# Types of RAM 

| DRAM       | older technology; gradually discharges                                        |             |            |        |
| SRAM       | faster, expensive; lower power consumption used for cache                     |             |            |        |
| SDRAM      | DRAM operating in sync with memory bus                                        |             |            |        |
| DDR SDRAM  | `2x` faster thab SDRAM; supports `2` writes and `2` reads per CPU clock cycle | `184` pins  | `200MHz`   | `2.5V` |
| DDR2 SDRAM |                                                                               | `240` pins | `533MHz`   | `1.8V` |
| DDR3 SDRAM | `2x` clock rate over DDR2                                                     | `240` pins  | `800MHz`   | `1.5V` |
| DDR4 SDRAM | `4x` storage capacity over DDR3                                               | `288` pins  | `1,600MHz` | `1.2V` |
| GDDR SDRAM | specifically designed for video **G**raphics                                  |             |            |        |



# Memory modules
- Notch designates type of memory module (DDR vs DDR2 vs DDR3 etc.)
- Single-sided vs double-sided  
- Single-channel vs dual-channel  

| DIP    | individual memory chip      | dual rows of pins                                                                                   | ![]({{site.baseurl}}/assets/netacad-it-essentials/memory-module-dip.jpg)    |
| SIMM   | holds several memory chips  | `30` or `70` pins                                                                                   | ![]({{site.baseurl}}/assets/netacad-it-essentials/memory-module-simm.jpg)   |
| DIMM   | holds SDRAM, DDRX SDRAM     | `160` pins (SDRAM)<br>`184` pins (DDR SDRAM)<br>`240` pins (DDR2/3 SDRAM)<br>`288` pins (DDR SDRAM) | ![]({{site.baseurl}}/assets/netacad-it-essentials/memory-module-dimm.jpg)   |
| SODIMM | smaller (printers, laptops) | `72` or `100` pins (`32`-bit transfer)<br>`144`, `200`, `204`, `260` pins (`64`-bit transfer)       | ![]({{site.baseurl}}/assets/netacad-it-essentials/memory-module-sodimm.jpg) |
|        |                             |                                                                                                     |                                                                             |

# Cache memory  
**L**=level
| L1 | integrated into CPU                             | SRAM           |
| L2 | usually soldered onto motherboard, close to CPU | typically DRAM |
| L3 | high-end workstations, server CPUs              |                |

# Memory errors

| non-parity | no check for errors                                 |
| parity     | `8` bits for data, `1` bit for error-checking       |
| ECC        | detects multiple errors, corrects single-bit errors |

# Installing memory modules
1. Open the RAM slot levers.
2. Orient the RAM chip to the motherboard slot.
3. Lower the RAM chip into the slot.
4. Press down firmly to lock the RAM chip.


## Adapter cards  
![]({{site.baseurl}}/assets/netacad-it-essentials/adapter-cards.jpg)

| storage controller card<br>(e.g. RAID controllers; provide fault tolerance, increase speed) | ![]({{site.baseurl}}/assets/netacad-it-essentials/storage-controller-card.jpg) |
| I/O card                                                                                    | ![]({{site.baseurl}}/assets/netacad-it-essentials/io-card.jpg)                 |
| NIC                                                                                         | ![]({{site.baseurl}}/assets/netacad-it-essentials/nic-card.jpg)                |
| capture card                                                                                | ![]({{site.baseurl}}/assets/netacad-it-essentials/capture-card.jpg)            |
| GPU (discrete)                                                                                         |                                                                                |

# GPU
Discrete (i.e. a separate entity) vs integrated (into GPU), for both
desktops and laptops

## Expansion slots 

| PCI                     | `32` or `64` bits                              | mostly obsolete                      | ![]({{site.baseurl}}/assets/netacad-it-essentials/expansion-slot-pci.jpg)        |
| mini-PCI                | smaller; type I, II, III                       | found in some laptops                | ![]({{site.baseurl}}/assets/netacad-it-essentials/expansion-slot-mini-pci.jpg)   |
| PCI-X<br>(PCI eXtended) | update of PCI                                  | mostly obsolete                      | ![]({{site.baseurl}}/assets/netacad-it-essentials/expansion-slot-pci-x.jpg)      |
| PCIe<br>(PCI Express)   | uses serial bus; `x1`, `x4`, `x8`, `x16` slots |                                      | ![]({{site.baseurl}}/assets/netacad-it-essentials/expansion-slot-pcie.jpg)       |
| Riser Card              | provides additional expansion slots            |                                      | ![]({{site.baseurl}}/assets/netacad-it-essentials/expansion-slot-riser-card.jpg) |
| AGP                     | high-speed slot for AGP video card             | superseded by PCI;rarely found today | ![]({{site.baseurl}}/assets/netacad-it-essentials/expansion-slot-agp.jpg)        |

# PCI vs PCIe

| PCI       | ![]({{site.baseurl}}/assets/netacad-it-essentials/expansion-slot-example-pci.jpg)     |
| PCIe - x1 | ![]({{site.baseurl}}/assets/netacad-it-essentials/expansion-slot-example-pcie-x1.jpg) |
| PCIe - x16 | ![]({{site.baseurl}}/assets/netacad-it-essentials/expansion-slot-example-pcie-x16.jpg) |



## Storage
- Non-volatile data storage.
- Flash drives usually refer to external storage devices.
- Smart phones and tablets use non-volatile flash storage due to their
  small form factor and to avoid malfunctions due to the moving parts
  found in spinning Hard Disk Drives (HDD).

# Types of storage devices  
![]({{site.baseurl}}/assets/netacad-it-essentials/storage-devices.jpg)

# Storage device interface  
- Internal storage devices often connect to the motherboard using SATA
  connections

| SATA1 | `1.5Gb/s` |
| SATA2 | `3.0Gb/s` |
| SATA3 | `6.0Gb/s` |

- PATA: legacy internal drive connections: IDE, EIDE

# Magnetic media storage  
- HDD
  - High storage capacity (GB - TB)  
  - Mechanical, moving parts  
  - Speed measured in RPM: `5,400`, **`7,200`**, **`10,000`**, `15,000`
  - Form factors: 
    - `3.5in`: standard
    - `2.5in`: mobile devices
    - `1.8in`: obsolete

![]({{site.baseurl}}/assets/netacad-it-essentials/storage-hdd-form-factors.jpg)

- Tape drive
  - tape backups still used in enterprise

![]({{site.baseurl}}/assets/netacad-it-essentials/storage-magnetic-tape-drive.jpg)

# Semiconductor storage: SSD
- Uses semiconductor flash memory
- Less capacity than HDDs (fewer TBs)
- No moving parts, more reliable, no noise, no wear, less heat
- Much faster than HDDs
- Form factors:
  - disk drive form factors
  - expansion cards
  - mSATA or M.2 modules

![]({{site.baseurl}}/assets/netacad-it-essentials/storage-ssd-form-factors.jpg)

![]({{site.baseurl}}/assets/netacad-it-essentials/storage-device-form-factors.jpg)

# SATA3 vs NVMe vs M.2
Reference: 
- [SATA 3 vs M.2 vs
  NVMe](https://www.online-tech-tips.com/computer-tips/sata-3-vs-m-2-vs-nvme-overview-and-comparison/)
  (online tech tips)

**Summary:**  
- M.2: A slimmer **form factor** for storage drives
- NVMe: a **protocol** that lets data be read and written via PCI-ez
- SATA 3: an older **protocol** that is typically not as fast as NVMe


| SATA vs NVMe             | two **protocols** to read and write data on a drive                                                  |
| SATA 3                   | connect data cable and power cable directly into motherboard and SSD                             |
| NVMe                     | data read straight from PCIe slot<br>faster than SATA 3<br>drive draws power through motherboard |
| M.2                      | physical **form factor** of a drive                                                                  |
| M.2 with SATA connection | ![]({{site.baseurl}}/assets/netacad-it-essentials/samsung-nvme-m2-drive.jpg)                     |
| M.2 with NVMe connection | ![]({{site.baseurl}}/assets/netacad-it-essentials/samsung-sata-m2-drive.jpg)                                                                                                 |



# SSHD
Solid-State Hybrid Drives

# Optical storage devices

| CD-ROM   | read-only, pre-recorded                              | `700MB`                                       |
| CD-R     | can be recorded one time                             |                                               |
| CD-RW    | rewritable: can be recorded, erased, and re-recorded |                                               |
| DVD-ROM  | read-only, pre-recorded                              | `4.7GB` (single-layer)<br>`8.5GB`(dual-layer) |
| DVD-RAM  | rewritable: can be recorded, erased, and re-recorded |                                               |
| DVD+/-R  | can be recorded one time                             |                                               |
| DVD+/-RW | rewritable: can be recorded, erased, and re-recorded |                                               |
| BD-ROM   | read-only, pre-recorded                              | `25GB` (single-layer)<br>`50GB` (dual-layer)  |
| BD-R     | can be recorded one time                             |                                               |
| BD-RE    | rewritable: can be recorded, erased, and re-recorded |                                               |

![]({{site.baseurl}}/assets/netacad-it-essentials/optical-drive-capabilities.jpg)
![]({{site.baseurl}}/assets/netacad-it-essentials/drive-bay-width.jpg)

# Media cards

| Secure Digital (SD) | cameras, MP3 players, laptops<br>up to `2TB`                                                                                           |
| MicroSD             | smartphones and tables                                                                                                                 |
| MiniSD              | mobile phones                                                                                                                          |
| CompactFlash        | video cameras<br>older<br>high-speed, high-capacity                                                                                    |
| Memory stick        | proprietaty flash memory<br>cameras, MP3 players, hand-held video game systems, mobile phones, cameras, and other portable electronics |
| xD/Picture Card     | was used in some digital cameras                                                                                                                                       |

![]({{site.baseurl}}/assets/netacad-it-essentials/common-media-cards.jpg)

# Monitors
- LCD
- LED
- OLED
- cut-off switch

## RAID


References: 
- [RAID animated](https://www.youtube.com/watch?v=U-OCdTeZLac) (PowerCert)

RAID: Redundant Array of Inexpensive/Independent Drives

Properties of RAID:
- availability
- reliability
- capacity
- redundancy
- performance

| striping      | distributes data across multiple drives              |
| mirroring     | duplicates data on one or more drives                |
| parity        | provides basic error checking and fault tolerance    |
| double parity | provides fault tolerance for up to two failed drives |

# RAID levels

| level    | min. &#35; of drives | features                  | advantages                                  | disadvantages           |
| 0        | 2                   | striping                  | performance<br>capacity                     | single-point of failure |
| 1        | 2                   | mirroring                 | performance<br>reliability                  | reduced capacity        |
| 5        | 3                   | striping w/ parity        | performance<br>reliability<br>capacity      | time-consuming rebuild  |
| 6        | 3                   | striping w/ double parity | two failed drives                           | time-consuming rebuild  |
| 10 (0+1) | 4                   | mirroring &amp; striping  | performance<br>capacity<br>high reliability | reduced capacity        |




## Ports, cables, adapters
Links:
- [Types of computer ports and their
  functions](https://www.skillonpage.com/types-of-computer-ports-and-their-functions/)
  (skillonpage.com)
- [Basic computer ports and
  connectors](https://greatmike.com/basic-computer-ports-and-connections/)
  (greatmike.com)
![]({{site.baseurl}}/assets/netacad-it-essentials/computer-ports-from-great-mike.jpg)
- [IWATSCBX - Computer Basics Course: Input and output](http://iwats.ecsquest.info/CBX/io4.php.htm)
![]({{site.baseurl}}/assets/netacad-it-essentials/ports-mb9.gif)
![]({{site.baseurl}}/assets/netacad-it-essentials/ports-mac.gif)
![]({{site.baseurl}}/assets/netacad-it-essentials/ports-video.jpg)

# Video ports and cables

| DVI                 | video, digital and analog                                                     | ![]({{site.baseurl}}/assets/netacad-it-essentials/video-ports-and-cables-dvi.jpg)                 |
| VGA                 | video, analog (`3` rows, `15` pins)                                    | ![]({{site.baseurl}}/assets/netacad-it-essentials/video-ports-and-cables-vga.jpg)                 |
| RCA                 | audio or video                                                         | ![]({{site.baseurl}}/assets/netacad-it-essentials/video-ports-and-cables-rca.jpg)                 |
| DisplayPort         | video, audio, high end                                                 | ![]({{site.baseurl}}/assets/netacad-it-essentials/video-ports-and-cables-displayport.jpg)         |
| HDMI                | high definition TV<br>computers                                        | ![]({{site.baseurl}}/assets/netacad-it-essentials/video-ports-and-cables-hdmi.jpg)                |
| Thunderbolt 1 and 2 | high-speed connection of peripherals                                   | ![]({{site.baseurl}}/assets/netacad-it-essentials/video-ports-and-cables-thunderbolt-1-and-2.jpg) |
| Thunderbolt 3       | `2x` bandwidth as Thunderbolt 2<br>4K<br> uses same connector as USB-C | ![]({{site.baseurl}}/assets/netacad-it-essentials/video-ports-and-cables-thunderbolt-3.jpg)       |
| S-video             |                                                                        | ![]({{site.baseurl}}/assets/netacad-it-essentials/s-video.jpg)                                    |
|                     |                                                                        |                                                                                                   |

# Other ports and cables

| PS/2           | mini-DIN<br>mouse (green)<br>keyboard (purple)             | ![]({{site.baseurl}}/assets/netacad-it-essentials/other-ports-and-cables-ps2.jpg)                            |
| audio and game |                                                            | ![]({{site.baseurl}}/assets/netacad-it-essentials/other-ports-and-cables-audio-and-game.jpg)                 |
| network        | RJ-45<br>(cat4+ cables)                                    | ![]({{site.baseurl}}/assets/netacad-it-essentials/other-ports-and-cables-network.jpg)                        |
| SATA           | connects SATA devices to SATA interfaces<br>L-shaped slots | ![]({{site.baseurl}}/assets/netacad-it-essentials/other-ports-and-cables-sata.jpg)                           |
| IDE            | `34` pins (floppy)<br>`40` pins (hard/optical drives)      | ![]({{site.baseurl}}/assets/netacad-it-essentials/other-ports-and-cables-ide.jpg)                            |
| USB            | hot swappable                                              | ![]({{site.baseurl}}/assets/netacad-it-essentials/other-ports-and-cables-usb.jpg)                            |
| parallel       | printer port                                               | ![]({{site.baseurl}}/assets/netacad-it-essentials/other-ports-and-cables-parallel-computer-printer-port.jpg) |
| serial         |                                                            | ![]({{site.baseurl}}/assets/netacad-it-essentials/other-ports-and-cables-serial-port.jpg)                    |

# USB connectors

| USB motherboard connectors | ![]({{site.baseurl}}/assets/netacad-it-essentials/usb-connector-motherboard.jpg) |
| internal USB connector     | ![]({{site.baseurl}}/assets/netacad-it-essentials/usb-connector-internal.jpg)    |



# Adapters and converters  

| adapter   | physically connects one technology to another          |
| converter | also translates signals from one technology to another |

| DVI to VGA      | adapter   | ![]({{site.baseurl}}/assets/netacad-it-essentials/adapters-and-converters-dvi-to-vga.jpg)            |
| USB to Ethernet | converter | ![]({{site.baseurl}}/assets/netacad-it-essentials/adapters-and-converters-usb-to-ethernet.jpg)       |
| USB to PS/2     | adpater   | ![]({{site.baseurl}}/assets/netacad-it-essentials/adapters-and-converters-usb-to-ps2.jpg)            |
| DVI to HDMI     | adapter   | ![]({{site.baseurl}}/assets/netacad-it-essentials/adapters-and-converters-dvi-to-hdmi.jpg)           |
| Molex to STA    | adapter   | ![]({{site.baseurl}}/assets/netacad-it-essentials/adapters-and-converters-molex-to-sata.jpg)         |
| HDMI to VGA     | converter | ![]({{site.baseurl}}/assets/netacad-it-essentials/adapters-and-converters-hdmi-to-vga-converter.jpg) |


More examples:  
![]({{site.baseurl}}/assets/netacad-it-essentials/cables-and-connectors-examples.jpg)

# KVM switch
Used to control more than one computer while using a single keyboard,
monitor, and mouse  
![]({{site.baseurl}}/assets/netacad-it-essentials/kvm-switch.jpg)

## Technician's toolkit
- anti-static wrist strap and mat
- compressed air
- extraction tool
- Phillips head screwdriver
- Torx driver
- cable tester
- crimpers

![]({{site.baseurl}}/assets/netacad-it-essentials/technician-toolkit.jpg)

## Computer disassembly
1. power off and disconnect power supply
2. disconnect mouse and keyboard
3. remove case screws
4. remove SATA power and data cables
5. remove hard drive
6. remove optical drive
7. remove adapter card
8. remover power supply
9. remove front pannel connectors
10. remove RAM

# Network cable tools

![]({{site.baseurl}}/assets/netacad-it-essentials/tool-technician-toolkit.jpg)

| wire cutter/side cutter | ![]({{site.baseurl}}/assets/netacad-it-essentials/tool-wire-cutter.jpg)              |
| wire stripper           | ![]({{site.baseurl}}/assets/netacad-it-essentials/tool-wire-stripper.jpg)            |
| cable connector         |                                                                                      |
| punch down tool         | ![]({{site.baseurl}}/assets/netacad-it-essentials/tool-punch-down-tool.jpg)          |
| network cable tester    | ![]({{site.baseurl}}/assets/netacad-it-essentials/tool-cable-tester.jpg)             |
| crimper                 | ![]({{site.baseurl}}/assets/netacad-it-essentials/tool-crimper.jpg)                  |
| toner and probe         | ![]({{site.baseurl}}/assets/netacad-it-essentials/tool-tone-generator-and-probe.jpg) |
| multimeter              | ![]({{site.baseurl}}/assets/netacad-it-essentials/tool-multimeter.jpg)               |
| loopback adpater/plug   | ![]({{site.baseurl}}/assets/netacad-it-essentials/adapter-loopback.jpg)              |
| wifi analyzer           | ![]({{site.baseurl}}/assets/netacad-it-essentials/tool-wifi-analyzer.jpg)            |



# Cable types



![]({{site.baseurl}}/assets/netacad-it-essentials/network-cables-examples.jpg)

![]({{site.baseurl}}/assets/netacad-it-essentials/network-cables-fiber-optic-multimode.jpg)

| twisted-pair (unshielded)                             | ![]({{site.baseurl}}/assets/netacad-it-essentials/network-cables-twisted-pair-unshielded.jpg)                |
| twisted-pair (shielded)                               | ![]({{site.baseurl}}/assets/netacad-it-essentials/network-cables-twisted-pair-shielded.jpg)                  |
| coaxial                                               | ![]({{site.baseurl}}/assets/netacad-it-essentials/network-cables-coaxial-cable.jpg)                          |
| fiber optic                                           | ![]({{site.baseurl}}/assets/netacad-it-essentials/network-cables-fiber-optic-diagram.jpg)                    |
| fiber optic<br>cross section                          | ![]({{site.baseurl}}/assets/netacad-it-essentials/network-cables-fiber-optic-cross-section.jpg)              |
| fiber optic<br>single-mode                            | ![]({{site.baseurl}}/assets/netacad-it-essentials/network-cables-fiber-optic-single-mode.jpg)                |
| fiber optic<br>multi-mode                             | ![]({{site.baseurl}}/assets/netacad-it-essentials/network-cables-fiber-optic-multimode.jpg)                  |

# Ethernet over twisted pair
- 10BASE-T
- 100BASE-TX (Fast Ethernet)
- 1000BASE-T (Gigabit Ethernet)
- 2.5GBASE-T

[Unshielded twisted pair (UTP) - cat 1 to cat5, 5e, cat6 &
  cat7](http://www.firewall.cx/networking-topics/cabling-utp-fibre/112-network-cabling-utp.html) (firewall.cx)


![]({{site.baseurl}}/assets/netacad-it-essentials/cabling-utp-categories.png)

See [different types of ethernet cables
explained](https://www.digitaltrends.com/computing/different-types-of-ethernet-cables-explained/
" digital trends")

**NEEDS CHECKING**

| category | shielding                 | max transmission speed<br>at 100meters | max bandwidth |
| cat3     | unshielded                | 10 Mbps                                | 16 MHz        |
| cat5     | unshielded                | 10/100 Mbps                            | 100 MHz       |
| cat5e    | unshielded                | 1,000 Mbps                             | 100 MHz       |
| cat6     | shielded or<br>unshielded | 1,000 Mbps                             | 250 MHz       |
| cat6a    | shielded                  | 10 Gbps                                | 500           |
| cat7     | shielded                  | 10,000 Mbps                            | 600 MHz       |
| cat7a    | shielded                  | 10,000Mbps                             | 1,000 MHz     |
|          |                           |                                        |               |

From [Professor Messer's 220-901 video
playlist](https://www.youtube.com/watch?v=RWCiqUm34Bc&list=PLG49S3nxzAnmlC1ZsppuM7yleDuYCMHrv&index=44&t=05m18s
"Professor Messer"):

| cable<br>category    | ethernet<br>standard     | maximum<br>distance | obsolete |
| cat3                 | 10BASE-T                 | 100 meters          | ------   |
| cat5                 | 100BASE-TX<br>1000BASE-T | 100 meters          | current  |
| cat5e<br>(enhanced)  | 100BASE-TX<br>1000BASE-T | 100 meters          |          |
| cat6                 | 10GBASE-T                | 37-55 meters        |          |
| cat6a<br>(augmented) | 10GBASE-T                | 100 meters          |          |
| cat7*<br>(shielded)  | 10GBASE-T                | 100 meters          |          |
|                      |                          |                     |          |


# Fiber standards

| FX or SX in the name | light travels in one direction   | use e.g. duplex multimode LC connector<br> |
| BX in the name                  | light travels in both directions | WDM (wave division multiplexing)           |


# Fiber optic connectors


| **straight tip** connector             | ![]({{site.baseurl}}/assets/netacad-it-essentials/network-cables-fiber-optic-connector-straight-tip.jpg)     |
| **subscriber** connector               | ![]({{site.baseurl}}/assets/netacad-it-essentials/network-cables-fiber-optic-connector-subscriber.jpg)       |
| **Lucent connector simplex connector** | ![]({{site.baseurl}}/assets/netacad-it-essentials/network-cables-fiber-optic-connector-lucent.jpg)           |
| **duplex multimode LC connector**      | ![]({{site.baseurl}}/assets/netacad-it-essentials/network-cables-fiber-optic-connector-duplex-multimode.jpg) |



# BIOS
- performs:
  - boot computer
  - perform Power-On Self-Testing (POST)
- configuration stored on CMOS (nor more commonly flash memory)
- possible modifications
  - boot order
  - enabling or disabling of devices

![]({{site.baseurl}}/assets/netacad-it-essentials/cmos-battery.jpg)


## Network addressing

### Public and private addresses

<table>
  <tr>
    <th>public address</th>
    <th>private address</th>
  </tr>
  <tr>
    <td>
	<ul>
	<li>usabe on public and private networks</li>
	<li>required to access Internet</li>
	<li>must be unique</li>
	<li>assigned by IANA/RIR</li>
  </ul>
  </td>
  <td>
  <ul>
  <li>usable only on private networks</li>
  <li>can be translated too access Internet</li>
  <li>cannot be routed through the internet</li>
  <li>administrator can assign</li>
  </ul>
  </td>
  </tr>  
</table>  

_References_:  
- [video by IT free training](https://www.youtube.com/watch?v=WsgK08FyoRk)

### Classful network addressing

| class | leading<br>bit(s) | public range  | private range     | private range<br>(CIDR) |
|-------|-------------------|---------------|-------------------|-------------------------|
| A     | 0                 | 1 - 126 (127) | 10                | 10.0.0.0/8              |
| B     | 10                | 128 - 191     | 172.16 - 172.31   | 172.16.0.0/12           |
| C     | 110               | 192 - 223     | 192.168 - 192.168 | 192.168.0.0/16          |
| D     | 1110              | 224 - 239     |                   |                         |
| E     | 1111              | 240 - 255     |                   |                         |

IPv6 site local: `fc::0/7`: 

### Link-local addresses:  
APIPA: Automatic Private IP Addressing  
Uses ARP to confirm address isn't currently in use

| version | slash/CIDR block<br>notation | range                                                                           |
| IPv4    | 169.254.0.0/16               | 169.254<br>reserved: 169.254.0, 169.254.255<br>effective: 169.254.1-169.254.254 |
| IPv6    | fe80::/10                    | fe80:: to febf::                                                                |

### Network Address Translation  
NAT: Network Address Translation  
PAT: Port Address Translation

| NAT                 | alleviates the depletion of IPv4 address space by allowing multiple hosts on the same private LAN to share a single public IP  address          |
|                     | hides internal IP addresses by modifying the IP address information in IP packet headers while it is in transit across a traffic routing device |
| DNAT<br>Dynamic NAT | provides a mapping between an individual private IP address and any of the IP addresses belonging to the available public IP address pool       |
| SNAT<br>Static NAT  | provides a permanent mapping between an individual private IP address and a public IP address                                                   |
| PAT                 | takes a combination of a private IP address and a port number, then binds them with the corresponding public IP address and port information    |
|                     |                                                                                                                                                 |


	


# TCP and UDP

| TCP                   | UDP               |
| connection-oriented   | connection-less   |
| reliable              | unreliable        |
| order; retransmission | no acknowledgment |

Ports:
- between 0 and 65,535
- server side: non-ephemeral port
- client side: ephemeral port, determined in real-time by client
  (e.g. one for each tab on browser)
- TCP ports and UDP ports separate




## Types of networks

| PAN/WPAN | Private Area Network/Wireless PAN | connects devices in close proximity to user, using e.g. Bluetooth         |
| LAN      | Local Area Network                | connects devices using wire cables in a small geographical area           |
| VLAN     | Virtual LAN                       | allows to segment ports on a single switch if it were multiple switches   |
| WLAN     | Wireless LAN                      | LAN where devices are connected wirelessly                                |
| WMN      | Wireless Mesh Network             | uses access points to extend WLAN                                         |
| MAN      | Metropolitan Area Network         | network spanning across a large campus or city<br>wireless or fiber optic |
| WAN/WWAN | Wide Area Network/Wireless WAN    | connects multiple networks that are geographically separated              |
| VPN      | Virtual Private Network           | used to connect securely over an insecure network                         |


# Internet connection types

| DSL      | modem connects user's network to digital infrastructure of phone company         |
|          | uses telephone lines, dedicated bandwidth                                        |
| cable    | modem connects user's network to cable service provider                          |
|          | uses cabling that carries TV signals, shared bandwdith                           |
| fiber    | used in backbone networks, large enterprise environments, and large data centers |
| cellular | uses towers distributed throughout user's                                        |



Connector types:
- fiber
- copper connectors:
 - RJ11 (6P2C): telephone
 - RJ45 (8P8C): ethernet
- BNC connectors
- F-connectors (cable television, cable modem)


Fiber
- transmission by light
- no RF signal: difficult to monitor or tap
- signal slow to degrade
- immune to interference

| single-mode       | multi-mode         |
| short range (2km) | long range (100km) |
| LED               | laser              |

# Cables
- fiber
- copper
- plenum
- coaxial




## Wireless communication and networking

- cellular
- Wi-Fi
- Bluetooth
- Radio Frequency IDentification (RFID)
- Near Field Communication (NFC)
- smart home standards (IEEE 802.15: Low Rate WPAN)
  - Zigbee (802.15.4)
  - Z-Wave


References:
- [Mansi Pruthi, 1G, 2G, 3G, 4G, 5G](https://mansipruthi.wordpress.com/2015/09/02/1g2g3g4g-and-5g/)
- [Low-power wireless links let the IoT
  proliferate](https://www.analogictips.com/low-power-wireless-links-let-the-iot-proliferate/)
  (Analog IC Tips)

# Cellular (1G to 5G)
![]({{site.baseurl}}/assets/netacad-it-essentials/compare-1g-2g-3g-4g-5g.jpg)


Long Term Evolution (LTE) is a wireless communications standard for
mobile devices and wireless hotspots. LTE is much faster than the
older generation of 2G and 3G cellular networks. Both LTE and its
later upgrade, LTE-Advanced (LTE-A), are often marketed as 4G
standards.



## IEEE 802.11 WLAN standards
References:  
- Muhammad Taha Jilani, *A Security Framework for Wireless Body Area
  Network Based Smart Healthcare System*
  [(link)](https://www.researchgate.net/publication/317425760_A_Security_Framework_for_Wireless_Body_Area_Network_Based_Smart_Healthcare_System)
- [Wi-Fi standard
  evolution](https://www.grandmetric.com/2018/05/29/wi-fi-standards-evolution/)
  (Grand Metric)
- [Networkustad](https://networkustad.com/tag/802-11-standards-chart/)

**_NEEDS CHECKING_**

![]({{site.baseurl}}/assets/netacad-it-essentials/802-11-comparison-of-variants-of-wifi-standards.png)

Incorporating data from [Professor
Messer](https://www.youtube.com/watch?v=dORMbdIMd5s&list=PLG49S3nxzAnmlC1ZsppuM7yleDuYCMHrv&index=50):

| standard              | frequency  | bandwidth               | maximum<br>allowable<br>streams | maximum<br>theoretical<br>throughput<br>per stream | maximum<br>theoretical<br>throughput<br>total | wireless<br>adapter<br>type |
| 802.11a               | 5 GHz      | 20 MHz                  | 1                               | 54 Mbps                                            | 54 Mbps                                       | mini-PCI, mini-PCIe         |
| 802.11b               | 2.4 GHz    | 22 MHz                  | 1                               | 11 Mbps                                            | 11 Mbps                                       | mini-PCI, mini-PCIe         |
| 802.11g               | 2.4 GHz    | 20 MHz                  | 1                               | 54 Mbps                                            | 54 Mbps                                       | mini-PCI, mini-PCIe         |
| 802.11n<br>(MIMO)     | 2.4, 5 GHz | 24, 40 MHz              | 4                               | 150 Mbps                                           | 600 Mbps                                      | mini-PCIe                   |
| 802.11ac<br>(MU-MIMO) | 5 GHz      | 20, 40,<br> 80, 160 MHz | 8                               | 866.7 Mbps                                         | 6,934 Mbps                                    | mini-PCIe                            |

- MIMO: Multiple Input / Multiple 
  - a wireless technology that allows for significant increase in data
  throughput due to the use of multiple antennas and multiple data
  streams
- MU-MIMO: Multi-User MIMO

Bottom line:  

| legacy  |          |
| current | 802.11ac |
|         |          |

# Bluetooth

Short-range wireless interconnetion of mobile phones, computers and
other electronic diveces
- physical level: radio frequency standard
- protocol level: Bluetooth pairing

|         | max. permitted power | approximate distance |
| class 1 | 100 mW               | ~330 ft (100 m)      |
| class 2 | 2.5 mW               | ~30 ft (10 m)        |
| class 3 | 1 mW                 | ~3 ft (1 m)          |

![]({{site.baseurl}}/assets/netacad-it-essentials/bluetooth-specifications-or-features.jpg)




# Wireless encryption
- WEP: RC4 stream cipher; 64- and 128-bit key size
- WPA: RC4 with TKIP (temporal key integrity protocol)
- WPA2 (2004): AES with CCMP: counter Mode with cipher block chaining
  message authentication code protocol
- WPS: Wi-Fi Protected Setup (WPS) simplifies the configuration of new
  wireless networks by enabling non-technical users to easily set up
  new networks, configure network security settings and add new
  devices to an existing network. However, due to its known security
  vulnerabilities, WPS is not recommended and should be disabled.

# Wireless site survey

| passive   | listens to WLAN traffic to detect active access points, measure signal strength and noise level                                                 |
| active    | wireless adapter is associated with one or several access points to measure round-trip time, throughput rates, packet loss, and retransmissions |
| preditive | a model of the RF environment is created using simulation tools                                                                                 |
|           |                                                                                                                                                 |

## The OSI and the TCP/IP models

> **P**lease **D**o **N**ot **T**hrow **S**ausage **P**izza **A**way

References: 
- [Networking models and data
flow](http://ptgmedia.pearsoncmg.com/imprint_downloads/informit/learninglabs/9780134213736/)
(The Pearson Knowledge manual)

![]({{site.baseurl}}/assets/netacad-it-essentials/model-osi-tcp-ip.jpg)

## Ethernet
# Ethernet standards
Reference:
- [The Pearson General Knowledge Manual](http://ptgmedia.pearsoncmg.com/imprint_downloads/informit/learninglabs/9780134213736/ch29.html#ch29tab01)

![]({{site.baseurl}}/assets/netacad-it-essentials/ethernet-standards.jpg)

## Networking devices
Host/end devices vs intermediary devices

# Intermediary devices

| repeater (extender)        | regenerates weak signals                                                                                                           |
| hub                        | (**legacy**) connects devices in a LAN<br>- receives data one port, sends to all other ports<br>- does not segment network traffic |
| bridge                     | (**legacy**) divides LAN into segments                                                                                             |
|                            | forwarding decisions made in hardware<br>fewer connections than switch<br>older and less effective                                 |
| switch                     | microsegments LAN<br>filters and segments traffic by sending data only to intended devices                                         |
|                            | forwarding decisions made in hardware                                                                                              |
| wireless access point (AP) | provides network access to wireless devices                                                                                        |
| router                     | connects networks                                                                                                                  |

| switch            | connects multiple devices to the network                                                            |
| router            | forwards traffic between networks                                                                   |
| wireless router   | connects multiple wireless devices to the network and may include a switch to connected wired hosts |
| access point (AP) | connects to wireless router and is used to extend the reach of a wireless network                   |
| modem             | connects a home or small office to the internet                                                     |
|                   |                                                                                                     |


**Switches vs bridges**

| bridge                                | switch                         |
| forwarding decisions made in software | decisions made in hardware     |
| connects fewer network segments       | connects more network segments |
| older and less effective              | newer and more effective       |


**Routers vs switches**

| switches | use MAC addresses | to forward traffic | **within** a  network |
| switch   | connect           | computers          | within a network      |
| routers  | use IP addresses  | to forward traffic | to **other** networks |
| routers  | connect           | networks           | to other networks     |

proxy: acts as an intermediary between a network host and the Internet

Wireless router = router + wireless access point

- hub has no routing table or intelligence on where to send
  information and broadcasts all network data across each connection

UPNP: 
- a type of architecture that simplifies networking by allowing
  devices to dynamically join a network, autoconfigure, and learn
  about the presence and capabilities of other devices
- zero-configuration networking

## Security devices


| firewall                   | placed between internal and external networks, monitors, controls, filters incoming and outgoing traffic        |
| IDS                        | copies traffic and forwards for evaluation                                                                      |
| IPS                        | installed inline, evaluates traffic before forwarding to destination                                            |
| UTM                        | - IDS and IPS functionalities<br>- stateful firewall services<br>- zero-day protection<br>-DoS, DDoS protection |
| Endpoint Management Server | centralizes views of all devices on network for administration with single interface                            |

- packet-filtering firewall
- stateful inspection firewall
- proxy firewall
- NGFW(?)
- personal firewall

# Facts and features

| port forwarding | allows a server with a private IP address to handle requests from an outside (public) network                                                   |
| port triggering | a router configuration feature that allows to open an inbound port based on the outbound requests made by hosts placed inside a private network |
|                 |                                                                                                                                                 |

## Protocols

| files | FTP, SFTP, SCP, WebDAV |
|       |                        |

From [Professor
Messer](https://www.youtube.com/watch?v=MTPTow2PTfY&list=PLG49S3nxzAnmlC1ZsppuM7yleDuYCMHrv&index=48&t=7m35s):

| Post Office Protocol v3             | POP3  | TCP/110 | receive email into an email client                               |
| Internet Message Access Protocol v4 | IMAP4 | TCP/143 | newer email client protocol                                      |
| Simple Mail Transfer Protocol       | SMTP  | TCP/25  | transfer email between servers<br>ASCII for text, MIME otherwise |


## Software utilities  

| `ping`     | tests reachability of a host on an IP network                                                    |
| `tracert`  | measures speed and route data takes to destination server                                        |
| `ipconfig` | displays TCP/IP network configuration, refreshes DHCP and DNS settings                           |
| `netstat`  | displays network connections for TCP, routing tables, etc.                                       |
| `nslookup` | queries DNS records                                                                              |
| `eventvwr` | launches Windows Event Viewer, showing logs of application and system messages, errors, warnings |




## Troubleshooting
Causes:
- Hardware
- Software
- Network


## To do
- docking stations vs port replicators  
- phablets vs smatphones vs PDA/handheld pc
- https://www.houkconsulting.com/2018/11/understanding-usb-cables-ports/
  - lightning (Apple)
  - USB standards
- IMAP vs POP3
  - POP3: port 110
  - POP3S: SSL, TLS, port 995
  - IMAP: port 143
  - IMAPS: SSL, TLS, port 993
- well known ports
- MIME, Secure MIME
- POP
- cloud-based email services
- SSID vs IMEI
- SMTP
- Apple connectors [identify the ports on your
  mac](https://support.apple.com/en-us/HT201736)
- LDAP
- NetBIOS: [How netbios name resolution really
  works](https://www.techrepublic.com/article/how-netbios-name-resolution-really-works/)
- [NetBIOS name](https://networkencyclopedia.com/netbios-name/
  "netbios names")
- WINS: Windows Internet Name Service: Microsoft's implementation of
  NetBIOS name service (NBNS); 
  - Windows: "Windows Internet Name Service (WINS) is ."
  - wikipedia:
    - "WINS is to NetBIOS names what DNS is to domain names — a central
      mapping of host names to network addresses."
    - "This is the predecessor to DNS and has been deprecated by Microsoft."
- NBT: NetBIOS over TCP/IP
- NBF: NetBIOS Frames
- SMB: Server Message Block
- CIFS: Common Internet File System
- SMB/CIFS: a network communication protocol for providing shared
  access to files, printers, and serial ports between nodes on a
  network.  Most usage of SMB involves computers running Microsoft
  Windows, where it was known as "Microsoft Windows Network" before
  the introduction of Active Directory.
- file services:
  - SMB
  - NFS (network file system)
  - FTP (file transfer protocol)
- the FTP protocol uses a separate connection for the file transfers
  and directory listings; [link](https://winscp.net/eng/docs/ftp_modes
  "ftp modes")
- [FTP
  port](https://www.ntchosting.com/encyclopedia/ftp/ftp-port-connection/)
- digitizer
- hotspot
- plenum cables (fire-retardant)
- [punch down
  tool](https://www.computerhope.com/jargon/p/punch-down-tool.htm):
  connects telecommunications and network wires to a patch panel,
  punch down block, keystone module, or surface mount box
- parity checking will halt a process when discovering an error
- crossover cable (e.g. Ethernet crossover cable)
- loopback plug
- domain controller (DC): a server computer that responds to security
  authentication requests within a computer domain
- domain: grouping of multiple "private" computer networks or hosts
- syslog
- 10BASET, 100BASET, 1000BASET
- WAP, WEP, WPA (confusion?)
- access control: rights vs permissions
- X.500
- UPNP
- T1
- paging to disk
- mapping a drive
- disk clean up
- print spooler
- printer queue
- mobile device synchronization
- patch panel
- injector (power over ethernet)
- PC card (PCMCIA)
- Express Cards
- flash vs SSD
- soft reset vs hard reset
- CPU: Processors run calculations using threads and each processor
  core can only handle one thread at a time. Additional cores improve
  processor performance by enabling multiple threads to be run
  simultaneously. When an application uses multiple threads on a
  single core processor the threads do not execute simultaneously
  limiting performance.
- Dynamic Host Configuration Protocol (DHCP) allows for static
  allocation of an IP address based on an IP-to-MAC address mapping.
- WiMAX: long-distance line-of-sight Internet service(?)
- PSTN: Public Switched Telephone Network
- ISDN: Integrated Services Digital Network
  - enables simultaneous digital transmission of voice, video, data,
    and other network services over a PSTN
- Tethering: Examples of tethering methods used in mobile Internet
  connection sharing include: Bluetooth, Wi-Fi, USB cable
- [Overclockers.net](https://www.overclockers.com/forums/showthread.php/662516-Is-a-Cat5e-patch-the-same-as-a-straight-through)
  - A 'patch cable' is a term from structured cabling, or the cabling
    jargon that installation techs use about the design of a computer
    network infrastructure in a building. For example, the cable at
    your work that goes from your computer to a wall jack is called
    the 'patch cable'.
  - Straight-through describes the wiring configuration within your
    cable. If the cable is straight-through then it has the same
    wiring configuration on both ends (T568A-T568A or T568B-T568B).
- 802.3: defines the physical layer and data link layer's media access
  control (MAC) of wired Ethernet. This is generally a local area
  network (LAN) technology with some wide area network (WAN)
  applications. Physical connections are made between nodes and/or
  infrastructure devices (hubs, switches, routers) by various types of
  copper or fiber cable.
- A standardized motherboard specification (including its dimensions,
  supported power supply types, and layout of components) is known as
  the motherboard's form factor.
- Trusted Platform Module (TPM) – This is a chip designed to secure
  hardware by storing encryption keys, digital certificates,
  passwords, and data. TPM is used by Windows to support BitLocker
  full-disk encryption.
[Bluetooth stack](https://flylib.com/books/en/4.215.1.116/1/)


## References  
- [IT Free Training handouts](http://itfreetraining.com/handouts/)
- [IT essentials Chapter 1: intro to personal computer hardware](https://itexamanswers.net/essentials-v7-0-chapter-1-introduction-to-personal-computer-hardware.html)
- [IT essentials Chapter 2: PC assembly ](https://itexamanswers.net/essentials-v7-0-chapter-2-pc-assembly.html)
- [IT essentials Chapter 3: Advanced
computer hardware](https://itexamanswers.net/essentials-v7-0-chapter-3-advanced-computer-hardware.html)
- [IT essentials Chapter 5 networking concepts](https://itexamanswers.net/essentials-v7-0-chapter-5-networking-concepts.html)
- [IT essentials v6.0 Chapter 5: Windows installation](https://itexamanswers.net/it-essentials-v6-0-chapter-5-windows-installation.html)
- [IT Essentials  Chapter 7: laptops and other mobile devices](https://itexamanswers.net/essentials-v7-0-chapter-7-laptops-and-other-mobile-devices.html)
- [IT essentials Chapter 8: Printers](https://itexamanswers.net/essentials-v7-0-chapter-8-printers.html)
- [Intro to networks Chapter 4: network access](https://itexamanswers.net/introduction-to-networks-6-0-instructor-materials-chapter-4-network-access.html)
- [LGA vs PGA - CPU socket types explained](https://www.unboxingtreatment.com/2017/07/lga-pga-socket.html)
- [Integrated Technology eXtended](https://www.computerhope.com/jargon/i/itx.htm)
- [Difference between EPROM and EEPROM](https://techdifferences.com/difference-between-eprom-and-eeprom.html)
- [Difference between SIMM and DIMM](https://techdifferences.com/difference-between-simm-and-dimm.html)
- [Difference between L1 and L2 cache](https://www.differencebetween.com/difference-between-l1-and-vs-l2-cache/)
- [SSD interface comparison: PCI Express
vs SATA](https://www.overclock.net/forum/355-ssd/1489684-ssd-interface-comparison-pci-express-vs-sata.html)
- [Everything you need to know about the PCI Express](https://www.hardwaresecrets.com/everything-you-need-to-know-about-the-pci-express/2/)
- [SATA3 vs M.2 vs NVMe: overview and comparison](https://www.online-tech-tips.com/computer-tips/sata-3-vs-m-2-vs-nvme-overview-and-comparison/)
- [Difference between switch and router](https://pc.net/helpcenter/answers/difference_between_switch_and_router`)
- [PC.net glossary](https://pc.net/glossary/)
- [Port addressing translation (PAT)](https://searchnetworking.techtarget.com/definition/Port-Address-Translation-PAT)
- [Advantages of
  VLANs](https://library.netapp.com/ecmdocs/ECMP1401193/html/GUID-C9DA920B-F414-4017-8DD1-D77D7FD3CC8C.html)
- [Types of computer ports and their functions](https://www.skillonpage.com/types-of-computer-ports-and-their-functions/)
- [Cable modem vs DSL
  modem](http://iwats.ecsquest.info/CBX/io4.php.htm) (IWATS CBX
  Computer Basics Course)
- [What is this connector for?](http://support.antec.com/support/solutions/articles/1000140052-what-is-this-connector-for-)
- [DITEC: fundamentals in networking](https://www.slideshare.net/rasansamarasinghe/module-iv-50035635)
- [What are the main differences between LCD and
  OLED?](https://www.mvps.net/docs/what-are-the-main-differences-between-lcd-or-oled/) (mvps.net)
- [What is a laptop
  inverter?](https://www.wisegeek.com/what-is-a-laptop-inverter.htm) (wisegeek.com)
- [Increasing Laptop Functionality with Docking Stations or Port
  Replicators](https://www.burgesstechnologyservices.com/burgess-technology-blog/docking-stations-port-replicators/)
  (Burgess technology services)
- [Understanding the different types of USB cables and
  ports](https://www.houkconsulting.com/2018/11/understanding-usb-cables-ports/)
  (Houk Consulting)
- [WireShark wiki](https://wiki.wireshark.org/FrontPage "Wireshark wiki")
- [Email protocols (SiteGround)](https://www.siteground.com/tutorials/email/protocols-pop3-smtp-imap/ "email protocols")
- [TCP and UDP ports used by
  Apple](https://support.apple.com/en-gb/HT202944 "TCP and UDP ports
  used by Apple") 
- [For Thunderbolt and Lightning, USB-C is very, very frightening](https://www.theverge.com/2015/3/10/8181551/thunderbolt-lightning-usb-type-c-new-macbook "The Verge")
- [SATA and M.2 SSD FAQs](https://www.kingston.com/en/ssd/ssd-faq "Kingston")
- [What is the difference between a link local address and an IP
  address in the private address
  space?](https://superuser.com/questions/342149/what-is-the-difference-between-a-linkl-ocal-address-and-an-ip-address-in-the-pri
  "superuser")
- [NAT and firewall](https://www.youtube.com/watch?v=2llWuivdS7w "IBM Cloud")
- [Traceroute
  explained](https://help.fasthosts.co.uk/app/answers/detail/a_id/1550/~/traceroute-explained
  "fasthosts")
- [Network design concepts](http://students.mimuw.edu.pl/~zbyszek/sieci/CCNA4%20Sample.pdf)
- [FAT32 vs. NTFS](https://www.diffen.com/difference/FAT32_vs_NTFS)
- [Fundamentals of Operating
  Systems](http://www.missouricareereducation.org/doc/networking/Basic_InstrStrat1_Fund_OSs.pdf) (missouricareereducation.org)
- [Difference between adapter card and
expansion
card](https://forums.tomshardware.com/threads/difference-between-adapter-card-and-expansion-card.2124351/)
(Tom's hardware)
- [Twisted pair
  cable](https://www.sciencedirect.com/topics/computer-science/twisted-pair-cable
  " (Science Direct)")
- [RAID](https://www.prepressure.com/library/technology/raid) (prepressure.com)
- [What is an IDE
  cable?](https://www.lifewire.com/what-is-an-ide-cable-2625908)
  (lifewire)  
- [Common computer power supply
connectors](https://forum.digikey.com/t/common-computer-power-supply-connectors/328) (digikey)
- [Understanding USB and Thunbderbolt:
  Speed, connectors and
  functionality](https://www.tripplite.com/products/usb-connectivity-types-standards)
  (TrippLite)
- [What is the difference between DVI-A, DVI-D and
  DVI-I?](http://iogear.custhelp.com/app/answers/detail/a_id/2209/~/what-is-the-difference-between-dvi-a%2C-dvi-d-and-dvi-i%3F)
- 

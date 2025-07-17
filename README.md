# Zenith ZT-1 (also the ZT-10, ZT-11 and ZTX-1, ZTX-10, ZTX-11)

The Zenith ZT-1 was a device that came out around 1981 that looked like a keyboard. It was designed to be used by someone who wanted to connect to online services via the internal 300 baud modem without the need of a computer. You would connect a monochrome composite video monitor and interface with it via an internal menu structure held in ROM. The system uses an Intel 8031 MCU (this is a variant with 128 bytes of internal RAM but no internal ROM) as the main CPU, it has 8K of ROM on two 2732 ICs (dumped), 1K of SRAM (via two 2114 chips), a single 2Kx8 6116 SRAM likely used as video RAM and a 2K Chargen EPROM (2516.) An Intel CRTC is used to generate the video sync and timing. The system also has a NiCD battery that can leak which appears to be used to save phone numbers and settings to a single 2114 SRAM. (NEC D444C in this machine.)

This can be considered to be like a WebTV but from 1981.

## ZT-1/ZT-10/ZT-11 PSU

Beware of two tanatalum caps on the main PCB that can short, which will damage the external PSU.

```
DE9
1 Black --+ 15VAC (Black wire is fused, 3A 250V) 
2 N/C     | 0.66ohms
3 N/C     |
4 White --|---+ 11 ohmx
5 Green --|---+ Center tap of 31VAC
6 Brown --+   |
7 N/C         | 11 ohms
8 N/C         |
9 Red --------+
```
Fuse is inside the PSU, and you must hammer it to open it.

Current draw on 15VAC is about 850ma while running. Forms ~12VDC after bridge rectifier inside terminal.

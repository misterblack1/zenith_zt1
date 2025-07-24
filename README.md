# Zenith ZT-1 (also the ZT-10, ZT-11 and ZTX-1, ZTX-10, ZTX-11)

The Zenith ZT-1 was a device that came out around 1981 that looked like a keyboard. It was designed to be used by someone who wanted to connect to online services via the internal 300 baud modem without the need of a computer. You would connect a monochrome composite video monitor and interface with it via an internal menu structure held in ROM. The system uses an Intel 8031 MCU (this is a variant with 128 bytes of internal RAM but no internal ROM) as the main CPU, it has 8K of ROM on two 2732 ICs (dumped), 1K of SRAM (via two 2114 chips), a single 2Kx8 6116 SRAM likely used as video RAM and a 2K Chargen EPROM (2516.) An Intel CRTC is used to generate the video sync and timing. The system also has a NiCD battery that can leak which appears to be used to save phone numbers and settings to a single 2114 SRAM. (NEC D444C in this machine.)

This can be considered to be like a WebTV but from 1981.

## ROMs

I dumped the ROMs from my ZT-1 (444-187 U114 ROM 2732.bin & 444-188 U113 ROM 2732.bin) and Sark has dumped the ROMs from his ZT-11 (ztx-11_U113 2732.bin & ztx-11_U114 2732.bin)

## Differences between machines

The ZT-1 has a 300 baud modem. The ZT-10 has a RS232 serial port but no modem. The ZT-11 has both the modem and the serial port. The Serial board in the ZT-11 (and possibly the ZT-10) seems to be an afterthought, with flying leads bodged onto four points. (See photos) This board has two ICs that convert TTL serial to RS232 (and vice verse) and also it has a 555 timer that is likely to create a negative voltage rail that RS232 would use. I theorize any cheap TTL to RS232 adapter (with something like a MAX232) would work perfectly in place of this.  It is unknown if the ROM code is different on the ZT10/ZT11 to support this extra serial port.

Also, on the underside of the main board on Sark's ZT-11 is a board providing the CPU with a new clock source. The frequency appears to be higher than the original ZT-1, perhaps to offer different baud rates, although there appear to be no baud rate settings on the setup screen.

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
Fuse is inside the PSU, and you must hammer the PSU case around the seam to open it. This is slightly destructive. Current draw on 15VAC is about 850ma while running. This creates ~12VDC after bridge rectifier inside terminal.

PSU information from Andrew C:
```
INPUT: 120V. 60HZ. 29W
OUTPUT: 10.2 V.R.M.S. @ 1.4 A.D.C
OUTPUT: 31.0 V.R.M.S. @ .020 A.D.C
```
### Thanks

Thanks to Sark for taking photos and dumping the ROMs on this ZT-11.
Thanks to Andrew C for sending PSU information

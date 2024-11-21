# WD33C93 Turbo

Sick of the slow SCSI speed of your Amiga 3000 onboard SCSI? Don't want to
spend the money on an A4091 SCSI controller? Well. Now you can have the cake
and eat it too. With the WD33C93 Turbo Interposer.

Yes, you heard right. This little board sits between your Amiga 3000 mainboard
and your WD33C93 or Am33c93 SCSI chip.

## What's in it?

You can increase the speed of your SCSI device access. On an Amiga 3000 with
25MHz 68030 and a WD33c93 turbo interposer running at 20MHz, we have measured
the following performance with Chris Hooper's devtest (https://github.com/cdhooper/amiga_devtest):

<p float="center">
<img src="images/wd33c93_devtest.jpg?raw=True" alt="devtest" width="75%" />
</p>

That's a solid 1MB/s more than on a regular Amiga 3000.

## How does it work?

The Amiga 3000 clocks the WD33c93 with 14MHz. Many variants of the chip are
specced for 16 or even 20 MHz.

Instead of feeding the slow 14MHz clock from the mainboard into the SCSI chip,
this little board lets you clock your WD33c93 with the clock frequency it was
designed for. Or a little higher.

## Does this always work?

Probably not. Without a driver update to your scsi.device you even end up with a slightly
overclocked SCSI bus . But your ZuluSCSI 2040 or BlueSCSI v2 does not care. They
can be driven with much higher frequencies that the 5 or 10MHz that the SCSI
bus is normally running at.

What about a real hard drive, you ask? A real CD-ROM? A SCSI attached scanner? I have not
tried. So if you do, please let me know.

## How to build this device?

You need two 20p pin headers, a 40p DIP socket, a 20MHz SMD oscillator (5V
tolerant), a 0.1uF 0805 capacitor and that's it.

## Experimental features

The WD33c93 Turbo can be equipped with two TSSOP DS21S07A active SCSI
terminator chips to add active termination instead of the sub optimal resistor
array based termination on the mainboard. Bonus: This termination can be turned
on/off with a jumper. In addition to the two DS21S07A chips, you will also need
two 4.7uF and one 2.2uF tantalum capacitors (0805) and a 1x02 jumper header.

## Where can I learn more?

Want to learn more about the various types of Wd33c93 and Am33c92 chips?
Check out Chris Hooper's comprehensive comparison at http://eebugs.com/scsi/wd33c93/

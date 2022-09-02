# Flex-Antenna-Disconnector
Teensy 4.1 based antenna disconnector / filter selector for Flex 6000 series radios.

Lu Romero, W4LT asked about a way to disconnect antennas from a pair of Flex radios owned
by the Tampa Amateur Radio Club.  He has Paradan switches, but no way to automatically
engage them.

While I was contemplating the antenna switch, Lu asked me about providing automatic switching
for the club's bandpass filters.  So I added that functionality as well.

The Flex radios stay powered up and wait for anyone with the proper credentials to log in and
use them.  When the Flex Antenna Disconnector detects a client logging into the radio. it sets 
a signal on pin 33 of the Teensy 4.1 board.  This signal is used to close the Paradan switch
so that the club member can operate. Once there are no more users connected to the radio, the 
Teensy resets pin 33 and the switch opens.

The antenna filter selection follows the panadapters.  If there is one panadapter open, the 
corresponding filter for that band is engaged through a dedicated Teensy pin.  If two bands are 
open at the same time, the filters are disengaged.

The Teensy boards communicate with the Flex radios using TCP/IP over Ethernet.  The USB port 
on the Teensy boards are just used to power and program the Teensy.  No radio control happens
using the USB port.

The goal is to allow club members to enjoy the club's pair of Flex 6000 radios without having
to remember to disconnect the antennas.  It is also to make the antenna filter switching
automatic to allow two transmitters to operate at the same site.

I hope this is useful!

73,
Len, KD0RC

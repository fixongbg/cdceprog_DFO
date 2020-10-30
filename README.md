# How to program DFO with cdceprog
This is a guide for programming DFOs for the Mega Drive, Playstation and Saturn with a Raspberry Pi. This corrects the sync frequence with a DFO (Dual Frequence Oscillator) to match 60Hz on PAL consoles when using region modded PAL/NTSC consoles. This is my collection of files to make the process much easier do. Credit goes to ikorb. 

# Connections

To connect the DFO to the Raspberry Pi, check the nice overview of the
GPIO connector [here](http://pi.gadgetoid.com/pinout). The programming
pins on the DFO must be connected as follows:

* DFO `SDA` to RasPi pin 3
* DFO `SCL` to RasPi pin 5
* DFO `GND` to RasPi pin 6
* DFO `3.3V` or `5V` to RasPi pin 1 or 2 (depends on the DFO board).

When connection is done, open up your SSH software of choice, connect to the Rpi and check if you can communicate with the clock generator chip on the DFO using:

       sudo i2cdetect -y 1

You should see a lot of dashes but in all those dashes there should be a number saying 65 (or any number) [like this](https://lh3.googleusercontent.com/_Gxg1M49yRi2BTcX0c3Z45i9h1tF_bkZa5rPwzWThPDWSAVoe7ZAxWv1xEoaSQSiG40iK5rT7gLBfwl75UDkaSGNPgL3dOsNAjHFuS8S7v5-eZkJk62OTY54CyYILQQZ1Pm8r546riM=w2400).
<br>If so, your good to go. If not, check your connections.

# Programming

Let's start by downloading the Python script (this does the programming) and the HEX-files for MD, PSX or SAT (timing files).
Type the following:

       cd Downloads
       
       git clone https://github.com/fix-ON/cdceprog_DFO.git
       
       cd cdceprog_DFO
       
Now, if your programming a DFO for the Mega Drive or Playstation, use MD_PSX.HEX.
If your programming for the Saturn, use SAT.HEX.
<br>In this guide we're using the MD_PSX.HEX, so type:

       sudo python cdceprog.py MD_PSX.HEX 
       
You should see a text that says: 

       Found data for a CDCE 913 chip.
       Waiting until EEPROM write cycle finishes...
       
Congratulations! 
Your DFO is now programmed.

# Installation
       
Installation for Playstation. [Check this](https://www.consolesunleashed.com/guides/sony-playstation-dual-frequency-oscillator-install-guide/).
<br>Installation for Mega Drive. [Check this](https://www.consolesunleashed.com/guides/sony-playstation-dual-frequency-oscillator-install-guide/).

[My own corrected installation](https://lh3.googleusercontent.com/YM1fPKKGZmAsZ23TLTULbut0lwdu7vYrq3Oe_t-7z9aZYnW7kQdPS30FKhKIY_Z4Xth14he5_4DSMkzZdRePHbivP_WVnAIu9CCfXsZncvz31CIxwi5SFzW7G0Sq5I7l-KcyscL1HO0=w2400) pic of the Playtation SCPH-100X PU-8 version. 

Picture of [my installation](https://lh3.googleusercontent.com/yA1KRLiw6e9q29PxjYsE2boe5n0g3t3T99dDg1JlJhc2YcsBoSy-kkWRHj08fb8A3P_q4zZzKag11orBf0PaYURxHIdjlMMwspfZJojBVSPcbiEr0oOo8DOR_08zUR4Pe34DS7nPWgM=w2400) (previous mods not made by me).
 













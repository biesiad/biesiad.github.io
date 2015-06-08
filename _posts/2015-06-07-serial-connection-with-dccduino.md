---
layout:     post
title:      USB Serial communication with DCCduino
date:       2015-06-07 13:30:00
summary:    Setting up usb serial port connection with cheap Arduino clone - DCCduino
categories: arduino dccduino serial port CH34OG
---


Recently I bought a few cheap Arduino clones from Amazon. They are supposed to be compatible with Arduino platform and virtualy be able to replace corresponding Arduino board.

![Avaliable serial ports](/images.jpg)

I connected it to with computer via USB cable and opened Arduino IDE. Unfortunately no additional serial port showed up in my IDE. Turns out DCCduino devices use different USB/Serial port converter. Instead of FTDI chip I found a CH34OG on on the bottom of my Arduino clone. Google search took me instantly a stack exchange [thread](http://arduino.stackexchange.com/questions/3700/rename-device-name-ch340-usb-to-serial-mac-os). I found there a link to the driver and some help on how to install it.

Driver page: [http://www.wch.cn/download/CH341SER_MAC_ZIP.html](http://www.wch.cn/download/CH341SER_MAC_ZIP.html)

On Yosemite you also have to run this command and restart the computer to enable non-approved drivers to work:

```bash
sudo nvram boot-args="kext-dev-mode=1"
```

Once the driver was installed and configuration updated new serial port show up in Arduino IDE and I can upload my sketches to DCCduino board.

![Avaliable serial ports](/images.jpg)

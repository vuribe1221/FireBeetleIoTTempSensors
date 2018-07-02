# 1 Day Temperature Sensor Project

## Introduction

> Problem statement: Server is running at over 40 degrees Celsius at idle and there aren’t any enough sensors on the motherboard to narrow down the problem areas.

> Action item: Create a temperature sensor platform to take many temperatures from different locations on the and output the measurements.

>Design: Use an off the shelf IoT platform and 1-Wire temperature sensors to create a quick temperature visualizer.

>Solution: Searching on Digikey I found the <a href=https://www.digikey.com/product-detail/en/dfrobot/DFR0489/1738-1352-ND/7897985>Firebeetle</a> that fits my needs of wifi enabled and ability to be powered over 5v (with a battery pinout if needed). The <a href=https://www.digikey.com/product-detail/en/maxim-integrated/DS18B20-/DS18B20--ND/956983>DS18B20</a> is the temperature sensor that I chose because it was the cheapest and easiest to use. 

Of course there is no need to re-invent the wheel so I found some good example code that will help finish this project in a day.

Full credit goes to <a href=https://www.hackster.io/adachsoft_com/esp8266-temperature-sensors-ds18b20-with-http-server-5509ac>Adach.com</a> for the picture of the schematic and the sample code.

<img src="https://hackster.imgix.net/uploads/attachments/274707/schematic_Mmklsxmjth.png" width="500">

> Conclusion: With the temperature sensor I was able to identify hot spots on the ram and near the video card (go figure). I rectified the hot spots by adding more fans and now the ambient server case temperature is almost 10 degrees cooler (except the CPU).

Before:
<img src="https://i.imgur.com/6EDvr2h.png">

After:
<img src="https://i.imgur.com/eXHdXkO.png">

28e80a550a000018    CPU Cooler<br>
28e254550a0000e0    GPU Area<br>
28b2c7540a0000b8    HDD Area<br>
287dbf540a000050    RAM Area

> Where to from here?
If this was a product I was going to keep using I could easily add MQTT funcionatily so that it can post the temperatures to my MQTT server and I could create alerts or monitor the temperatures over time and visualize it. At this time it fixed the issues so the project is not going to advance and this time.

## Installation

> 1. First flash the Firebeetle using the NodeMCU application to enable the Arduino environment on the chip.
> 2. Open the MultipleTempSensors.ino sketch in the Arduino IDE and upload the code to the Firebeetle(ESP8266).

Once you attach sensor and reboot the board it should detect and find all of the temperature sensors then update the webpage accordingly.
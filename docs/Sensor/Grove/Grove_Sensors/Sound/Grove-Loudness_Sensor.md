---
title: Grove - Loudness Sensor
nointro:
keywords:
  - docs
  - docusaurus
image: https://wiki.seeedstudio.com/Grove-Loudness_Sensor/
slug: /Grove-Loudness_Sensor
last_update:
  date: 01/06/2022
  author: gunengyu
---

![](https://files.seeedstudio.com/wiki/Grove-Loudness_Sensor/img/Loudness%20Sensor_new.jpg)

The Grove - Loudness Sensor is designed to detect the sound of environment. Based on LM2904 amplifier and a built-in microphone, it amplifies and filters the high frequency signal that received from the microphone, and outputs a positive envelop. This is used for Arduino’s signal acquisition. The output value depends on the level of sound input. In order to avoid unnecessary signal disturbances, input signal will go through two times’ filtering inside the module. There is a screw potentiometer that enables manual adjustments to the output gain.

<iframe width="800" height="450" src="https://www.youtube.com/embed/EhZ7uDvoALE" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<p style={{}}><a href="https://www.seeedstudio.com/Grove-Loudness-Sensor-p-1382.html" target="_blank"><img src="https://files.seeedstudio.com/wiki/wiki_english/docs/images/get_one_now_small.png" width={200} height={38} border={0} /></a></p>

## Version

| Product Version              | Changes                                   | Released Date |
|------------------------------|-------------------------------------------|---------------|
|Grove-Loudness Sensor V0.9b   | Initial                                   | Dec 2012      |

## Features

- Grove Interface
- Easy to use
- Basic Grove element

:::tip
    More details about Grove modules please refer to [Grove System](https://wiki.seeedstudio.com/Grove_System/)
:::

## Specifications

| Parameter             | Value/Range            |
|-----------------------|------------------------|
| Voltage               | 3.5~10 VDC             |
| Working Frequency     | 5~2000 Hz              |
| Sensitivity           | -60~-56dBV/Pa           |
| Signal-to-noise Ratio | >58 dB                 |
| Output Signal range   | Analog Signal (0-1023) |

## Platforms Supported

| Arduino                                                                                             | Raspberry Pi                                                                                             |                                                                                                 |                                                                                                          |                                                                                                    |
|-----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| ![](https://files.seeedstudio.com/wiki/wiki_english/docs/images/arduino_logo.jpg) | ![](https://files.seeedstudio.com/wiki/wiki_english/docs/images/raspberry_pi_logo.jpg) | ![](https://files.seeedstudio.com/wiki/wiki_english/docs/images/bbg_logo.jpg) | ![](https://files.seeedstudio.com/wiki/wiki_english/docs/images/wio_logo_n.jpg) | ![](https://files.seeedstudio.com/wiki/wiki_english/docs/images/linkit_logo.jpg) |

:::caution
    The platforms mentioned above as supported is/are an indication of the module's software or theoritical compatibility. We only provide software library or code examples for Arduino platform in most cases. It is not possible to provide software library / demo code for all possible MCU platforms. Hence, users have to write their own software library.
:::

## Getting Started

:::note
    If this is the first time you work with Arduino, we firmly recommend you to see [Getting Started with Arduino](https://wiki.seeedstudio.com/Getting_Started_with_Arduino/) before the start.
:::

### Play With Arduino

**Hardware**

- **Step 1.** Prepare the below stuffs:

| Seeeduino V4.2 | Base Shield|  Grove-Loudness Sensor |
|--------------|-------------|-----------------|
|![enter image description here](https://files.seeedstudio.com/wiki/wiki_english/docs/images/seeeduino_v4.2.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/wiki_english/docs/images/base_shield.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Grove-Loudness_Sensor/img/LoudnessSensor_s.jpg)|
|[Get One Now](https://www.seeedstudio.com/Seeeduino-V4.2-p-2517.html)|[Get One Now](https://www.seeedstudio.com/Base-Shield-V2-p-1378.html)|[Get One Now](https://www.seeedstudio.com/Grove-Loudness-Sensor-p-1382.html)|

- **Step 2.** Connect Grove-Loudness Sensor to **A0** port of Grove-Base Shield.
- **Step 3.** Plug Grove - Base Shield into Seeeduino.
- **Step 4.** Connect Seeeduino to PC via a USB cable.

![](https://files.seeedstudio.com/wiki/Grove-Loudness_Sensor/img/seeeduino_loudness.jpg)

:::note
 If we don't have Grove Base Shield, We also can directly connect Grove-Loudness Sensor to Seeeduino as below.
:::

| Seeeduino |  Grove-Loudness Sensor |
|-----------|-----------------|
| 5V        | Red             |
| GND       | Black           |
| NC        | White           |
| A0        | Yellow          |

**Software**

- **Step 1.** Please copy below code to Arduio IDE and upload to arduino. If you do not know how to upload the code, please check [how to upload code](https://wiki.seeedstudio.com/Upload_Code/).

```
int loudness;

void setup()
{
    Serial.begin(9600);
}

void loop()
{
    loudness = analogRead(0);
    Serial.println(loudness);
    delay(200);
}

```

- **Step 2.** Open the serial to monitor the output. It will be a significant change when blow to the sensor.

![](https://files.seeedstudio.com/wiki/Grove-Loudness_Sensor/img/seeeduino_serial.png)

### Play With Raspberry Pi (With Grove Base Hat for Raspberry Pi)

#### Hardware

- **Step 1**. Things used in this project:

| Raspberry pi | Grove Base Hat for RasPi | Grove - Loudness Sensor |
|--------------|-------------|-----------------|
|![enter image description here](https://files.seeedstudio.com/wiki/wiki_english/docs/images/rasp.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Grove_Base_Hat_for_Raspberry_Pi/img/thumbnail.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Grove-Loudness_Sensor/img/LoudnessSensor_s.jpg)|
|[Get ONE Now](https://www.seeedstudio.com/Raspberry-Pi-3-Model-B-p-2625.html)|[Get ONE Now](https://www.seeedstudio.com/Grove-Base-Hat-for-Raspberry-Pi-p-3186.html)|[Get ONE Now](https://www.seeedstudio.com/Grove-Loudness-Sensor-p-1382.html)

- **Step 2**. Plug the Grove Base Hat into Raspberry Pi.
- **Step 3**. Connect the Grove - Loudness Sensor to to the A0 port of the Base Hat.
- **Step 4**. Connect the Raspberry Pi to PC through USB cable.
![](https://files.seeedstudio.com/wiki/Grove-Loudness_Sensor/img/withrpi_basehat.jpg)

#### Software

- **Step 1**. Follow [Setting Software](https://wiki.seeedstudio.com/Grove_Base_Hat_for_Raspberry_Pi/#installation) to configure the development environment.
- **Step 2**. Download the source file by cloning the grove.py library.

```
cd ~
git clone https://github.com/Seeed-Studio/grove.py

```

- **Step 3.** Excute below command to run the code.

```
cd grove.py/grove
python grove_loudness_sensor.py 0
```

Following is the grove_water_sensor.py code.

```python

import math
import sys
import time
from grove.adc import ADC


class GroveLoudnessSensor:

    def __init__(self, channel):
        self.channel = channel
        self.adc = ADC()

    @property
    def value(self):
        return self.adc.read(self.channel)

Grove = GroveLoudnessSensor


def main():
    if len(sys.argv) < 2:
        print('Usage: {} adc_channel'.format(sys.argv[0]))
        sys.exit(1)

    sensor = GroveLoudnessSensor(int(sys.argv[1]))

    print('Detecting loud...')
    while True:
        value = sensor.value
        if value > 10:
            print("Loud value {}, Loud Detected.".format(value))
            time.sleep(.5)

if __name__ == '__main__':
    main()


```

:::success
    If everything goes well, you will be able to see the following result:
:::

```python

pi@raspberrypi:~/grove.py/grove $ python grove_loudness_sensor.py 0
Detecting loud...
Loud value 15, Loud Detected.
Loud value 11, Loud Detected.
Loud value 250, Loud Detected.
Loud value 429, Loud Detected.
Loud value 203, Loud Detected.
Loud value 16, Loud Detected.
Loud value 11, Loud Detected.
^CTraceback (most recent call last):
  File "grove_loudness_sensor.py", line 68, in <module>
    main()
  File "grove_loudness_sensor.py", line 65, in main
    time.sleep(.5)
KeyboardInterrupt


```

You can use this sensor to detect the loudness. Press ++ctrl+c++ to quit.

:::note
        You may have noticed that for the analog port, the silkscreen pin number is something like **A1, A0**, however in the command we use parameter **0** and **1**, just the same as digital port. So please make sure you plug the module into the correct port, otherwise there may be pin conflicts.
:::

### Play With Raspberry Pi(with GrovePi_Plus)

**Hardware**

- **Step 1.** Prepare the below stuffs:

| Raspberry pi | GrovePi_Plus | Grove-Loudness Sensor |
|--------------|-------------|-----------------|
|![enter image description here](https://files.seeedstudio.com/wiki/wiki_english/docs/images/rasp.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/wiki_english/docs/images/Grovepi%2B.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Grove-Loudness_Sensor/img/LoudnessSensor_s.jpg)|
|[Get One Now](https://www.seeedstudio.com/Raspberry-Pi-3-Model-B-p-2625.html)|[Get One Now](https://www.seeedstudio.com/GrovePi%2B-p-2241.html)|[Get One Now](https://www.seeedstudio.com/Grove-Loudness-Sensor-p-1382.html)|

- **Step 2.** Plug the GrovePi_Plus into Raspberry.
- **Step 3.** Connect Grove-Loudness Sensor to **A0** port of GrovePi_Plus.
- **Step 4.** Connect the Raspberry to PC through USB cable.

![](https://files.seeedstudio.com/wiki/Grove-Loudness_Sensor/img/rpi_loudness.jpg)

**Software**

- **Step 1.** Follow [Setting Software](https://www.dexterindustries.com/GrovePi/get-started-with-the-grovepi/setting-software/) to configure the development environment.
- **Step 2.** Git clone the Github repository.

```
cd ~
git clone https://github.com/DexterInd/GrovePi.git

```

- **Step 3.** Excute below commands to monitor the loudness.

```python
cd ~/GrovePi/Software/Python
python grove_loudness_sensor.py
```

Here is the grove_loudness_sensor.py code.

```python
import time
import grovepi

# Connect the Grove Loudness Sensor to analog port A0
# SIG,NC,VCC,GND
loudness_sensor = 0

while True:
    try:
        # Read the sound level
        sensor_value = grovepi.analogRead(loudness_sensor)

        print("sensor_value = %d" %sensor_value)
        time.sleep(.5)

    except IOError:
        print ("Error")
```

- **Step 4.** We will see the loudness status as below.

```python
pi@raspberrypi:~/GrovePi/Software/Python $ python grove_loudness_sensor.py
sensor_value = 135
sensor_value = 23
sensor_value = 196
sensor_value = 258
sensor_value = 98
sensor_value = 131
```

## FAQ

- Q1: What is the difference between Grove-Loudness sensor and Grove - Sound Sensor?
  - A1: The Grove-Loudness sensor have screw potentiometer to adjust the output gain.

## Schematic Online Viewer

<div className="altium-ecad-viewer" data-project-src="https://files.seeedstudio.com/wiki/Grove-Loudness_Sensor/res/Grove%20-%20Loudness%20Sensor%20Eagle%20File_v0.9b.zip" style={{borderRadius: '0px 0px 4px 4px', height: 500, borderStyle: 'solid', borderWidth: 1, borderColor: 'rgb(241, 241, 241)', overflow: 'hidden', maxWidth: 1280, maxHeight: 700, boxSizing: 'border-box'}}>
</div>

## Resources

- **[Eagle&PDF]** [Grove - Loudness Sensor Schematic](https://files.seeedstudio.com/wiki/Grove-Loudness_Sensor/res/Grove%20-%20Loudness%20Sensor%20Eagle%20File_v0.9b.zip)
- **[Datasheet]** [LM2904DR Datasheet](https://files.seeedstudio.com/wiki/Grove-Loudness_Sensor/res/LM2904DR.pdf)

## Projects

**Solar Powered Environmental Monitoring Kit**: A solar-powered open source kit for monitoring air quality, sound level, humidity, and temperature.

<iframe frameborder='0' height='327.5' scrolling='no' src='https://www.hackster.io/taifur/solar-powered-environmental-monitoring-kit-b1d03d/embed' width='350'></iframe>

**The Da Vinci Code**: The work combines art and electronics. The art part makes the skeleton and consists of 11 layers of medium density fiberboard.

<iframe frameborder='0' height='327.5' scrolling='no' src='https://www.hackster.io/coding-with-da-vince/the-da-vinci-code-3b91a8/embed' width='350'></iframe>

## Upgradable to Industrial Sensors

With the SenseCAP [S2110 controller](https://www.seeedstudio.com/SenseCAP-XIAO-LoRaWAN-Controller-p-5474.html) and [S2100 data logger](https://www.seeedstudio.com/SenseCAP-S2100-LoRaWAN-Data-Logger-p-5361.html), you can easily turn the Grove into a LoRaWAN® sensor. Seeed not only helps you with prototyping but also offers you the possibility to expand your project with the SenseCAP series of robust [industrial sensors](https://www.seeedstudio.com/catalogsearch/result/?q=sensecap&categories=SenseCAP&application=Temperature%2FHumidity~Soil~Gas~Light~Weather~Water~Automation~Positioning~Machine%20Learning~Voice%20Recognition&compatibility=SenseCAP).

The IP66 housing, Bluetooth configuration, compatibility with the global LoRaWAN® network, built-in 19 Ah battery, and powerful support from APP make the [SenseCAP S210x](https://www.seeedstudio.com/catalogsearch/result/?q=S21&categories=SenseCAP&product_module=Device) the best choice for industrial applications. The series includes sensors for soil moisture, air temperature and humidity, light intensity, CO2, EC, and an 8-in-1 weather station. Try the latest SenseCAP S210x for your next successful industrial project.

<div align="center"><a href="https://www.seeedstudio.com/catalogsearch/result/?q=sensecap&application=Temperature%2FHumidity~Soil~Gas~Light~Weather~Water~Automation~Positioning~Machine%20Learning~Voice%20Recognition&compatibility=SenseCAP" target="_blank"><img width={800} src="https://files.seeedstudio.com/wiki/K1100_overview/sensecap.png" /></a></div>

## Tech Support & Product Discussion

Thank you for choosing our products! We are here to provide you with different support to ensure that your experience with our products is as smooth as possible. We offer several communication channels to cater to different preferences and needs.

<div class="button_tech_support_container">
<a href="https://forum.seeedstudio.com/" class="button_forum"></a> 
<a href="https://www.seeedstudio.com/contacts" class="button_email"></a>
</div>

<div class="button_tech_support_container">
<a href="https://discord.gg/eWkprNDMU7" class="button_discord"></a> 
<a href="https://github.com/Seeed-Studio/wiki-documents/discussions/69" class="button_discussion"></a>
</div>

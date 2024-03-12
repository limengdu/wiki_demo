---
title: Grove - Recorder V3
nointro:
keywords:
  - docs
  - docusaurus
image: https://wiki.seeedstudio.com/Grove-Recorder_v3.0/
slug: /Grove-Recorder_v3.0
last_update:
  date: 01/09/2022
  author: gunengyu
---

![enter image description here](https://files.seeedstudio.com/wiki/Grove_Recorder_V3/img/cover.jpg)

This is the latest version of Grove-recorder, and also the best version. Comparing the previous one, there are some updates that we would like to mention.

First change is MCU. In V3.0, the MCU is upgraded from to be ISD9160FI, which is more powerful than the old one ISD1820PY. How is it more powerful? Together with the newly added 2Mbytes flash, it allows you to record up to 83 seconds, much longer than previous 12 sec record.

Secondly, if you have ever used previous version, you would know that if you want to play back what you have recorded, you need to press another button on the Grove button that connected separately. In V3.0, we integrated the record button and play back button in to one button. By holding the button for 2 sec, it starts recording, by push the button quickly, it plays back what has been recorded.

## What's new in V3

* MCU from ISD1820PY to ISD 9160FI
* Record and playback button
* Record switch
* 2Mbytes flash

## Features

* Very long record time, up to 83s
* Built-in button to operate
* Built-in led indicator
* Stand alone or control by MCU
* Built-in Microphone

:::tip
    More details about Grove modules please refer to [Grove System](https://wiki.seeedstudio.com/Grove_System/)
:::

## Platform Support

|Arduino|Wio|BeagleBone|Raspberry Pi|LinkIt|
|---------|-----|-----|------|------|
|![enter image description here](https://files.seeedstudio.com/wiki/Seeed-WiKi/docs/images/arduino_logo.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Seeed-WiKi/docs/images/wio_logo.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Seeed-WiKi/docs/images/bbg_logo.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Seeed-WiKi/docs/images/raspberry_pi_logo.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Seeed-WiKi/docs/images/linkit_logo.jpg)|

## Specification

* Working Voltage: 3.3/5V
* Working Current (@5V, 25℃)
  * Standby: 25-30mA
  * Recording: 29-35mA
  * Playing: 110-150mA
* Working Current (@3.3V, 25℃)
  * Standby: 23-25mA
  * Recording: 25-30mA
  * Playing: 70-150mA
* Working Temperature: 0~85℃
* Size: 40x20mm
* Weight: 31.5g

## Hardware Overview

![enter image description here](https://files.seeedstudio.com/wiki/Grove_Recorder_V3/img/hw.png)

1.Speaker Connector - JST2.0

2.Microphone

3.Voice Control

4.Button

* Short Press and Release: Play
* Long Press: Start recording until release the button

5.Led Indicator

* Red led, lights when button press

6.Grove Connector

7.REC Switch

* Switch to ON if you want to control the module to record vis Software

8.MCU

## Getting Started

Here we will show you how this Grove - Recorder V3.0 works via a simple demo. First of all, you need to prepare the below stuffs:

| Seeeduino V4 | Grove - Recorder | Base Shield |
|--------------|----------------------|-----------------|
|![enter image description here](https://files.seeedstudio.com/wiki/Grove_Light_Sensor/images/gs_1.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Grove_Recorder_V3/img/stuff.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Grove_Light_Sensor/images/gs_4.jpg)|
|[Get ONE Now](https://www.seeedstudio.com/Seeeduino-V4.2-p-2517.html)|[Get ONE Now](https://www.seeedstudio.com)|[Get ONE Now](https://www.seeedstudio.com/Grove-Universal-4-Pin-20cm-Unbuckled-Cable-%285-PCs-Pack%29-p-749.html)|

### Hardware Connection
Thanks to the benefit of Grove series module, you don't need to make soldering or bread board, what you need to do is connect the modules to the right port of Base Shield. For this demo, we connect Grove - Recorder to D2.

![enter image description here](https://files.seeedstudio.com/wiki/Grove_Recorder_V3/img/connection.jpeg)

## Standalone

This module can work standalone without coding.

* **Record** - Press the button until the LED light, and it's recording, release the button when finish recording.
* **Play** - Press and release the button to play the voice that had been recorded.

If you want to control the module by code. please go ahead.

## Software

Copy the below code and paste to your Arduino IDE, and upload to your Seeeduino V4. After upload the code to an Arduino, then open the Serial monitor.

```
/* Grove - Recorder Test Code
+--------------------------------------------------------------------+
|   Open Serial Monitor and input command to control the module:
|   r - start recording
|   s - stop recording
|   p - play
+-------------------------------------------------------------------*/

const int pinRec  = 3;
const int pinPlay = 2;

void setup() 
{
    Serial.begin(115200);
    Serial.println("Grove - Recorder V3.0 Test Code");
    Serial.println("cmd: \r\nr: record\r\ns: stop recording\r\np: play");
    
    pinMode(pinRec, OUTPUT);
    pinMode(pinPlay, OUTPUT);
    digitalWrite(pinRec, HIGH);
    digitalWrite(pinPlay, HIGH);
}

void loop() 
{
    if(Serial.available())
    {
        char c = Serial.read();
        if(c == 'r')            // begin to record
        {
            digitalWrite(pinRec, LOW);
            Serial.println("start recording...");
        }
        else if(c == 's')       // stop recording
        {
            digitalWrite(pinRec, HIGH);
            Serial.println("stop recording...");
        }
        else if(c == 'p')       // play
        {
            digitalWrite(pinPlay, LOW);
            delay(100);
            digitalWrite(pinPlay, HIGH);
            Serial.println("play...");
        }
    }
}
```

## Enter Command

You can enter some command in Serial monitor:

* **Start recording** - Enter a 'r'
* **Stop recording** - Enter a 's'
* **Play** - Enter a 'p'

### Play with Codecraft

#### Hardware

**Step 1.** Connect a Grove - Record to port D2 of a Base Shield.

**Step 2.** Plug the Base Shield to your Seeeduino/Arduino.

**Step 3.** Link Seeeduino/Arduino to your PC via an USB cable.

#### Software

**Step 1.** Open [Codecraft](https://ide.chmakered.com/), add Arduino support, and drag a main procedure to working area.

:::note
    If this is your first time using Codecraft, see also [Guide for Codecraft using Arduino](https://wiki.seeedstudio.com/Guide_for_Codecraft_using_Arduino/).
:::
**Step 2.** Drag blocks as picture below or open the cdc file which can be downloaded at the end of this page.

![cc](https://files.seeedstudio.com/wiki/Grove_Recorder/img/cc_Recorder.png)

Upload the program to your Arduino/Seeeduino.

:::tip
    When the code finishes uploaded, you can use Recorder to record and play via Serial Monitor.
:::

## Schematic Online Viewer

<div className="altium-ecad-viewer" data-project-src="https://files.seeedstudio.com/wiki/Grove_Recorder_V3/res/eagle.zip" style={{borderRadius: '0px 0px 4px 4px', height: 500, borderStyle: 'solid', borderWidth: 1, borderColor: 'rgb(241, 241, 241)', overflow: 'hidden', maxWidth: 1280, maxHeight: 700, boxSizing: 'border-box'}}>
</div>

## Resources

* [Schematics in PDF](https://files.seeedstudio.com/wiki/Grove_Recorder_V3/res/Grove%20-%20Recorder%20v3.0a.pdf)
* [Schematics in Eagle](https://files.seeedstudio.com/wiki/Grove_Recorder_V3/res/eagle.zip)
* [Codecraft CDC File](https://files.seeedstudio.com/wiki/Grove_Recorder/res/Grove_Recorder_CDC_File.zip)

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

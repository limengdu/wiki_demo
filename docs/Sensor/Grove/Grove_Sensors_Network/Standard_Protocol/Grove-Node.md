---
description: Grove - Node
title: Grove - Node
keywords:
- Grove_Sensors_Network
image: https://files.seeedstudio.com/wiki/wiki-platform/S-tempor.png
slug: /Grove-Node
last_update:
  date: 1/20/2023
  author: jianjing Huang
---


 Grove - Node is a simple and flexible electronic module to connect physical objects. It's based on the idea of IFTTT (IF-This-Then-That). It has two Grove connectors to access a variety of Grove modules. With pre-programming IFTTT firmware, it's easy to create physical objects with analog sensors and 0/1 actuators.


It integrates Bluetooth Low Energy (BLE) which makes it extremely easy to interact with phones and tablets. To extend its usability, a DFU bootloader is built in to reprogram it Over-The-Air through BLE. It supports ARM mbed platform to write new firmware with hundreds of libraries.

## Features

* IFTTT pattern to use

* Two Grove connectors for sensors and actuators

  * Plug-Play with analog sensors and high/low actuators

    * Flexible 4 GPIOs, all can be used for PWM, ADC, I2C and UART

* Nordic nRF51822 Multi-protocol Bluetooth® 4.0 low energy/2.4GHz RF SoC

  * ARM Cortex-M0 processor

    * 256kB flash, 16kB RAM

* On board battery charge circuit

* OTA firmware

* mbed enabled

  * Online IDE

    * Easy to use C/C++ SDK

    * Handy libraries

## Specifications

* Operating voltage: 3.3Vdc

* Battery capacity: 80mAH

* Maximum charge current: 100mA

* Grove Interface supply Voltage：3.3V

* Grove Interface supply Current:  100mA max

* Grove Interface input Voltage：0~3.3V

## Pinout

## Get Started

* Turn On Grove Node

Connect Grove Node with a battery or a USB cable and then press its button, it will run.

<dl><dd>

* Double Clicks - run its bootloader, the red LED will be on.

* Otherwise - run its application, the green LED will blink.

</dd></dl>

* Turn Off Grove Node

<dl><dd>

* In bootloader mode - wait for a while to run into the application.

* In application mode - long press the button wait until all LEDs are off

</dd></dl>

### Get Started with Pre-programmed Firmware

![](https://files.seeedstudio.com/wiki/Grove-Node/img/Milcandy_IFTTT.jpg)

First, we need an **Input** Grove module to sense the physical world. Pre-programmed firmware only supports an analog input sensor or 0/1 digital input sensor.
The following Grove modules from Seeedstudio can be used as an **Input**:

<table>
  <tbody><tr>
      <th>Module name
      </th>
      <th>Parameter to measure
      </th></tr>
    <tr style={{fontSize: '90%'}}>
      <td width={300}> Grove - 80cm Infrared Proximity Sensor
      </td>
      <td width={400}> Distance
      </td></tr>
    <tr style={{fontSize: '90%'}}>
      <td> Grove - Button
      </td>
      <td colSpan={3} rowSpan={1}>On/Off
      </td></tr>
    <tr style={{fontSize: '90%'}}>
      <td> Grove - Electricity Sensor
      </td>
      <td colSpan={3} rowSpan={1}> Electricity
      </td></tr>
    <tr style={{fontSize: '90%'}}>
      <td> Grove - Gas Sensor(MQ2&amp;MQ5)
      </td>
      <td colSpan={3} rowSpan={1}> Gas Quality
      </td></tr>
    <tr style={{fontSize: '90%'}}>
      <td> Grove - Light Sensor
      </td>
      <td colSpan={3} rowSpan={1}> Light
      </td></tr>
    <tr style={{fontSize: '90%'}}>
      <td> Grove - Magnetic Switch
      </td>
      <td colSpan={3} rowSpan={1}> Magnetic
      </td></tr>
    <tr style={{fontSize: '90%'}}>
      <td> Grove - Moisture Sensor
      </td>
      <td colSpan={3} rowSpan={1}> Moisture
      </td></tr>
    <tr style={{fontSize: '90%'}}>
      <td> Grove - PIR Motion Sensor
      </td>
      <td colSpan={3} rowSpan={1}> PIR Motion
      </td></tr>
    <tr style={{fontSize: '90%'}}>
      <td> Grove - Rotary Angle Sensor
      </td>
      <td colSpan={3} rowSpan={1}> Rotary Angle
      </td></tr>
    <tr style={{fontSize: '90%'}}>
      <td> Grove - Tilt Switch
      </td>
      <td colSpan={3} rowSpan={1}>  Object Position
      </td></tr>
    <tr style={{fontSize: '90%'}}>
      <td> Grove - Sound Sensor
      </td>
      <td colSpan={3} rowSpan={1}> Sound
      </td></tr>
    <tr style={{fontSize: '90%'}}>
      <td> Grove - Temperature Sensor
      </td>
      <td colSpan={3} rowSpan={1}> Temperature
      </td></tr>
    <tr style={{fontSize: '90%'}}>
      <td> Grove - Touch Sensor
      </td>
      <td colSpan={3} rowSpan={1}> Human touch
      </td></tr>
    <tr style={{fontSize: '90%'}}>
      <td> Grove - Water Sensor
      </td>
      <td colSpan={3} rowSpan={1}> Water
      </td></tr></tbody></table>

Other analog sensors which is not Grove-compatible need a little small adjustment. Just connect your signal output to pin4 of Grove connector and then the VCC and GND. _Note that only sensors that output an analog or digital 1/0 value can be used with the pre-programmed firmware_

![](https://files.seeedstudio.com/wiki/Grove-Node/img/Mil_Grove_con.png)

Second, we need an **output** Grove module as an actuator. The following Grove modules can be used:

<table>
  <tbody><tr>
      <th>Module name
      </th>
      <th>Action when triggered
      </th></tr>
    <tr style={{fontSize: '90%'}}>
      <td width={300}> Grove - Buzzer
      </td>
      <td width={400}> Buzzer enabled
      </td></tr>
    <tr style={{fontSize: '90%'}}>
      <td> Grove - LED
      </td>
      <td colSpan={3} rowSpan={1}>LED On
      </td></tr>
    <tr style={{fontSize: '90%'}}>
      <td> Grove - Vibrator
      </td>
      <td colSpan={3} rowSpan={1}> Vibrate
      </td></tr>
    <tr style={{fontSize: '90%'}}>
      <td> Grove - Relay
      </td>
      <td colSpan={3} rowSpan={1}> Swith On/Off other circuits
      </td></tr></tbody></table>


For example, we intend to create a light which automatically turns on if the environment is dark and turns off if otherwise, then we select a [Grove-Light_Sensor](/Grove-Light_Sensor "Grove - Light Sensor") and a Grove-Red_LED. 


Third, teach the Grove Node a logic.

Connect the light sensor as an input and the LED as an output, and then turn on the Grove Node.

* In a normal environment, do a single-click on the Grove Node's button

* Cover the light sensor with a hand to simulate a dark environment, and then do a double-clicks, the Grove - LED will be on.

* Release the light sensor, the Grove - LED will be off.

## Over-The-Air

The Grove Node has a pre-programmed OTA bootloader. To run into the bootloader:

1. power off the Grove Node

2. do a double-clicks on the Grove Node's button

3. the red LED will be on and a BLE device named SD7DFU can be scaned

4. use [nRF Master Control Panel](https://play.google.com/store/apps/details?id=no.nordicsemi.android.mcp) to upgrade the BLE app

![](https://files.seeedstudio.com/wiki/Grove-Node/img/Ota-ui.png)

More information can be found at [mbed.org](https://developer.mbed.org/teams/Bluetooth-Low-Energy/wiki/Firmware-Over-the-Air-FOTA-Updates).

## Develop New Application

See [ble on mbed.org](http://developer.mbed.org/teams/Bluetooth-Low-Energy/)

## Schematic Online Viewer

<div className="altium-ecad-viewer" data-project-src="https://files.seeedstudio.com/wiki/Grove-Node/res/Grove-Node_v1.0_eagle.zip" style={{borderRadius: '0px 0px 4px 4px', height: 500, borderStyle: 'solid', borderWidth: 1, borderColor: 'rgb(241, 241, 241)', overflow: 'hidden', maxWidth: 1280, maxHeight: 700, boxSizing: 'border-box'}}>
</div>

## Resources

* [Grove - Node v1.0 schematic pdf file](https://files.seeedstudio.com/wiki/Grove-Node/res/Grove-Node_v1.0.pdf)

* [Grove - Node v1.0 eagle design file](https://files.seeedstudio.com/wiki/Grove-Node/res/Grove-Node_v1.0_eagle.zip)

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

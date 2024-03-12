---
description: Grove - Serial Camera Kit
title: Grove - Serial Camera Kit
keywords:
- Grove
image: https://files.seeedstudio.com/wiki/wiki-platform/S-tempor.png
slug: /Grove-Serial_Camera_Kit
last_update:
  date: 2/22/2023
  author: jianjing Huang
---
<!-- ---
name: Grove - Serial Camera Kit
category: Sensor
bzurl: https://www.seeedstudio.com/Grove-Serial-Camera-Kit-p-1608.html
oldwikiname:  Grove - Serial Camera Kit
prodimagename: GSCK_Introduction.jpg
surveyurl: https://www.research.net/r/Grove_Serial_Camera_Kit
sku:  101020000
--- -->

![](https://files.seeedstudio.com/wiki/Grove-Serial_Camera_Kit/img/GSCK_Introduction.jpg)

Grove - Serial Camera Kit includes one control board and two interchangeable lenses, one is standard lens and the other is wide-angle lens. It's a great camera for Arduino centered image recognition projects, because 30W pixel wouldn't be overwhelming for Arduino, so that real-time image recognition is possible. To make it more fun and playable, lenses of two specs are shipped in this kit. The standard one is for common photo shots and the wide-angle one is specially suitable for monitoring projects.

## Specifications

---

* Input Voltage: 5V

* Pixel: 300,000

* Resolution: 640*480, 320*240, 160*120

* Uart Baud Rate: 9600~115200

* Communication: RS485 and RS232

* Photo JPEG compression, high, medium and low grades Optional

* AGC

* Auto Exposure Event Control

* Automatic White Balance Control

* Focus adjustable

## Demonstration

---
This demo will show you how to use Grove - Serial Camera Kit. We need a [Seeeduino](https://www.seeedstudio.com/seeeduino-v30-atmega-328p-p-669.html?cPath=6_7), an [SD Card Shield](https://www.seeedstudio.com/sd-card-shield-v40-p-1381.html?cPath=105) and a [Grove - Button](/Grove-Button). When the button pressed, we take a photo and save it to SD Card.

Follow the below steps step by step, you can easily run your Grove - Serial Camera Kit. Then let's go.

### Hardware Installation

We can find that there are two Grove interfaces on SD Card Shield V4.0, so we needn't a Base Shield, just plug Button to I2C Grove and plug Camera to Uart Grove.

![](https://files.seeedstudio.com/wiki/Grove-Serial_Camera_Kit/img/GSCK_Hardware.jpg)

### Download Code and Upload

You can download demo code in github, click [here](https://github.com/Seeed-Studio/Grove_Serial_Camera_Kit)

Then upload the code, and it works.

### Take a Photo

After finish uploading demo code, we can take a photo now, just press the button, then wait for a few seconds, a photo will be saved to SD card.

The following image is the ceiling of my office use straight angle lens.

![](https://files.seeedstudio.com/wiki/Grove-Serial_Camera_Kit/img/GSCK_60.jpg)

### Replacing a Lens

There is another wide-angle lens, I will show you how to replace it.

Firstly you should have a screwdriver：

![](https://files.seeedstudio.com/wiki/Grove-Serial_Camera_Kit/img/GSCK_Step1.jpg)

Then, unscrew the screws on the side of lens:

![](https://files.seeedstudio.com/wiki/Grove-Serial_Camera_Kit/img/GSCK_Step2.jpg)

Try rotating the lens, it can be screwed out：

![](https://files.seeedstudio.com/wiki/Grove-Serial_Camera_Kit/img/GSCK_Step3.jpg)

We use  the wide-angle lens to take a photo, also, it's  the ceiling of my office!

Find anything different from the ceiling image previous?

![](https://files.seeedstudio.com/wiki/Grove-Serial_Camera_Kit/img/GSCK_90.jpg)

### How To Focus

Lens screwed different depths represent different focal length, you can have a try.

## Resources

* **[Library]** [Demo Code](https://github.com/Seeed-Studio/Grove_Serial_Camera_Kit)
* **[Datasheet]** [CJ OV528](https://files.seeedstudio.com/wiki/Grove-Serial_Camera_Kit/res/cj-ov528_protocol.pdf)

## Project

**Grove Camera -> PHPoC -> Web Application** This project shows how to read data from Grove camera and send the data to web application via WebSocket.

<iframe frameborder='0' height='327.5' scrolling='no' src='https://www.hackster.io/phpoc_man/grove-camera-phpoc-web-application-1dfd63/embed' width='350'></iframe>

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

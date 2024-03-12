---
description: Seeed Studio BeagleBone® Green LCD Cape with Resistive Touch
title: Seeed Studio BeagleBone® Green LCD Cape with Resistive Touch
keywords:
- Beagle_Bone
image: https://files.seeedstudio.com/wiki/wiki-platform/S-tempor.png
slug: /Seeed-Studio-BeagleBone-Green-LCD-Cape-with-Resistive-Touch
last_update:
  date: 1/10/2022
  author: jianjing Huang
---


![](https://www.seeedstudio.site/media/catalog/product/cache/ef3164306500b1080e8560b2e8b5cc0f/h/t/httpsstatics3.seeedstudio.comseeedimg2016-08ddkssqrw2lfthpq0phlecp1r.jpg)

**Green LCD Cape with Resistive Touch** is designed for SeeedStudio Beagle bone® Green or Beagle bone Black with a compact 5-inch LCD which is smaller than a 7-inch one but provides a resolution of 800x480 using a layer of 4-wired resistive touchscreen for user interactions. It's easy to setup by just connecting 2x46 pin headers to SeeedStudioBeaglebone®Green/Beaglebone®Black, which provides everything the cape requires such power supply and display signals. In addition, the cape can be powered by the built-in micro USB on the back. Buttons below the screen, LEFT, RIGHT, UP, DOWN and ENTER, provide an alternative way to interact with your screen. Two LEDs are used for power and user status indication.

**5 Inch**

<p style={{textAlign: 'center'}}><a href="https://www.seeedstudio.com/5-Inch-BeagleBone-Green-LCD-Cape-with-Resistive-Touch-p-2642.html" target="_blank"><img src="https://files.seeedstudio.com/wiki/Seeed-WiKi/docs/images/300px-Get_One_Now_Banner-ragular.png" /></a></p>

**7 Inch**

<p style={{textAlign: 'center'}}><a href="https://www.seeedstudio.com/7-Inch-BeagleBone-Green-LCD-Cape-with-Resistive-Touch-p-2643.html" target="_blank"><img src="https://files.seeedstudio.com/wiki/Seeed-WiKi/docs/images/300px-Get_One_Now_Banner-ragular.png" /></a></p>

## Features

--------

- Resolution up to 800x480 (5 inch)  /   1024x600 (7 inch)
- Resistive touchscreen
- 5 buttons including LEFT, RIGHT, UP, DOWN and ENTER
- Debian supported
- ULP backlight
- 4 x 3mm mounting holes
- Built-in USB power supply

## Specifications

-------------

| Name                | Value                                                                                                  |
|--------------------------|--------------------------------------------------------------------------------------------------------|
| Dimension            | 200mm x130mm x50mm                                                                                              |
| Weight | G.W 120g                                  |
|Working Voltage|5V |
|Working Current|110mA |
|Power|0.55W |

## Application

-----------------

Use it with BeagleBone® to display anything you want.

## Hardware

-----------------

![](https://www.seeedstudio.site/media/catalog/product/cache/ef3164306500b1080e8560b2e8b5cc0f/h/t/httpsstatics3.seeedstudio.comseeedimg2016-08za8h5rzwtbm1lq3n3oydkcxp.jpg)

**SN74HC245**

- Large range of IO driving current

**Cape I2C address switch**

- I2C address configuration switch

**CAT4139TD**

- Backlight, constant current and voltage

### Part list

|                            |          |
|----------------------------|----------|
| **Name**             | Quantity |
|  Green LCD Cape with Resistive Touch | 1        |

## Getting Started

-----------

***It will be shown to you how to get started step by step in this section.***

### Preparation

- BeagleBone® Green board or BeagleBone® black board(with OS [installation](https://beagleboard.org/getting-started)) × 1.
- USB cables (type A to micro type B) × 2.

### Hardware Connection

![](https://www.seeedstudio.site/media/catalog/product/cache/ef3164306500b1080e8560b2e8b5cc0f/h/t/httpsstatics3.seeedstudio.comseeedimg2016-086yqt2uwelst8w5mwuaklys12.jpg)

:::note
BeagleBone® Green board and Green LCD Cape with Resistive Touch both need to be USB-connected for sufficient driving.
:::

### Software Configuration

1. Check what COM port BeagleBone® Green board is using in Device Manager

![](https://files.seeedstudio.com/wiki/BBG-LCD-Cape-with-Resistive-Touch/img/com-show.png)

2. Access BeagleBone® Green board system using putty with the COM port.

![](https://files.seeedstudio.com/wiki/BBG-LCD-Cape-with-Resistive-Touch/img/putty-config.png)

account: debian, password: temppwd

![](https://files.seeedstudio.com/wiki/BBG-LCD-Cape-with-Resistive-Touch/img/BBG-start.png)

3. Modify configurations in `/boot/uEnv.txt`

```bash
sudo nano /boot/uEnv.txt
```

For 7-inch screen:

![](https://files.seeedstudio.com/wiki/BBG-LCD-Cape-with-Resistive-Touch/img/7-inch-config.png)

For 5-inch screen:

![](https://files.seeedstudio.com/wiki/BBG-LCD-Cape-with-Resistive-Touch/img/5-inch-config.png)

For display devices using BeagleBone® HDMI, uncomment `disable_uboot_overlay_video=1`

![](https://files.seeedstudio.com/wiki/BBG-LCD-Cape-with-Resistive-Touch/img/HDMI-config.png)

4. Reboot system. LED is blinking and you will see this window

![](https://files.seeedstudio.com/wiki/BeagleBone_Green_HDMI_Cape/img/Bbb_vnc.jpg)

## Resources

---------

- **[Schematic]** [Schematic files](https://statics3.seeedstudio.com/assets/file/bazaar/product/5INCH_BBG_00A2_SCH.pdf)

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

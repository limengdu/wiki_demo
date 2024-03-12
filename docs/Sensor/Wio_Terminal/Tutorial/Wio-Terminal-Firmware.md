---
description:  Wio Terminal Retro Gaming Firmware
title:  Wio Terminal Retro Gaming Firmware
keywords:
- Wio_terminal Tutorial
image: https://files.seeedstudio.com/wiki/wiki-platform/S-tempor.png
slug: /Wio-Terminal-Firmware
last_update:
  date: 1/31/2023
  author: jianjing Huang
---

# Wio Terminal Retro Gaming Firmware

<div align="center"><img src="https://static-cdn.seeedstudio.site/media/wysiwyg/wtretro.gif" /></div>

Here we released the initial factory firmware of the Wio Terminal, which is a simple game that you can play with Wio Terminal!

## Download the Complete Source Code

You can download the complete source code of the Wio Terminal Initial Firmware from [**this repo**](https://github.com/Seeed-Studio/Seeed_Arduino_Sketchbook/tree/master/examples/jumper) here.

- Download the entire repo

- Under `examples/jumper` location

## Dependant Libraries

### Installing the Adafruit ZeroTimer Libraries

1. Visit the [Adafruit_ZeroTimer](https://github.com/adafruit/Adafruit_ZeroTimer) repositories and download the entire repo to your local drive.

2. Now, the Adafruit ZeroTimer library can be installed to the Arduino IDE. Open the Arduino IDE, and click `sketch` -> `Include Library` -> `Add .ZIP Library`, and choose the `Adafruit_ZeroTimer` file that you've have just downloaded.

![InstallLibrary](https://files.seeedstudio.com/wiki/Wio-Terminal/img/Xnip2019-11-21_15-50-13.jpg)

:::note
Also depends on **1. Seeed_Arduino_LCD 2. Seeed_Arduino_FS 3. Seeed_Arduino_SFUD 4. Adafruit_ZeroDMA**, but these libraries are included in the Wio Terminal Board library. If having troubles, please update to the latest board library.
:::

## Arduino Instructions

There are **2 ways** of loading images of the gaming elements:

1. **Using Flash:**

      - This is the default method and loads the images into the flash.

      - Upload the code.

2. **Loading images using SD Card:**

      - Copy and paste `rgb332` file(with all the images) into the SD card.

      - If loading images from the SD card, you need to uncomment the macro `LOAD_IMAGE_SD`.

      - Upload the code.

Now, you can enjoy playing retro gaming using WIo Terminal again!

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

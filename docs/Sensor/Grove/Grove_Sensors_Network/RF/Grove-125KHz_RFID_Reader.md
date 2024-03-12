---
title: Grove - 125KHz RFID Reader
nointro:
keywords:
  - docs
  - docusaurus
image: https://wiki.seeedstudio.com/Grove-125KHz_RFID_Reader/
slug: /Grove-125KHz_RFID_Reader
last_update:
  date: 01/06/2022
  author: gunengyu
---

![](https://files.seeedstudio.com/wiki/Grove-125KHz_RFID_Reader/img/Grove-125KHz_RFID_Reader.jpg)

This Grove-125KHz RFID Reader is a module used to read uem4100 RFID card information with two output formats: Uart and Wiegand. It has a sensitivity with maximum 7cm sensing distance. There is also [the electronic brick version](https://www.seeedstudio.com/depot/electronic-brick-125khz-rfid-card-reader-p-702.html?cPath=52) of this module. It can help you with project like internet of thing and access control system.

And you should use the module below while using RFID reader:

- [RFID tag combo (125khz)](https://www.seeedstudio.com/depot/rfid-tag-combo-125khz-5-pcs-p-700.html?cPath=19_24)

[![](https://files.seeedstudio.com/wiki/common/Get_One_Now_Banner.png)](https://www.seeedstudio.com/depot/grove-125khz-rfid-reader-p-1008.html)

## Version

| Product Version | Changes | Released Date |
|-----------------|---------|---------------|
| Grove - 125KHz RFID Reader V1.0 | Initial | Oct 2015      |

## Specifications

|Parameter| Value/Range|
|:------|:------------------|
|Voltage| 4.75-5.25V|
|Working Frequency| 125 KHz|
|Sensing Distance(Max)|70mm|
|TTL Output| 9600 baudrate, 8 data bits, 1 stop bit, and no verify bit|
|Wiegand Output|26 bits Wiegand format, 1 even verify bit, 24 data bits, and 1 odd verify bit|

:::tip
    More details about Grove modules please refer to [Grove System](https://wiki.seeedstudio.com/Grove_System/)
:::

## Platforms Supported

| Arduino                                                                                             | Raspberry Pi                                                                                             |                                                                                                 |                                                                                                          |                                                                                                    |
|-----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| ![](https://files.seeedstudio.com/wiki/wiki_english/docs/images/arduino_logo.jpg) | ![](https://files.seeedstudio.com/wiki/wiki_english/docs/images/raspberry_pi_logo_n.jpg) | ![](https://files.seeedstudio.com/wiki/wiki_english/docs/images/bbg_logo_n.jpg) | ![](https://files.seeedstudio.com/wiki/wiki_english/docs/images/wio_logo_n.jpg) | ![](https://files.seeedstudio.com/wiki/wiki_english/docs/images/linkit_logo_n.jpg) |

:::caution
    The platforms mentioned above as supported is/are an indication of the module's software or theoritical compatibility. We only provide software library or code examples for Arduino platform in most cases. It is not possible to provide software library / demo code for all possible MCU platforms. Hence, users have to write their own software library.
:::

## Getting Started

:::note
    If this is the first time you work with Arduino, we firmly recommend you to see [Getting Started with Arduino](https://wiki.seeedstudio.com/Getting_Started_with_Arduino/) before the start.
:::

### Play With Arduino

#### Hardware

- **Step 1.** Prepare the below stuffs:

| Seeeduino V4.2 | Base Shield|  Grove - 125KHz RFID Reader |
|--------------|-------------|-----------------|
|![enter image description here](https://files.seeedstudio.com/wiki/Grove_Light_Sensor/images/gs_1.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Grove_Light_Sensor/images/gs_4.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Grove-125KHz_RFID_Reader/img/gr125k_01.jpg)|
|[Get One Now](https://www.seeedstudio.com/Seeeduino-V4.2-p-2517.html)|[Get One Now](https://www.seeedstudio.com/Base-Shield-V2-p-1378.html)|[Get One Now](https://www.seeedstudio.com/depot/grove-125khz-rfid-reader-p-1008.html)|

- **Step 2.** Connect Grove - 125KHz RFID Reader to port **D2** of Grove-Base Shield.
- **Step 3.** Plug Grove - Base Shield into Seeeduino.
- **Step 4.** Connect Seeeduino to PC via a USB cable.

![](https://files.seeedstudio.com/wiki/Grove-125KHz_RFID_Reader/img/RFID_reader.jpg)

:::note
 If we don't have Grove Base Shield, We also can directly connect Grove_Ultrasonic_Ranger to Seeeduino as below.
:::
| Seeeduino     | Grove - 125KHz RFID Reader |
|---------------|----------------------------|
| 5V            | Red                        |
| GND           | Black                      |
| D3            | White                      |
| D2            | Yellow                     |

#### Software

- **Step 1.** Copy the code into Arduino IDE and upload. If you do not know how to upload the code, please check [how to upload code](https://wiki.seeedstudio.com/Upload_Code/).

```c
/*
  link between the computer and the SoftSerial Shield
  at 9600 bps 8-N-1
  Computer is connected to Hardware UART
  SoftSerial Shield is connected to the Software UART:D2&D3
*/
 
#include <SoftwareSerial.h>
 
SoftwareSerial SoftSerial(2, 3);
unsigned char buffer[64];       // buffer array for data receive over serial port
int count = 0;                    // counter for buffer array
 
void setup()
{
    SoftSerial.begin(9600);     // the SoftSerial baud rate
    Serial.begin(9600);         // the Serial port of Arduino baud rate.
}
 
void loop()
{
    // if date is coming from software serial port ==> data is coming from SoftSerial shield
    if (SoftSerial.available())              
    {
        while(SoftSerial.available())               // reading data into char array
        {
            buffer[count++] = SoftSerial.read();      // writing data into array
            if(count == 64)break;
        }
        Serial.write(buffer, count);     // if no data transmission ends, write buffer to hardware serial port
        clearBufferArray();             // call clearBufferArray function to clear the stored data from the array
        count = 0;                      // set counter of while loop to zero
    }
    if (Serial.available())             // if data is available on hardware serial port ==> data is coming from PC or notebook
    SoftSerial.write(Serial.read());    // write it to the SoftSerial shield
}
void clearBufferArray()                 // function to clear buffer array
{
    // clear all index of array with command NULL
    for (int i=0; i<count; i++)
    {
        buffer[i]=NULL;
    }                  
}
```

- **Step 2.** Open the Serial Monitor, the card information can be displayed as shown below:

![](https://files.seeedstudio.com/wiki/Grove-125KHz_RFID_Reader/img/Read_Data_.jpg)

## Wiegand Mode

(Jumper Set to the Right two Pins)
You would need to select the jumper to "W" to enter this mode.
The [Wiegand demo code](https://files.seeedstudio.com/wiki/Grove-125KHz_RFID_Reader/res/RFID_Wiegand_INT.zip) for Seeeduino is designed to read Wiegand data in interrupt mode.

In Wiegand Mode, output data is formatted with 26bits including 24bits card info and 2 bits parity.

<table border={1}>
  <tbody><tr style={{fontWeight: 'bold'}}>
      <td width={20}>
        bit
      </td>
      <td width={20}>
        0
      </td>
      <td width={20}>
        1
      </td>
      <td width={20}>
        2
      </td>
      <td width={20}>
        3
      </td>
      <td width={20}>
        4
      </td>
      <td width={20}>
        5
      </td>
      <td width={20}>
        6
      </td>
      <td width={20}>
        7
      </td>
      <td width={20}>
        8
      </td>
      <td width={20}>
        9
      </td>
      <td width={20}>
        10
      </td>
      <td width={20}>
        11
      </td>
      <td width={20}>
        12
      </td>
      <td width={20}>
        13
      </td>
      <td width={20}>
        14
      </td>
      <td width={20}>
        15
      </td>
      <td width={20}>
        16
      </td>
      <td width={20}>
        17
      </td>
      <td width={20}>
        18
      </td>
      <td width={20}>
        19
      </td>
      <td width={20}>
        20
      </td>
      <td width={20}>
        21
      </td>
      <td width={20}>
        22
      </td>
      <td width={20}>
        23
      </td>
      <td width={20}>
        24
      </td>
      <td width={20}>
        25
      </td>
    </tr>
    <tr style={{fontSize: '90%'}} align="center">
      <td>
        -
      </td>
      <td>
        PE
      </td>
      <td colSpan={24} rowSpan={1}>
        D
      </td>
      <td>
        P0
      </td>
    </tr>
    <tr style={{fontSize: '90%'}} align="center">
      <td>
        -
      </td>
      <td>
        -
      </td>
      <td colSpan={12} rowSpan={1}>
        E
      </td>
      <td colSpan={12} rowSpan={1}>
        0
      </td>
      <td>
        -
      </td>
    </tr>
    <tr style={{fontSize: '90%'}} align="center">
      <td>
        -
      </td>
      <td>
        -
      </td>
      <td colSpan={8} rowSpan={1}>
        D2[7..0]
      </td>
      <td colSpan={8} rowSpan={1}>
        D1[7..0]
      </td>
      <td colSpan={8} rowSpan={1}>
        D0[7..0]
      </td>
      <td>
        -
      </td>
    </tr>
  </tbody></table>

- PE is even bit, PO is odd bit;
- E is the data bit which was involved in even, O is the data bit which was involved in odd;
- DX\[7..0\] is the data bit which correspond to Mifare@ Standard & Light card read only ID;

## FAQs

**Q1: How to convert the output to Card Number?**

A1: Please follow below steps.

- Take ID: 0009776930 for example:
- Card Number ID: 0009776930 ------- Decimalism [Start Bit(00) + Card Number(8 numbers)]
- Output: 0700952F229F ------------- Hex [[Start Bit(07h) + Card Number(8 numbers) + Checksum]
- The calculator for decimal and hex numbers is available online.

**Q2: How to read tags continuously?**

A2: The RFID reader can read tags continuously without any setting. Keep the tag 2.5-4 cm from the antenna, and the reader can read data continuously. And if the distance is below 2.5cm, the reader reads data once if not moving tags away.

## Resources

- **[Demo]** [Grove - 125KHz RFID Reader Demo](https://files.seeedstudio.com/wiki/Grove-125KHz_RFID_Reader/res/RFID_Wiegand_INT.zip)
- **[PDF]** [Declaration of conformity](https://files.seeedstudio.com/wiki/Grove-125KHz_RFID_Reader/res/CSTR140821808_Declaration%20of%20conformity.pdf)
- **[PDF]** [Test Report](https://files.seeedstudio.com/wiki/Grove-125KHz_RFID_Reader/res/CSTR140821808_test%20report.pdf)

## Projects

**Arduino Based Security Project Using Cayenne**: Arduino based Home Security Project. SMS/email alerts when intruder detected. Personalized messages for authorized personnel.

<iframe frameborder='0' height='327.5' scrolling='no' src='https://www.hackster.io/ArduinoBasics/arduino-based-security-project-using-cayenne-eb379b/embed' width='350'></iframe>

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

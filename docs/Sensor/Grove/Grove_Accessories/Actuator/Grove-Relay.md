---
title: Grove - Relay
nointro:
keywords:
  - docs
  - docusaurus
image: https://wiki.seeedstudio.com/Grove-Relay/
slug: /Grove-Relay
last_update:
  date: 01/09/2022
  author: gunengyu
---


<!-- <p style=":center"><img src="https://files.seeedstudio.com/wiki/Grove-Relay/img/Twig-Relay.jpg" /></p> -->

![](https://files.seeedstudio.com/wiki/Grove-Relay/img/Twig-Relay.jpg)

The Grove-Relay module is a digital normally-open switch. Through it, you can control circuit of high voltage with low voltage, say 5V on the controller. There is an indicator LED on the board, which will light up when the controlled terminals get closed.

<iframe width="800" height="450" src="https://www.youtube.com/embed/MwLEawbP0ZU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<p style={{}}><a href="https://www.seeedstudio.com/Grove-Relay-p-769.html" target="_blank"><img src="https://files.seeedstudio.com/wiki/Seeed-WiKi/docs/images/300px-Get_One_Now_Banner-ragular.png" /></a></p>

## Version

| Parameter     | V1.1     |V1.2     |
| :------------- | :------------- |:------------- |
| Product Release Date       | 27th Jan 2013       |9th June 2014|
|Operating Voltage|5V|3.3V~5V|
|Operating Current|60mA|100mA|
|Relay Life|100,000 Cycle|100,000 Cycle|
|Max Switching Voltage|250VAC/30VDC|250VAC/30VDC|
|Max Switching Current|5A|5A|

:::tip
    More details about Grove modules please refer to [Grove System](https://wiki.seeedstudio.com/Grove_System/)
:::
## Platforms Supported

| Arduino                                                                                             | Raspberry Pi                                                                                             |                                                                                                 |                                                                                                          |                                                                                                    |
|-----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| ![](https://files.seeedstudio.com/wiki/wiki_english/docs/images/arduino_logo.jpg) | ![](https://files.seeedstudio.com/wiki/wiki_english/docs/images/raspberry_pi_logo.jpg) | ![](https://files.seeedstudio.com/wiki/wiki_english/docs/images/bbg_logo.jpg) | ![](https://files.seeedstudio.com/wiki/wiki_english/docs/images/wio_logo.jpg) | ![](https://files.seeedstudio.com/wiki/wiki_english/docs/images/linkit_logo.jpg) |

:::caution
    The platforms mentioned above as supported is/are an indication of the module's software or theoritical compatibility. We only provide software library or code examples for Arduino platform in most cases. It is not possible to provide software library / demo code for all possible MCU platforms. Hence, users have to write their own software library.
:::
## Getting Started

### Play With Arduino

:::note
    If this is the first time you work with Arduino, we strongly recommend you to see [Getting Started with Arduino](https://wiki.seeedstudio.com/Getting_Started_with_Arduino/) before the start.
:::
#### Materials required

| Seeeduino V4.2 | Base Shield| Grove-Button **x2** |Grove-Relay|
|--------------|-------------|-----------------|-----|
|![enter image description here](https://files.seeedstudio.com/wiki/Grove_Light_Sensor/images/gs_1.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Grove_Light_Sensor/images/gs_4.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Grove-Relay/img/button_s.jpg)|![](https://files.seeedstudio.com/wiki/Grove-Relay/img/Thumbnail.jpg)|
|<a href="https://www.seeedstudio.com/Seeeduino-V4.2-p-2517.html">Get One Now</a>|<a href="https://www.seeedstudio.com/Base-Shield-V2-p-1378.html" >Get One Now</a>|<a href="https://www.seeedstudio.com/Grove-Button-p-766.html" target="_blank">Get One Now</a>|<a href="https://www.seeedstudio.com/Grove-Relay-p-769.html">Get One Now</a>| 

:::note
    **1** Please plug the USB cable gently, otherwise you may damage the port. Please use the USB cable with 4 wires inside, the 2 wires cable can't transfer data. If you are not sure about the wire you have, you can click [here](https://www.seeedstudio.com/Micro-USB-Cable-48cm-p-1475.html) to buy

    **2** Each Grove module comes with a Grove cable when you buy. In case you lose the Grove cable, you can click [here](https://www.seeedstudio.com/Grove-Universal-4-Pin-Buckled-20cm-Cable-%285-PCs-pack%29-p-936.html) to buy
:::
#### Hardware

- **Step 1.** Connect Grove-Relay to port **D4** of Grove-Base Shield.

- **Step 2.** Connect Grove-Button#1 to port **D2** of Grove-Base Shield, Connect Grove-Button#2 to port **D3** of Grove-Base Shield.

- **Step 3.** Plug Grove - Base Shield into Seeeduino.

- **Step 4.** Connect Seeeduino to PC via a Micro-USB cable.

![enter image description here](https://files.seeedstudio.com/wiki/Grove-Relay/img/button-relay.jpg)

:::note
    If we don't have the base shield, we also can directly connect the Grove-Relay and Grove-Button to Arduino board. Please follow below connection.
:::
| Grove-Relay | Arduino | Grove Cable|
|-------------|---------|-----------|
| GND         | GND     | Black|
| VCC         | 5V      |Red|
| SIG         | D4      |Yellow|

| Grove-Button#1 | Arduino |Grove Cable|
|----------------|---------|-------|
| GND            | GND     |Black|
| VCC            | 5V      |Red|
| SIG            | D2      |Yellow|

| Grove-Button#2 | Arduino |Grove Cable|
|----------------|---------|----|
| GND            | GND     |Black|
| VCC            | 5V      |Red|
| SIG            | D3      |Yellow|

#### Software

Here is a demo that shows you how to control a Grove - Relay with a Grove - Button. When one button gets pressed, the relay will close. When the other button gets pressed, the relay will open.

- **Step 1.** Open the Arduino IDE and copy the following code into a new sketch.

```
// Relay Control

void setup()
{
  pinMode(2, INPUT);
  pinMode(3, INPUT);
  pinMode(4, OUTPUT);
}

void loop()
{
  if (digitalRead(2)==HIGH)
  {
    digitalWrite(4, HIGH);
    delay(100);
  }
  if (digitalRead(3)==HIGH)
  {
    digitalWrite(4, LOW);
  }
}

```

- **Step 2.** Upload the demo. If you do not know how to upload the code, please check [How to upload code](https://wiki.seeedstudio.com/Upload_Code/).

Done uploading, if you press the button#1 the relay should be on; and if you press the button#2 the relay should be off.

### Play with Codecraft

#### Hardware

**Step 1.** Connect a Grove - Relay to port D4, connect two Grove - Button to port D2 and port D3 of a Base Shield.

**Step 2.** Plug the Base Shield to your Seeeduino/Arduino.

**Step 3.** Link Seeeduino/Arduino to your PC via an USB cable.

#### Software

**Step 1.** Open [Codecraft](https://ide.chmakered.com/), add Arduino support, and drag a main procedure to working area.

:::note
    If this is your first time using Codecraft, see also [Guide for Codecraft using Arduino](https://wiki.seeedstudio.com/Guide_for_Codecraft_using_Arduino/).
:::
**Step 2.** Drag blocks as picture below or open the cdc file which can be downloaded at the end of this page.

![cc](https://files.seeedstudio.com/wiki/Grove-Relay/img/cc_Relay.png)

Upload the program to your Arduino/Seeeduino.

:::success
    When the code finishes uploaded. Relay will turns on when you push the button connected to port D2, and it will turns off when you push the button connected to port D3.
:::
### Play With Raspberry Pi (With Grove Base Hat for Raspberry Pi)

#### Hardware

- **Step 1**. Things used in this project:

| Raspberry pi | Grove Base Hat for RasPi| Grove - Relay |
|--------------|-------------|-----------------|
|![enter image description here](https://files.seeedstudio.com/wiki/wiki_english/docs/images/rasp.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Grove_Base_Hat_for_Raspberry_Pi/img/thumbnail.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Grove-Relay/img/Thumbnail.jpg)|
|[Get ONE Now](https://www.seeedstudio.com/Raspberry-Pi-3-Model-B-p-2625.html)|[Get ONE Now](https://www.seeedstudio.com/Grove-Base-Hat-for-Raspberry-Pi-p-3186.html)|[Get ONE Now](https://www.seeedstudio.com/Grove-Relay-p-769.html)|

- **Step 2**. Plug the Grove Base Hat into Raspberry.
- **Step 3**. Connect the Grove - Relay to port 12 of the Base Hat.
- **Step 4**. Connect the Raspberry Pi to PC through USB cable.

![](https://files.seeedstudio.com/wiki/Grove-Relay/img/Relay_Hat.jpg)

:::note
    For step 3 you are able to connect the relay module to **any GPIO Port** but make sure you change the command with the corresponding port number.
:::
#### Software

:::note
     If you are using **Raspberry Pi with Raspberrypi OS >= Bullseye**, you have to use this command line **only with Python3**.
:::
- **Step 1**. Follow [Setting Software](https://wiki.seeedstudio.com/Grove_Base_Hat_for_Raspberry_Pi/#installation) to configure the development environment.
- **Step 2**. Download the source file by cloning the grove.py library.

```
cd ~
git clone https://github.com/Seeed-Studio/grove.py

```

- **Step 3**. Excute below commands to run the code.

```
cd grove.py/grove
python3 grove_relay.py 12

```

Following is the grove_relay.py code.

```python

from grove.gpio import GPIO


class GroveRelay(GPIO):
    def __init__(self, pin):
        super(GroveRelay, self).__init__(pin, GPIO.OUT)

    def on(self):
        self.write(1)

    def off(self):
        self.write(0)


Grove = GroveRelay


def main():
    import sys
    import time

    if len(sys.argv) < 2:
        print('Usage: {} pin'.format(sys.argv[0]))
        sys.exit(1)

    relay = GroveRelay(int(sys.argv[1]))

    while True:
        try:
            relay.on()
            time.sleep(1)
            relay.off()
            time.sleep(1)
        except KeyboardInterrupt:
            relay.off()
            print("exit")
            exit(1)            

if __name__ == '__main__':
    main()



```

:::success
    If everything goes well, you will be able to see the LED indicator blinking.
:::
You can quit this program by simply press ++ctrl+c++.

### Play With Raspberry Pi (with GrovePi_Plus)

#### Hardware

**Materials required**

| Raspberry pi | GrovePi_Plus| Grove-Button  |Grove-Relay|
|--------------|-------------|-----------------|-----|
|![enter image description here](https://files.seeedstudio.com/wiki/Grove_Ultrasonic_Ranger/img/rasp.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Grove_Ultrasonic_Ranger/img/Grovepi%2B.jpg)|![enter image description here](https://files.seeedstudio.com/wiki/Grove-Relay/img/button_s.jpg)|![](https://files.seeedstudio.com/wiki/Grove-Relay/img/Thumbnail.jpg)|
|<a href="https://www.seeedstudio.com/Raspberry-Pi-3-Model-B-p-2625.html" target="_blank">Get One Now</a>|<a href="https://www.seeedstudio.com/GrovePi%2B-p-2241.html" target="_blank">Get One Now</a>|<a href="https://www.seeedstudio.com/Grove-Button-p-766.html" target="_blank">Get One Now</a>|<a href="https://www.seeedstudio.com/Grove-Relay-p-769.html" target="_blank">Get One Now</a>|

- **Step 1.** Plug the GrovePi_Plus into Raspberry.

- **Step 2.** Connect the Grove-Relay to **D4** port of GrovePi_Plus.

- **Step 3.** Connect the Grove-Button to **D3** port of GrovePi_Plus.

- **Step 4.** Connect the Raspberry to PC via USB cable.

![enter image description here](https://files.seeedstudio.com/wiki/Grove-Relay/img/GrovePiPlus_Grove_relay.jpeg)

#### Software

If this is the first time you use GrovePi, please do this part step by step. If you are an old friend with GrovePi, you can skip **Step1** and **Step2**.

- **Step 1.** Setting Up The Software. In the command line, type the following commands:

:::note
     If you are using **Raspberry Pi with Raspberrypi OS >= Bullseye**, you **cannot use this command line**.
:::
```
sudo curl -kL dexterindustries.com/update_grovepi | bash

```

```
sudo reboot
```

```
cd /home/pi/Desktop
```

```
git clone https://github.com/DexterInd/GrovePi.git
```

For more detail about this part, please refer to [Setting Software](https://www.dexterindustries.com/GrovePi/get-started-with-the-grovepi/setting-software/).

- **Step 2.** Follow [Updating the Firmware](https://www.dexterindustries.com/GrovePi/get-started-with-the-grovepi/updating-firmware/) to update the latest firmware of GrovePi.

:::note
    We firmly suggest you to update the firmware, or for some sensors you may get errors.
:::
- **Step 3.** Run the following command to get the result.

:::note
     If you are using **Raspberry Pi with Raspberrypi OS >= Bullseye**, you have to use this command line **only with Python3**.
:::
```
cd /home/pi/Desktop/GrovePi/Software/Python/
sudo python3 grove_switch_relay.py
```

If you want to check the code, you can use the following command:

```
sudo nano grove_switch_relay.py

```

The code :

```python
# Raspberry Pi + Grove Switch + Grove Relay

import time
import grovepi
# Connect the Grove Switch to digital port D3
# SIG,NC,VCC,GND

switch = 3
# Connect the Grove Relay to digital port D4
# SIG,NC,VCC,GND

relay = 4
grovepi.pinMode(switch,"INPUT")
grovepi.pinMode(relay,"OUTPUT")
while True:
    try:
        if grovepi.digitalRead(switch):
            grovepi.digitalWrite(relay,1)
        else:
            grovepi.digitalWrite(relay,0)
            time.sleep(.05)
    except KeyboardInterrupt:
        grovepi.digitalWrite(relay,0)
        break
    except IOError:
        print "Error"
```

### Play With TI LaunchPad

Controlling other electronics (Relay)

![enter image description here](https://files.seeedstudio.com/wiki/Grove-Relay/img/Relay.jpg)

This example shows how to use the Grove-relay module to control larger load, i.e. a desk lamp light. A 3V voltage signal can cause the relay to switch on, allowing current to flow through the connected appliance.

```
/*
Relay
The basic Energia example.
This example code is in the public domain.
*/

#define RELAY_PIN 39

// the setup routine runs once when you press reset:
void setup() {
         pinMode(RELAY_PIN, OUTPUT); // initialize the digital pin as an output.
}

// the loop routine runs over and over again forever:
void loop() {
         digitalWrite(RELAY_PIN, HIGH); // turn the relay on (HIGH is the voltage level)
         delay(1000);   // wait for a second
         digitalWrite(RELAY_PIN, LOW);   // turn the relay o by making the voltage LOW
         delay(1000);   // wait for a second
}
```

## Schematic Online Viewer

<div className="altium-ecad-viewer" data-project-src="https://files.seeedstudio.com/wiki/Grove-Relay/res/Grove-Relay_Eagle_Files.zip" style={{borderRadius: '0px 0px 4px 4px', height: 500, borderStyle: 'solid', borderWidth: 1, borderColor: 'rgb(241, 241, 241)', overflow: 'hidden', maxWidth: 1280, maxHeight: 700, boxSizing: 'border-box'}}>
</div>


We have this part available in [geppetto](https://geppetto.seeedstudio.com/), easy modular electronic design with Seeed and Geppeto. Build it Now. [geppetto.seeedstudio.com](https://geppetto.seeedstudio.com/)

## Resources

- **[Eagle]** [Grove - Relay Schematic and PCB in Eagle format](https://files.seeedstudio.com/wiki/Grove-Relay/res/Grove-Relay_Eagle_Files.zip)
- **[PDF]** [Grove - Relay PCB in PDF format](https://files.seeedstudio.com/wiki/Grove-Relay/res/Grove%20-%20Relay%20PCB.pdf)
- **[PDF]** [Grove - Relay Schematic in PDF format](https://files.seeedstudio.com/wiki/Grove-Relay/res/Grove%20-%20Relay%20Schematic.pdf)
- **[Datasheet]** [HLS8-T73 Series Relay Datasheet](https://files.seeedstudio.com/wiki/Grove-Relay/res/Relay_Datasheet.pdf)
- **[Codecraft]** [CDC File](https://files.seeedstudio.com/wiki/Grove-Relay/res/Grove_Relay_CDC_File.zip)

## Projects


<table class="tg">
  <tr>
    <th class="tg-031e"><iframe frameborder='0' height='327.5' scrolling='no' src='https://project.seeedstudio.com/sodaqmoja/using-a-switch-to-open-and-close-a-relay-3329ec/embed' width='350'></iframe></th>
    <th class="tg-031e"><iframe frameborder='0' height='327.5' scrolling='no' src='https://project.seeedstudio.com/rei-vilo/private-iot-with-blynk-on-local-server-619926/embed' width='350'></iframe></th>
    <th class="tg-yw4l"><iframe frameborder='0' height='327.5' scrolling='no' src='https://project.seeedstudio.com/josephroberts/resinified-office-lock-0ca2eb/embed' width='350'></iframe></th>
  </tr>
</table>

**Relay Grove module**:

<iframe width="560" height="315" src="https://www.youtube.com/embed/DnHqh_Rupb8" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/JOsjUOI9FU8" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

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

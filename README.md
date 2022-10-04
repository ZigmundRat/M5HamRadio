# M5HamRadio
![basic](https://img.shields.io/badge/M5Stack-BASIC-blue)
![grey](https://img.shields.io/badge/M5Stack-GREY-blue)
![fire](https://img.shields.io/badge/M5Stack-FIRE-orange)
![core2](https://img.shields.io/badge/M5Stack-CORE2-green)
![aws](https://img.shields.io/badge/M5Stack-AWS-orange)

**First of all, many thanks to all my [donors](#donations)🙏🏻** 

The M5HamRadio project is a distrib of my stable HamRadio projects on M5Stack. It include 3 applications :

- ICSMeter (default application)
- ICMultiMeter
- DXTracker

All these applications are available for free and for all !

![ICSMeter](https://github.com/armel/M5HamRadio/blob/main/img/ICSMeter.png)
![ICMultiMeter](https://github.com/armel/M5HamRadio/blob/main/img/ICMultiMeter.png)
![DXTracker](https://github.com/armel/M5HamRadio/blob/main/img/DXTracker.png)

# Installation

## Prerequisites

You need an M5Stack, a micro SD card and a PC under Windows, Linux or MacOS, with the USB drivers installed and the M5Burner application version 3.0.0 (or higher).

## Micro SD card

Prepare and format a micro SD card in FAT32. This micro SD card will be used to put your configuration files and to place other firmwares.

## USB drivers installation

Please go to [download page](https://docs.m5stack.com/en/download) to download the USB driver that matches your operating system, and install it.

> Note: Core2 currently has two CP2104/CH9102F A USB chip version, users can install the drivers (CH9102 and CP210x) that are compatible with two ICs at the same time to ensure that the device drivers work normally.

## M5Burner installation

Please go to [download page](https://docs.m5stack.com/en/download) to download the M5Burner (version 3.0.0 or higher) that matches your operating system, and install it.

## Firmware flash

Connect your M5Stack to your PC.

Launch the M5Burner application and select the M5HamRadio firmware for your M5Stack model. Be aware, there is a version for M5Core (Basic, Grey, Fire, etc.) with buttons and a version for M5Core2 (Core2, AWS, etc.) with touch screen. 

Click on the blue Download button. Then click on the red Burn button.


## Settings

Using a plain text editor, you will create a file that should have the `.ini` extension. For example `IC705BT.ini` if you plain to use an IC-705, connected by Bluetooth. 

And now, here is what you will put in this `IC705BT.ini` :

```
; Icom Config
[icom]
icom_model = 705
icom_address = 0xA4
icom_connect = BT
icom_device = 30:31:7D:33:B2:58

; Wifi Config
[wifi]
wifi_ssid = YOUR_SSID
wifi_password = YOUR_PASSWORD

; Proxy Config
[proxy]
baud_rate = 115200
proxy_url = http://192.168.1.32
proxy_port = 1234

; Transverter Config
[transverter]
transverter_lo_1 = 116000000
transverter_lo_2 = 118000000
transverter_lo_3 = 404000000
transverter_lo_4 = 406000000
transverter_lo_5 = 9968000000

; Geolocation Config
[geolocation]
latitude = 48.848285
longitude = 2.2708201
```

Please, **take the time to adapt the values to your use** (Icom CI-V Address, Wifi SSID and password, and so on). It's important !

Here is an another example, if you're using an IC-7300, here is an another example with this `IC7300USB.ini` :

```
; Icom Config
[icom]
icom_model = 7300
icom_address = 0x94
icom_connect = USB
icom_device = /dev/ttyUSB0

; Wifi Config
[wifi]
wifi_ssid = YOUR_SSID
wifi_password = YOUR_PASSWORD

; Proxy Config
[proxy]
baud_rate = 115200
proxy_url = http://192.168.1.32
proxy_port = 1234

; Transverter Config
[transverter]
transverter_lo_1 = 116000000
transverter_lo_2 = 118000000
transverter_lo_3 = 404000000
transverter_lo_4 = 406000000
transverter_lo_5 = 9968000000

; Geolocation Config
[geolocation]
latitude = 48.848285
longitude = 2.2708201
```

> Important ! Important ! Important ! In USB mode, you need to use the [ICUSBProxy](https://github.com/armel/ICUSBProxy) version 0.0.6 or upper. 

Last, you will need to copy these files at the root of the micro SD card. That's all.

> You are able to put multiple .ini settings files for all your transceivers. I have got 3 of them for my IC-705 in BT mode, my IC-705 in USB mode and my IC-7300 in USB mode. I put them in this repository. 

# Usage

## Bin Loader

By default, M5Stack will start on ICSMeter firmware. At startup, you'll see the Bin Loader with a green gauge. You have 3 seconds to use the bottom middle button to select another firmware. Pressing the left or right button will bypass this step. 

## Ini Loader

You'll now see the Ini Loader with a blue gauge. You have 3 seconds to use the bottom middle button to select an `.ini` file. Select the `.ini` file you would like to load and... enjoy.

> The last valid .ini file will be load if no action on buttons.  

# Add more firmwares

Even if you already have 3 firmwares (ICSMeter, ICMultiMeter and DXTracker) after flashing your M5Stack via M5Burner, you can add other firmwares to the root of the micro SD card. 

Maybe it's time to test my last project : ICKeyer !

![ICKeyer](https://github.com/armel/M5HamRadio/blob/main/img/ICKeyer.png)

You find the firmwares of all these projects in this repository, of course for free ! 

# Disclaimers 

Because of the systematic plundering of my open source projects by a minority of unscrupulous people, taking advantage of my work to make money, I decided not to open the source code of these projects, for the moment.

I was insulted, threatened and blacklisted by these same people (resellers, youtubers, etc.). Some of them think they are little judges. And even if I know that the majority is behind me, that's enough 😔 

I believe in Open Source. But I believe too that a small part of the HamRadio community and some resellers are not yet mature enough to understand Open Source.

This being the case, I will make theses firmwares available for FREE and for ALL, but... 

These firmware is copyright (c) 2022 Armel FAUVEAU, that is to say me F4HWN and covered by the Berne Convention.

THESE FIRMWARES ARE NOT ALLOWED TO BE SOLD, IN ANY WAY. 

THESE FIRMWARES ARE PROVIDED "AS THEY ARE", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. 

IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THESE FIRMWARES OR THE USE OR OTHER DEALINGS IN THESE FIRMWARES.

# Credits
 
Many thanks to...

| Project             | Author                                                |  Link                                        |
|:------------------- | :---------------------------------------------------- | :------------------------------------------- |
| M5Stack             | [M5Stack](https://twitter.com/M5Stack)                | https://github.com/m5stack/M5Stack           |
| M5Stack-SD-Updater  | [Tobozo](https://twitter.com/TobozoTagada)            | https://github.com/tobozo/M5Stack-SD-Updater |
| FastLED             | FastLED                                               | https://github.com/FastLED/FastLED           |

Icom and the Icom logo are registered trademarks of Icom Incorporated (Japan) in Japan, the United States, the United Kingdom, Germany, France, Spain, Russia, Australia, New Zealand, and/or other countries.


# Donations

Special thanks to Rolf Schroeder DL8BAG, Brian Garber WB8AM, Matt B-Wilkinson M6VWM, Robert Agnew KD0TVP, Meinhard Frank Günther DL0CN, Johan Hansson SM0TSC, Tadeusz Pater VA7CPM, Frederic Ulmer F4ESO, Joshua Murray M0JMO, Mark Hammond N8MH, Angel Mateu Muzzio EA4GIG, Hiroshi Sasaki JL7KGW, Robert John Williams VK3IE, Mark Bumstead M0IAX, Félix Symann F1VEO, Patrick Ruhl DG2YRP, Michael Beck DH5DAX, Philippe Nicolas F4IQP, Timothy Nustad KD9KHZ, Martin Blanz DL9SAD, Edmund Thompson AE4TQ, Gregory Kiyoi KN6RUQ, Patrick Samson F6GWE and George Kokolakis SV3QUP for their donations. That’s so kind of them. Thanks so much 🙏🏻

If you find this project fun and useful then [buy me a glass of wine](https://www.paypal.me/F4HWN) 🍷 🤗 

You could use the code F4HWN in order to get 5% discount on the [M5Stack shop](https://shop.m5stack.com/?ref=LUxetaH4) 🎁

By the way, you can follow me on [Twitter](https://twitter.com/F4HWN) and post pictures of your installation with your M5Stack. It always makes me happy ;) 
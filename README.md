# Eveil_twin_Attack
ESP8266 EvilTwin & deauther all-in-one WiFi pen-testing tools.
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">Introduction</a>
      <ul>
        <li><a href="#disclaimer">Disclaimer</a></li>
        <li><a href="#conclusion">Conclusion</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li>
    <a href="#usage">Usage</a>
          <ul>
        <li><a href="#wiring">Wiring</a></li>
        <li><a href="#how-to-use">How to use</a></li>
        <li><a href="#customization">Customization</a></li>
      </ul>
    </li>
  </ol>
</details>
## Introduction
This project is developed for ESP8266 EvilTwin & deauther all-in-one WiFi pen-testing tools. The addition of `Display` integration, `RSSI` (received signal strength indication), several changes to `captive pages`, some fixing and adjustments to the `ESP8266 Boards Manager` to avoid `errors when deauthing`, and fixed other issues like the `captive portal not opening automatically`.

<i>The name of this project is inspired by Zero Two from Darling In The Franxx</i>

## Disclaimer
__IMPORTANT:__
- This tool is for testing and educational purposes
- Please use this tool for pen-testing purposes on your **own network or a network that you have permission for**
- All consequences of using this tool are the user's responsibility, so **DWYOR** (*Do With Your Own Risk*).

**I don't take any responsibility for what you do with this program in the future**

## Conclusion
This tool utilizes the deauth attack, which is used to disconnect devices from their WiFi network. After the client disconnects, this tool creates a clone SSID of the target WiFi.
After that EvilTwin will do his job.

# Getting Started
Here are some steps on how to compile this project and a guide for using it.

Untuk intstruksi dalam Bahasa Indonesia silahkan [__buka halaman ini__](https://github.com/shinyxn/ZeroTwin/tree/master/ESP8266-ZeroTwin%20Indonesian).

## Prerequisites
Here are the things you need to prepare:
- ESP8266 Development Board (NodeMCU, Wemos D1 Mini, etc)
- [Arduino IDE](https://www.arduino.cc/en/software)
- OLED 0.96” I2C Display (optional)
- Project board and some jumper cables (optional)

## Installation
- Open your Arduino IDE and add [**Deauther ESP8266 Boards**](https://raw.githubusercontent.com/SpacehuhnTech/arduino/main/package_spacehuhn_index.json) URL in the Additional Board Manager (`File` > `Preferences` > `Additional Board Manager URLs`), then add/paste this URL 
`https://raw.githubusercontent.com/SpacehuhnTech/arduino/main/package_spacehuhn_index.json`
<br>or you can refer to the [Spacehuhn Deauther ESP8266 Boards installation wiki](https://github.com/spacehuhntech/esp8266_deauther/wiki/Installation#compiling-using-arduino-ide)
- Go to `Tools` > `Board` > `Boards Manager`, search `deauther` and install `Deauther ESP8266 Boards`
- Go To `Tools` > `Board` > `Deauther ESP8266 Boards` (make sure it's `Deauther ESP8266 Boards`) and select your board. 
<br>Because I using NodeMCU, so I choose NodeMCU
- Download [this Eveiltwin projects](https://github.com/shinyxn/ZeroTwin/releases/), and open the `Eveil.ino` with Arduino IDE
- Go To `Tools` > `Manage Libraries`, then type `Adafruit SSD1306` in the search box and install the library. (make sure the library is `Adafruit SSD1306 by Adafruit`)
- Choose the correct COM port, click "`Upload`" to start the compiling process, and upload the source code to the ESP8266 board.
- You are done!

# Usage
**If you don't want to integrate with OLED, you can [skip](#how-to-use) the following step**

## Wiring

| OLED PIN      | ESP8266       |
| ------------- | ------------- |
|  VCC          |  `3.3V`       |
|  GND          |  `GND`        |
|  SCL          |  `D1`         |
|  SDA          |  `D2`         |

## How to use
- After completing the steps above, connect to the SSID named `Eveil` with password `123456` (you can customize it later)
- Wait until the portal page automatically opens, if not opening automatically, go to `192.168.4.1` in your favorite browser
- Select the target SSID
- Look on att4ck panel and click `Start Deauth`
- After a while, click `Start Evil-Twin`

The AP's mode will stopped and starting Evil-Twin mode

The OLED display will show the log and captured events of the tools. If the password entered in the captive portal is true, the clone SSID will disappear, and deauth automatically stop. Then connect to `Zero Twin v1.0`, the result will appear at the bottom of the pages.

## Customization
You can easily find some variables at the top of the source code, you can doing something such as changing the default SSID and password, customizing the captive portal, etc.

# Warning 
Don,t try this with your farmily and other people. This is only for educational purpous. You can try this only for learning.

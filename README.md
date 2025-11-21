# ESP32-CAM Photo to Telegram Bot

CSN150 – Advanced ESP32 Projects
Student: Alassane Camara

# Overview

This project demonstrates how to use an ESP32-CAM (AI Thinker) to capture a photo and send it directly to a Telegram bot using secure HTTPS communication.
The ESP32 listens for Telegram commands such as:

/photo → captures and sends a live picture

/flash → toggles the onboard flash LED

Documentation followed:
 https://randomnerdtutorials.com/telegram-esp32-cam-photo-arduino/

# Purpose

To learn how IoT devices communicate with cloud platforms.
This project introduces:

ESP32-CAM Wi-Fi configuration

Using Telegram Bot API

Sending images over HTTPS

Remote camera control

IoT automation concepts

# Equipment Used

ESP32-CAM AI Thinker

USB-C ESP32-CAM programmer (no jumper wires, no FTDI module used)

USB-C cable

Laptop with Arduino IDE installed

Wi-Fi network

Telegram app (web or mobile)

# Tools & Software

Arduino IDE 2.3.6

ESP32 Board Package

UniversalTelegramBot library

ArduinoJson library

Telegram BotFather

GitHub for documentation

# Steps I Followed
1. Create the Telegram Bot

Messaged BotFather in Telegram

Created esp32cam_photo_bot

Received Bot Token

Used @myidbot → /getid to get my Chat ID

Pressed Start on my bot to enable message reception

2. Prepare Arduino IDE

Installed ESP32 boards

Selected: AI Thinker ESP32-CAM

Installed required libraries:

UniversalTelegramBot

ArduinoJson

3. Connect the ESP32-CAM 

- Plugged the ESP32-CAM directly into the USB-C programmer
- Connected the USB-C cable to my laptop
- Programmer automatically handled upload mode

4. Configure ESP32-CAM Credentials

Updated in the code:

const char* ssid = "A*****2";
const char* password = "******";

String BOTtoken = "<my-bot-token>";
String CHAT_ID = "<my-chat-id>";

5. Upload the Sketch

Selected the correct COM port

Pressed Upload

Upload succeeded on first try

6. Test Telegram Commands

In the Telegram chat:

/start → bot sent welcome message

/photo → ESP32-CAM captured and sent a photo

/flash → toggled the flash LED

Everything worked successfully.

# Problems / Solutions
Issue — ESP32-CAM didn’t respond at first

Cause: wrong board selected
Fix: chose AI Thinker ESP32-CAM

# Final Report

This project was successful.
The ESP32-CAM was able to:

Connect to Wi-Fi

Communicate with the Telegram API

Receive commands

Capture photos

Send images securely over HTTPS

This assignment helped me understand IoT-cloud integration, API communication, and ESP32-CAM camera configuration.
Using a USB-C programmer made the process easier compared to traditional FTDI wiring.

ESP32-CAM Photo to Telegram Bot

CSN150 – Advanced ESP32 Projects
Student: Alassane Camara

Overview

This project uses an ESP32-CAM (AI Thinker) to capture a live photo and send it to a Telegram bot using the Telegram Bot API over HTTPS.
The ESP32-CAM listens for Telegram commands:

/photo – captures and sends a picture

/flash – toggles the flash LED

Documentation followed:
https://randomnerdtutorials.com/telegram-esp32-cam-photo-arduino/

Purpose

This assignment demonstrates how IoT devices communicate with cloud APIs. It covers:

ESP32-CAM Wi-Fi configuration

Using the Telegram Bot API

Sending images over HTTPS

Remote camera command execution

Basic IoT automation and cloud communication concepts

Equipment Used

ESP32-CAM AI Thinker

USB-C ESP32-CAM programmer (no jumper wires, no FTDI module)

USB-C cable

Laptop with Arduino IDE installed

Wi-Fi network

Telegram application (Web or Mobile)

Tools & Software

Arduino IDE 2.3.6

ESP32 Board Package

UniversalTelegramBot library

ArduinoJson library

Telegram BotFather

GitHub for documentation

ChatGPT (GPT-5.1) for troubleshooting assistance

Steps I Followed
1. Created the Telegram Bot

Opened Telegram

Searched for BotFather

Used the /newbot command

Created the bot and received the Bot Token

2. Obtained My Chat ID (Actual Method Used)

Instead of using @myidbot, I retrieved my Chat ID directly through the Telegram API:

Opened a chat with my bot

Typed “hello”

Opened the link:

https://api.telegram.org/bot<my_token>/getUpdates


Refreshed the page

Copied the "chat":{"id": ... } value

3. Prepared the Arduino IDE

Installed the ESP32 board package

Selected the board: AI Thinker ESP32-CAM

Installed the required libraries:

UniversalTelegramBot

ArduinoJson

4. Connected the ESP32-CAM

No FTDI programmer or jumper wires were used.
I connected the ESP32-CAM directly using a USB-C ESP32-CAM programmer:

Plugged the ESP32-CAM into the USB-C programmer

Connected the programmer to my laptop

The programmer handled upload mode automatically

5. Entered My Wi-Fi and Telegram Credentials

Edited the sketch:

const char* ssid = "A*****2";
const char* password = "******";
String BOTtoken = "<my-bot-token>";
String CHAT_ID = "<my-chat-id>";

6. Uploaded the Code

Selected the correct COM port

Clicked Upload

The ESP32-CAM reset properly, and the upload succeeded

7. Tested Telegram Commands

Inside the bot conversation:

/start – bot sent the welcome message

/photo – the ESP32-CAM captured and sent a photo

/flash – toggled the onboard flash LED

All commands worked successfully.

Problems / Solutions
Problem: ESP32-CAM did not respond at first

Cause: Incorrect board selection in Arduino IDE
Solution: Changed board to “AI Thinker ESP32-CAM”

Final Report

This project was completed successfully. The ESP32-CCAM connected to Wi-Fi, communicated securely with the Telegram API, and responded to Telegram commands by capturing and sending live photos. The assignment demonstrated practical IoT-to-cloud integration, API communication, HTTPS requests on microcontrollers, and basic camera functionality using the ESP32-CAM.
Using a USB-C programmer made the upload process simple and reliable without jumper wires or FTDI hardware.

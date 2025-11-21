# ESP32-CAM Photo to Telegram Bot

**CSN150 – Advanced ESP32 Projects**
**Student:** Alassane Camara

---

## Overview

This project uses an ESP32-CAM (AI Thinker) to capture a photo and send it to a Telegram bot using the Telegram Bot API over HTTPS. The ESP32-CAM responds to the following commands:

* `/photo` – captures and sends a picture
* `/flash` – toggles the flash LED

Documentation followed:
[https://randomnerdtutorials.com/telegram-esp32-cam-photo-arduino/](https://randomnerdtutorials.com/telegram-esp32-cam-photo-arduino/)

---

## Purpose

This assignment demonstrates how IoT devices communicate with cloud APIs. It includes:

* ESP32-CAM Wi-Fi configuration
* Interacting with the Telegram Bot API
* Sending images through HTTPS
* Remote camera control
* Understanding IoT automation concepts

---

## Equipment Used

* ESP32-CAM AI Thinker
* USB-C ESP32-CAM programmer (no jumper wires, no FTDI module)
* USB-C cable
* Laptop running Arduino IDE
* Wi-Fi network
* Telegram application (Web or Mobile)

---

## Tools & Software

* Arduino IDE 2.3.6
* ESP32 Board Package
* UniversalTelegramBot library
* ArduinoJson library
* Telegram BotFather
* GitHub for documentation

---

## Steps I Followed

### 1. Created the Telegram Bot

* Opened Telegram
* Searched for **BotFather**
* Used the `/newbot` command
* Created the bot and received the Bot Token

### 2. Obtained My Chat ID (Using the Telegram API)

I retrieved my Chat ID using the API method:

1. Opened a chat with my Telegram bot
2. Sent the message: `hello`
3. Opened this link in the browser:

   ```
   https://api.telegram.org/bot<my_token>/getUpdates
   ```
4. Refreshed the page
5. Copied the `"chat":{"id": ... }` value

### 3. Prepared the Arduino IDE

* Installed the ESP32 board package
* Selected the correct board: **AI Thinker ESP32-CAM**
* Installed required libraries:

  * UniversalTelegramBot
  * ArduinoJson

### 4. Connected the ESP32-CAM

No FTDI module or jumper wires were used. The setup was:

* Inserted the ESP32-CAM into the USB-C programmer
* Connected the USB-C cable to my laptop
* Programmer automatically handled upload mode

### 5. Entered Wi-Fi and Bot Credentials

Updated the following lines in the sketch:

```
const char* ssid = "A*****2";
const char* password = "******";
String BOTtoken = "<my-bot-token>";
String CHAT_ID = "<my-chat-id>";
```

### 6. Uploaded the Code

* Selected the correct COM port
* Clicked **Upload**
* The ESP32-CAM reset successfully and the upload completed

### 7. Tested Telegram Commands

Inside the Telegram bot conversation:

* `/start` – bot sent the welcome message
* `/photo` – ESP32-CAM captured and sent a picture
* `/flash` – toggled the flash LED

Everything worked correctly.

---

## Problems / Solutions

### ESP32-CAM not responding at first

**Cause:** Incorrect board selected.
**Solution:** Switched to **AI Thinker ESP32-CAM** in Arduino IDE.

---

## Final Report

The ESP32-CAM successfully connected to Wi-Fi, communicated with the Telegram API, and responded to commands by capturing and sending live images. This assignment demonstrated IoT-to-cloud communication, HTTPS API usage, and ESP32-CAM camera functionality. Using a USB-C programmer made the upload process simple and reliable with no need for jumper wires or FTDI hardware.

---

## Screenshots

### ESP32-CAM Telegram Photo

<img width="960" height="1020" alt="telegram_serial_monitor" src="https://github.com/user-attachments/assets/449a9ed6-49c4-4fe0-b9cf-41ba3b454f5b" />

### Telegram Bot Receiving Photo

<img width="1920" height="1020" alt="telegram_bot" src="https://github.com/user-attachments/assets/67883cfd-faf0-4520-ba07-40bbac7f78ff" />


---

## GitHub Repository

[https://github.com/Alassane427/ESP32CAM-Telegram-Photo](https://github.com/Alassane427/ESP32CAM-Telegram-Photo)

#  RFID-Based Toll Tax System using Arduino

## 📌 Overview

This project implements a **smart toll collection system** using **RFID technology** and **Arduino Uno**. The system automates toll gate access by reading RFID cards attached to vehicles, verifying balance, and operating a servo-controlled barrier. A built-in recharge mechanism simulates a prepaid system, and the status is displayed on an OLED screen.

---

## 🎯 Features

- ✅ Automatic toll access for registered RFID cards
- 💰 Balance deduction and low balance warnings
- 🚫 Access denial for unregistered or insufficient balance tags
- 🔁 Recharge function to top up card balance
- 📟 OLED display showing real-time access and balance info
- ⚙️ Fully implemented on breadboard and simulated using Arduino IDE

---

## 🧰 Hardware Components

| Component            | Description                         |
|----------------------|-------------------------------------|
| Arduino Uno          | Microcontroller board               |
| RC522 RFID Reader    | Reads RFID tag UID                  |
| RFID Tags/Cards      | Used for vehicle identification     |
| SG90 Servo Motor     | Simulates gate barrier movement     |
| OLED Display (SSD1306)| Displays status and balance info   |
| Push Button          | Used for recharging balance         |
| Breadboard & Wires   | Circuit prototyping                 |

---

## 🔄 Working Principle

1. RFID reader continuously scans for tags.
2. On detecting a tag:
   - **Valid Tag + Sufficient Balance** → Access granted, gate opens, balance deducted.
   - **Valid Tag + Low Post-Deduction Balance** → Access granted with warning.
   - **Invalid Tag or Insufficient Balance** → Access denied.
3. Recharge button resets the tag balance to a maximum preset value.
4. OLED display provides feedback at every step.

---
## 🧠 Libraries Used

- `SPI.h` – For SPI communication with RC522
- `MFRC522.h` – RFID reader library
- `Wire.h` – I2C communication
- `Adafruit_GFX.h` – OLED graphics
- `Adafruit_SSD1306.h` – OLED driver
- `Servo.h` – Servo motor control

---

### How to Upload:
1. Open Arduino IDE.
2. Install all required libraries via Library Manager.
3. Connect Arduino Uno.
4. Upload the code to your board.

---

## 📊 Testing & Results

| Parameter          | Value           |
|--------------------|------------------|
| Detection Range    | 3–5 cm           |
| Gate Open Time     | 3 seconds        |
| Display Response   | Instantaneous    |
| Error Rate         | 0% (for valid tags) |
| Recharge Time      | Instant          |

Tested scenarios include:
- Access with valid cards
- Denied access for unknown/invalid cards
- Proper low balance and recharge flow

---

## 📦 Future Improvements

- Integrate UPI/digital payment gateways
- Add real-time data logging via IoT
- Add support for dynamic pricing

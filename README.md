# ChronoFlex Adaptive FPGA Timekeeper on BASYS3

[GitHub Repo](https://github.com/dhanush-271/ChronoFlex-Adaptive-FPGA-Timekeeper_Basys3)

👤 **Author**: Kothapalli Dhanush

---

## 🚀 Project Overview

This project involves designing and implementing a digital multifunction watch on a Basys3 FPGA board using Verilog. The system supports:

- Real-Time Clock (RTC)
- Time and Date Editing
- Countdown Timer
- Stopwatch
- Alarm System
- Date Display (with long press)

---

## 🧭 States of Operation

### 1. Real-Time Clock (RTC)
- Default mode
- Displays current time in 24-hour format
- Updates every second

### 2. Edit Mode
- Set **Time** and **Date**
- Use `edit_shift` to toggle (hours/minutes/day/month)
- `inc` to increment fields
- Blinking digits indicate active edit

### 3. Timer Mode
- Countdown from user-set duration (max 59:59)
- `start_stop` toggles timer
- `edit_shift` and `inc` to set duration

### 4. Stopwatch Mode
- Activated after Timer
- Measures elapsed time from 00:00 to 59:59
- `start_stop` to run/pause
- `reset` to clear

### 5. Alarm Mode
- Follows Stopwatch mode
- Alarm can be toggled ON/OFF
- Time editable in stop state
- When triggered, **LED[15] (buzzer_led)** turns on
- Stop alarm via `start_stop` button

### 6. Date Display
- Hold `inc` in RTC mode to display date (DD/MM)
- Editable in Edit mode when `edit_place` is 2 or 3

---

## ⌨️ Board Constraints

### 🔘 Push Buttons
- `reset`: Resets values (mode-specific)
- `mode`: Cycle through all states
- `edit_shift`: Toggle fields (hours/minutes/date)
- `inc`: Increment selected field / long press to show date
- `start_stop`: Start/stop timer, stopwatch or alarm

### 💡 LEDs
- `mode_value`: Indicates current mode (3-bit)
- `buzzer_led (LED[15])`: Lights when alarm is triggered; acts as visual buzzer

### 🔢 Seven-Segment Display
| Mode           | Display                        |
|----------------|--------------------------------|
| **Clock**      | HH:MM (long press → DD/MM)     |
| **Edit**       | HH:MM or DD/MM (blinking)      |
| **Timer**      | MM:SS (editable before start)  |
| **Stopwatch**  | MM:SS (resets with `reset`)    |
| **Alarm**      | HH:MM (editable in stop state) |

---

## 📸 Output Demo

🔗 [Watch Demo on Google Drive](https://drive.google.com/file/d/1fSnPEZKsoybbPT9YLK6JAlKtDaetjgsl/view?usp=sharing)

---

Feel free to fork, star, or contribute to the project! 🚀



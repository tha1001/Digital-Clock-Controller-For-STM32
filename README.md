🕒 STM32 Digital Clock Controller (LCD Based)

A simple and practical digital clock project using STM32F103C8T6 and 16x2 LCD display.
This project allows you to set and adjust hours, minutes, and seconds using buttons.

✨ Features
⏰ Real-time digital clock display
🖥️ LCD 16x2 interface support
🔘 Button-based time adjustment
⚙️ Easy configuration with STM32CubeMX
📟 Lightweight and beginner-friendly code
🧰 Hardware Requirements
STM32F103C8T6 (Blue Pill)
16x2 LCD Display
Push Buttons × 3
Breadboard + Jumper Wires
USB to Serial / ST-Link Programmer
📌 Pin Configuration (STM32CubeMX)
GPIO Outputs:
PA0 → PA5 (LCD data/control pins)
GPIO Inputs:
PB0 → Button (Decrease)
PB1 → Button (Increase)
PB3 → Mode Select
📁 Project Setup
1. LCD Library Setup
Download lcd.c and lcd.h
Create a folder named:
LCD
Paste both files inside it
2. STM32CubeMX Configuration
Select board: STM32F103C8T6
Configure GPIO pins as shown above
Generate code
3. Add Library to Project

Copy the LCD folder into:

ProjectName/Core/Src

Then:

Open your IDE (IAR / Keil / STM32CubeIDE)
Right click on DRIVERS
Create new folder → LCD
Add files:
lcd.c
lcd.h
🧠 Main Code Integration
🔹 Add Includes

Inside:

/* USER CODE BEGIN Includes */

Add:

#include "LCD/lcd.h"
#include <stdio.h>

🔹 Add Variables in main
char data[17];
uint32_t sanyeh;
uint32_t daghyghe;
uint32_t saat;
uint8_t a = 1;
🔹 Initialization (Before while(1))
lcd_init();
lcd_clear();
a = 1;
🔁 Main Loop Logic

Inside while (1):

Display time on LCD
Read button inputs
Switch between:
Hours ⏰
Minutes ⏱️
Seconds ⌛
Increase / decrease selected value
🚀 How It Works
Button 1 → Switch between time fields
Button 2 → Increase value
Button 3 → Decrease value
LCD highlights selected field
📷 Output Example
12 : 45 : 30
      __
📌 Notes
Add small delays to avoid button bouncing
Ensure LCD wiring is correct
Initialize all variables properly
🎯 Result

After setup, you will have a fully working digital clock system on STM32 with LCD control 🎉

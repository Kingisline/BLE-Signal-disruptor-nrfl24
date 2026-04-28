# Esp32 Bluetooth Jammer


## Introduction

### This project demonstrates a Bluetooth jammer built using an ESP32 microcontroller and an NRF24L01 wireless module. The system works by transmitting interference signals in the 2.4 GHz frequency range to disrupt nearby Bluetooth communication. This project is created for educational and research purposes to understand wireless communication, signal interference, and RF security concepts.



## Identify Your USB-to-UART Chip
Look at the small square chip near the micro-USB port on your ESP32. It is usually one of two types:

1. **CP2102 (Silicon Labs)**: A small square chip.
2. **CH340 (WCH)**: A slightly larger rectangular chip.

## Download and Install the Drivers
### For CP2102 Chips:

1. Visit the [Silicon Labs Official Website.](https://www.silabs.com/software-and-tools/usb-to-uart-bridge-vcp-drivers?tab=downloads)
2. Download the **CP210x Universal Windows Driver.**
3. Extract the zip file and right-click on silabser.inf, then select **Install.**

### For CH340 Chips:
1. Download the driver from the [Gojo:Tronincs](https://sparks.gogo.co.nz/ch340.html)
2. Run the .exe file and click **Install.**

## Esp32 Flasher

[click Here](https://kingisline.github.io/BLE-Signal-disruptor-nrfl24/)



## Circuit Diagram
<img width="320" height="309" alt="Image" src="https://github.com/user-attachments/assets/fd34261c-9d2b-485e-8e91-db47975e62dc" />

## PINS TO ATTACH NRF24L01 TO ESP32
### FOR DUAL/TWO NRF24L01
>HSPI= SCK = 14, MISO = 12, MOSI = 13, CS = 15 , CE = 16

 > VSPI= SCK = 18, MISO =19, MOSI = 23 ,CS =21 ,CE = 22

### FOR SINGLE/ONE NRF24L01 YOU CAN CHOOSE BETWEEN HSPI OR VSPI
> VSPI= SCK = 18, MISO =19, MOSI = 23 ,CS =21 ,CE = 22

> HSPI= SCK = 14, MISO = 12, MOSI = 13, CS = 15 , CE = 16
### SWITCH PIN (OPTIONAL)
> PIN 33 OF YOUR ESP32 

## HOW YOU ATTACH CAPACITOR LOOK OUT FOR POLAROITY SIGNS `- +`
<img width="785" height="487" alt="Image" src="https://github.com/user-attachments/assets/f28d8e64-1049-4094-9046-c3a431a95265" />

## Verify the Connection

Once installed, connect your ESP32 to your PC and follow these steps:

Right-click the **Start Button** and select **Device Manager.**
Expand the **Ports (COM & LPT) section.**
You should see "Silicon Labs CP210x..." or "USB-SERIAL CH340" followed by a COM port number (e.g., **COM3).**
> Note: If you see "Unknown Device" or a yellow warning triangle, the driver was not installed correctly or your USB cable is "Charge-only."

## Setting Up Arduino IDE for ESP32
By default, the Arduino IDE only supports Arduino boards. You must add the ESP32 board definitions manually.

Open Arduino IDE and go to **File > Preferences.**
In the **Additional Boards Manager URLs** field, paste this link: https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
Click **OK.**
Go to **Tools > Board > Boards Manager.**
Search for **"ESP32"** and click **Install** on the version by **Espressif Systems.**


## Uploading Your First Sketch
Now that the drivers and software are ready, let's test it:

1. Go to Tools > Board and select "DOIT ESP32 DEVKIT V1" (or your specific model).
2. Go to Tools > Port and select the COM port you found in Step 3
3. Open the Blink Example: File > Examples > 01.Basics > Blink.
4. Click Upload.

## The "Boot" Button Trick
Some ESP32 boards do not enter "Upload Mode" automatically. If you see **"Connecting........_____"** in the console and then an error, do this:

Hold down the **BOOT** (or IO0) button on the ESP32.
Click **Upload** in the IDE.
When you see "Writing at 0x00001...", release the button.


## Troubleshooting Common Setup Errors
>**Error: "A fatal error occurred:** Failed to connect to ESP32": Check your USB cable. Many micro-USB cables used for charging phones do not have data wires. Try a different cable.

>**COM Port Not Appearing:** Ensure the ESP32 is getting power (the red LED should be on). If it's on but no port appears, try a different USB port on your computer.

>**Compilation Error:** Ensure you selected the correct ESP32 board model from the Tools menu.

## Conclusion
Setting up the ESP32 is a one-time process. Once the drivers are installed and the board manager is configured, you are ready to dive into the world of Wi-Fi-connected sensors, web servers, and remote-controlled robotics!

## SPECIAL THANKS

* [ATOMNFT](https://github.com/ATOMNFT) -  HEADER AND DONATIONS
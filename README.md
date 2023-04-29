# esphome-8bit-wiegand-reader-with-timeout
An ESPHome configuration file with a built-in brute-force prevention timer for communicating with various wiegand readers

# Why?
Some Wiegand readers use non-"standard" communication protocols. (Worth noting is that there is no "standard" per se, but some protocols are more common than others.)

This keypad is one such device. 
<img src="/intended_keypad.png"  width=50% height=50%>

It uses an 8-bit communication protocol for keystrokes, with the numbers pressed expressed by the 4 LSB.

This ESPHome configuration aims to provide support for such devices. It also has the bonus feature of internally limiting the RFID/keypad read frequency to once every 5 seconds after the initial read, in order to limit the success rate of brute-force attacks.

# How-Tos
Paste the configuration file into your ESPHome interface. Change the various parameters as needed.

# Known Issues.
- The device may not respond if the ESP32 was reset by an OTA update, this seems to be a keypad specific issue, and may not happen with your hardware. Power-cycling the device can usually fix this.
- Sometimes, ESPHome compiles the code just fine, but the binary file may not link. When this happens, use the "Clean Build Files" option in ESPHome and compile again.

# Experiencing Problems?
Feel free to open a GitHub issue. Please provide a log file of the reader's output and clearly describe the issue that you are facing. I will try my best to assist.

:3

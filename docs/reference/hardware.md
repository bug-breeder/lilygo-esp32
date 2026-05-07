# Hardware Reference

This page records the working hardware model for the LilyGO T-Embed CC1101 Plus course. Recheck official sources before changing pin maps, board environments, or firmware assumptions.

## Board

- Product: LilyGO T-Embed CC1101 Plus.
- MCU: ESP32-S3 dual-core LX7.
- Flash: 16MB.
- PSRAM: 8MB.
- Display: 1.9 inch ST7789V IPS color TFT LCD over SPI.
- Wireless: Wi-Fi 802.11 b/g/n and BLE 5 from ESP32-S3.
- Sub-GHz radio: CC1101.
- 2.4GHz radio on Plus variant: nRF24L01 module.
- NFC/RFID: PN532 module over I2C.
- IR: transmit and receive support.
- Power observation: battery voltage detection is listed on IO04 by LilyGO.

## Source Links

- LilyGO product page: https://lilygo.cc/en-us/products/t-embed-cc1101-plus
- LilyGO wiki: https://wiki.lilygo.cc/get_started/en/Wearable/T-Embed-CC1101/T-Embed-CC1101.html
- LilyGO GitHub examples: https://github.com/Xinyuan-LilyGO/T-Embed-CC1101
- Bruce firmware: https://github.com/BruceDevices/firmware

## Course Assumptions

- The device currently has Bruce installed.
- The first course stage does not replace firmware.
- PlatformIO is the preferred build workflow for later firmware lessons.
- Exact board environment names must be verified from the selected upstream source before building or flashing.

## User Observation Log

Record the physical device details here before flashing or opening the case:

- Purchase date:
- Board label or silkscreen:
- Bruce version:
- Boot behavior:
- Battery behavior:
- SD card present:
- USB serial port name:
- Notes:

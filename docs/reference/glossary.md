# Glossary

## Embedded Basics

- **ESP32-S3:** Espressif microcontroller used by the LilyGO T-Embed CC1101 Plus.
- **Firmware:** Software that runs directly on the device.
- **Flash:** Non-volatile storage used for firmware and persistent data.
- **PSRAM:** External RAM used for larger runtime buffers.
- **GPIO:** General-purpose input/output pins.
- **I2C:** Two-wire bus commonly used for sensors and modules such as PN532.
- **SPI:** High-speed bus commonly used for displays, SD cards, and radio modules.
- **UART/Serial:** Communication channel used for logs, shells, and flashing workflows.
- **Boot mode:** Device state used to receive new firmware over USB/serial.

## Board and Firmware

- **Bruce:** ESP32 firmware focused on security research features and multi-device support.
- **PlatformIO:** Build and project tool commonly used for ESP32 Arduino and embedded projects.
- **Board environment:** A PlatformIO configuration entry that selects board, framework, flags, libraries, and build settings.
- **WebUI:** Browser-based interface exposed by firmware for file or device interaction when supported.

## Protocols and Modules

- **CC1101:** Sub-GHz RF transceiver used for learning radio concepts and owned-device experiments.
- **nRF24L01:** 2.4GHz transceiver module included on the Plus variant.
- **PN532:** NFC/RFID controller used for reading and writing compatible tags.
- **IR:** Infrared light communication commonly used by remote controls.
- **BLE:** Bluetooth Low Energy.
- **Wi-Fi scanning:** Discovery of nearby Wi-Fi networks or device metadata without joining or attacking them.

## Security Terms

- **White-hat:** Authorized security learning or testing intended to improve safety.
- **Authorization:** Explicit permission to test a device, system, or environment.
- **Receive-only:** Observing signals without transmitting.
- **Replay:** Re-sending a previously captured signal; allowed only for owned devices in scoped labs.
- **Jamming:** Deliberate interference or disruption; prohibited in this course.

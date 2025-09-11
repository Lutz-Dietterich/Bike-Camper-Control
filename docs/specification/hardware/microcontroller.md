| Feature              | ESP8266                 | ESP32                    | Raspberry Pi Pico    |
|----------------------|-------------------------|--------------------------|----------------------|
| **CPU**              | Single-core Tensilica   | Dual-core Tensilica      | Dual-core ARM Cortex |
|                      | Xtensa LX106            | Xtensa LX6               | M0+                  |
| **Frequency**        | Up to 160 MHz           | Up to 240 MHz            | Up to 133 MHz        |
| **RAM**              | 32 KiB instruction      | 520 KiB SRAM             | 264 KiB SRAM         |
|                      | 80 KiB user data        |                          |                      |
| **GPIO Pins**        | 17                      | 36                       | 26                   |
| **Analog Input**     | 1 channel (10-bit ADC)  | 18 channels (12-bit ADC) | 3 channels (12-bit ADC)|
| **Wi-Fi**            | 802.11 b/g/n            | 802.11 b/g/n             | None                 |
| **Bluetooth**        | None                    | BLE 4.2 and BR/EDR       | None                 |
| **USB**              | None (requires UART     | None (requires UART      | 1 x Micro USB        |
|                      | for programming)        | for programming)         | (supports USB 1.1)   |
| **Storage**          | Flash (size varies)     | Flash (size varies)      | Flash (2 MB onboard) |
| **Power Consumption**| Low                     | Moderate                 | Low                  |
| **Price Range**      | $                       | $$                       | $                    |
| **Documentation**    | [ESP8266](https://docs.espressif.com/projects/esp8266-rtos-sdk/en/latest/) | [ESP32](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/) | [Raspberry Pi Pico](https://datasheets.raspberrypi.org/pico/pico-datasheet.pdf) |

## ESP8266

The ESP8266 is a low-cost Wi-Fi microchip with full TCP/IP stack and microcontroller capability produced by Espressif Systems. The chip first came to the attention of western makers in August 2014 with the ESP-01 module, made by a third-party manufacturer, AI-Thinker. This small module allows microcontrollers to connect to a Wi-Fi network and make simple TCP/IP connections using Hayes-style commands. However, at first there was almost no English-language documentation on the chip and the commands it accepted. The very low price and the fact that there were very few external components on the module which suggests that it could eventually be very inexpensive in volume, attracted many hackers to explore the module, chip, and the software on it, as well as to translate the Chinese documentation.

In late October 2014, Espressif released a software development kit (SDK) that allowed the chip to be programmed, removing the need for a separate microcontroller. Since then, there have been many official SDK releases from Espressif, and third party SDKs such as [NodeMCU](https://nodemcu.readthedocs.io/en/release/) and [Arduino](https://www.arduino.cc/en/Reference/ESP8266WiFi) have also been released. The ESP8266 is now one of the leading platforms for the Internet of Things (IoT).

## ESP32

The ESP32 is a low-cost, low-power system on a chip (SoC) with Wi-Fi and Bluetooth capabilities. It was created by Espressif Systems and initially released in 2016. It is a successor to the ESP8266 microcontroller.

The ESP32 is a [Tensilica Xtensa LX6](https://www.espressif.com/en/products/socs/esp32) microcontroller with dual-core 32-bit LX6 microprocessors. It runs at 160 or 240 MHz (or overclocked to 320 MHz). It also features a single-core [RTOS](https://en.wikipedia.org/wiki/Real-time_operating_system), Wi-Fi and Bluetooth capabilities. It features 520 KiB SRAM, 16 KiB SRAM in RTC, 448 KiB ROM, 16 KiB ROM in RTC, 802.11 b/g/n/e/I Wi-Fi, Bluetooth v4.2 BR/EDR and BLE specification, 2.2V to 3.6V operating range, -40°C to +125°C operating temperature, and 41 GPIO pins.

## Raspberry Pi Pico

The Raspberry Pi Pico is a low-cost, high-performance microcontroller board with flexible digital interfaces. It features the RP2040 microcontroller chip designed by Raspberry Pi in a compact form factor measuring 51mm x 21mm x 3.5mm. The Pico's CPU is a dual-core Arm Cortex-M0+ processor with flexible clock running up to 133 MHz. It also features 264KB of SRAM, 2MB of onboard Flash memory, 26 multifunction GPIO pins, 2 × SPI, 2 × I2C, 2 × UART, 3 × 12-bit ADC, 16 × controllable PWM channels, 1 × USB 1.1 controller and PHY, 8 × Programmable I/O (PIO) state machines for custom peripheral support, and low-power sleep and dormant modes.


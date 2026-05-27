# Firmware

This folder contains the ESPHome firmware configuration for the **Toshiba x ESP32-C6 UART Bridge**.

The firmware runs on a **Seeed Studio XIAO ESP32-C6** and uses the external Toshiba Suzumi ESPHome component to communicate with compatible Toshiba air conditioners over the internal CN22 UART interface.

## Files

- `esphome/toshiba-uart.yaml`  
  Main ESPHome configuration.

- `esphome/secrets.yaml`  
  Example secrets file with placeholder Wi-Fi values.

## ESPHome Component

This firmware uses the external Toshiba Suzumi ESPHome component:

https://github.com/pedobry/esphome_toshiba_suzumi

That component is licensed by its original author under the **GNU General Public License v3.0**.

## Board

Target board:

    Seeed Studio XIAO ESP32-C6

ESPHome board configuration:

    board: seeed_xiao_esp32c6
    variant: esp32c6
    framework: esp-idf

## UART

UART settings used to communicate with the Toshiba AC unit:

    Baud rate: 9600
    Parity: EVEN
    ESP32 TX: GPIO1
    ESP32 RX: GPIO0

Connection direction:

    ESP32 TX -> Toshiba RX
    ESP32 RX <- Toshiba TX

Always check your own AC unit's CN22 pinout before connecting the board.

## Features

- Toshiba AC control through ESPHome
- Real AC state feedback over UART
- Home Assistant API support
- OTA updates
- Wi-Fi fallback access point
- Wi-Fi signal and uptime sensors
- AC Wi-Fi LED control
- Off timer support
- XIAO ESP32-C6 onboard antenna switch setup

## Secrets

Before compiling, edit:

    firmware/esphome/secrets.yaml

Example:

    wifi_ssid: "YOUR_WIFI_NAME"
    wifi_password: "YOUR_WIFI_PASSWORD"
    fallback_ap_password: "YOUR_FALLBACK_AP_PASSWORD"

Do not commit real Wi-Fi credentials if you fork or modify this repository; untrack `firmware/esphome/secrets.yaml` and add it to `.gitignore` before entering real values.

## Build

From the `firmware/esphome` folder:

    esphome config toshiba-uart.yaml

To compile:

    esphome compile toshiba-uart.yaml

To upload:

    esphome run toshiba-uart.yaml

The first upload may require USB. After that, OTA updates can be used if the device is connected to Wi-Fi.

## License

Firmware files in this repository are licensed under **GPL-3.0-only**.

See `../LICENSE_SOFTWARE` for details.

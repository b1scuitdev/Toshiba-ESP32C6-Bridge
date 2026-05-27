# Hardware

This folder contains the hardware files for the **Toshiba x ESP32-C6 UART Bridge**.

The board is designed around the **Seeed Studio XIAO ESP32-C6** and connects to the internal **CN22 UART connector** of compatible Toshiba air conditioners.

It is used with ESPHome to read the real AC state and send control commands over UART.

## Files

- `SCHEMATIC - Toshiba x ESP32C6 UART Bridge v1.0 - Rev A.pdf`  
  Schematic export.

- `GERBER - Toshiba x ESP32C6 UART Bridge v1.0 - Rev A.zip`  
  Gerber files for PCB manufacturing.

- `BOM - ESP32C6 UART Bridge v1.0 - Rev A.xlsx`  
  Bill of materials.

- `PickAndPlace - Toshiba x ESP32C6 UART Bridge v1.0 - Rev A.xlsx`  
  Pick and place / assembly file.

## Compatibility

This board has only been tested with a **Toshiba Seiya** air conditioner.

It will likely work with other Toshiba air conditioners that use the same internal **CN22 UART** interface, but this has not been verified. Always check your own unit's connector, pinout, and service documentation before connecting the board.

## UART

UART settings used by the ESPHome firmware:

    Baud rate: 9600
    Parity: EVEN
    ESP32 TX: GPIO1
    ESP32 RX: GPIO0

Connection direction:

    ESP32 TX -> AC RX
    ESP32 RX <- AC TX

Check your own AC unit's **CN22 pinout** before connecting the board.

## Before Powering On

Before connecting or powering the board:

- Turn off the circuit breaker or completely disconnect AC power to the air conditioner.
- Do not work on the unit while it is connected to mains power.
- Check the PCB carefully for solder bridges, missing parts, wrong parts, or damaged components.
- Verify the orientation of polarized components.
- Check the Schottky diode direction before powering the board.
- Confirm connector orientation and cable order.
- Make sure the board is only connected to the low-voltage UART side of the air conditioner.

## Safety

This board is only intended for the low-voltage UART interface side of the air conditioner.

Do **not** connect it to mains voltage.

Air conditioners contain dangerous voltages inside. Disconnect AC power before opening the unit or connecting this board.

Use this hardware at your own risk.

## License

Hardware files are licensed under **CERN-OHL-S-2.0**.

See `../LICENSE_HARDWARE` for details.

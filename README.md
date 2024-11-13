# Create WiFi Access Point from WT32-ETH01

## How to put WT32-ETH01 into programming mode

To put the WT32-ETH01 into programming mode, the correct procedure involves connecting GND to IO0 (also called the BOOT pin) during the reset process. Here's the step-by-step process:

```Connect GND to IO0```

Use a jumper wire to connect the GND pin to the IO0 (BOOT) pin on the board. This is the most common method for forcing the board into programming mode.
With GND and IO0 connected, plug the USB cable back into the board to power it on.
Release IO0 jumper.

Once the board is in programming mode, it will be ready to accept new firmware uploads. You can then proceed to flash the firmware using ESP-IDF or your preferred method.
```
idf.py build
idf.py -p COM1 flash monitor
```

This process is necessary for boards like the WT32-ETH01, where the IO0 pin must be pulled low to trigger the bootloader for firmware flashing.


## Resources

- [eth2ap Example](https://github.com/espressif/esp-idf/tree/release/v5.0/examples/ethernet/eth2ap)
- [Ethernet on ESP32 using LAN8720](https://sautter.com/blog/ethernet-on-esp32-using-lan8720/)
- [Original Project idea](https://github.com/purplewish07/esp32-ethernet-to-wifi-ap)

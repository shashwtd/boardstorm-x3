## BoardStorm X3

designing a custom devboard


---
## notes for future reference

this is an RP2040 devboard with USB-C, LiPo charging, automatic battery/USB power switching, and battery percentage reading.

some things to keep in mind:

- `MAX17048` fuel gauge chip uses `GPIO4` and `GPIO5` to talk to the RP2040. It uses fixed I2C address `0x36`, so don't add another `0x36` I2C device.
- keep decoupling capacitors close to the chips during PCB layout.
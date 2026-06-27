## BoardStorm X3

this is a custom RP2040 microcontroller devboard, it comes with the following features

- USB-C power and programming
- 2MB onboard SPI flash
- 12MHz crystal oscillator
- broken out GPIO headers (Pico-compatible pinout)
- LiPo battery support with USB-C charging
- automatic USB/battery power switching via BQ24075
- can charge and run at once on USB power
- MAX17048 fuel gauge for accurate battery percentage over I2C

![PCB RENDER](images\pcb_render.png)
![PCB RENDER BACK](images\pcb-render-back.png)
![PCB DESIGN](images\pcb-design.png)


### key components used

- [RP2040](https://www.raspberrypi.com/products/rp2040/) — dual-core ARM Cortex-M0+ microcontroller
- [BQ24075RGT](https://www.ti.com/product/BQ24075) — USB Li-ion charger and power-path manager (USB/battery switching)
- [MAX17048G+T10](https://www.analog.com/en/products/max17048.html) — 1-cell fuel gauge (battery % over I2C)
- [MCP1700-330](https://www.microchip.com/en-us/product/mcp1700) — 3.3 V low-quiescent LDO regulator
- [W25Q16JVSS](https://www.winbond.com/hq/product/code-storage-flash-memory/serial-nor-flash/?__locale=en&partNo=W25Q16JV) — 16 Mbit (2 MB) SPI flash

---

### some things to keep in mind:
- `MAX17048` fuel gauge chip uses `GPIO4` and `GPIO5` to talk to the RP2040. It uses fixed I2C address `0x36`, so don't add another `0x36` I2C device.
- keep decoupling capacitors close to the chips during PCB layout.
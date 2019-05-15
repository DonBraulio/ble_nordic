# BLE demo app for nRF52840 DK
Demo application using FreeRTOS for BLE. Based on SDK nRF5_SDK_15.3.0_59ac345 app under `examples/ble_peripheral/ble_app_hrs_freertos`.

## Installation
### Requirements
- make
- Nordic nRF5 SDK (15.3.0)
- ARM GCC toolchain (8-2018-q4-major)
- nRF Command Line Tools
- Segger JLink (using JLinkGDBServerCL)

### Installation tips
- Download SDK in the same dir than this project (`../nRFxx` relative path from the project dir), and then set this location in `SDK_ROOT` in the `Makefile`.
- Copy ARM GCC toolchain and then set it on `nRF5xx/components/toolchain/gcc/Makefile.posix` (e.g: `GNU_INSTALL_ROOT ?= /usr/local/gcc-arm-none-eabi-8-2018-q4-major/bin/`)
- Include the nRF Command Line Tools into your `$PATH` so that nrfjprog is accessible (otherwise you'll need to set that path in the Makefile)

## Make targets
- `make`: Just compile
- `make ctags`: Generate tags file from the project and all included .c and .h files
- `make flash`: flash device (requires nrfjprog)
- `make flash_softdevice`: only flash softdevice (requires nrfjprog)
- `make jlink`: Start GDB Server (requires Segger JLink)
- `make debug`: Start gdb and connect to GDB server, set parameters (see `gdb_cmds.txt`) and download binary file. Ready to debug!

## Example debugging
```bash
make
make flash_softdevice
make jlink  # in another terminal
make debug
```

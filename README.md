# PSA Mbed OS example

This is an example application showing how to query the PSA version.

You can build this project with all supported [Mbed OS build tools](https://os.mbed.com/docs/mbed-os/latest/tools/index.html). However, this example project specifically refers to the command-line interface tool [Arm Mbed CLI](https://github.com/ARMmbed/mbed-cli#installing-mbed-cli).

1. Install Mbed CLI.
1. From the command-line, import the example: `mbed import mbed-os-example-psa`
1. Change the current directory to where the project was imported.

## Application functionality

The `main()` function queries the PSA version and toggles the state of a digital output connected to an LED on the board.

## Building and running

1. Connect a USB cable between the USB port on the target and the host computer.
1. Run the following command to build the example project, program the microcontroller flash memory, and open a serial terminal:

   ```
   mbed compile -m <TARGET> -t <TOOLCHAIN> --flash --sterm --baud 115200
   ```

**Note:**  The serial terminal baud rate should be set to 115200 for this example.

The binary is located at `./BUILD/<TARGET>/<TOOLCHAIN>/mbed-os-example-psa.bin`.

## Expected output

The LED on your target turns on and off every 1000 milliseconds. For TFM targets, for example ARM_MUSCA_S1, the serial terminal shows an output similar to (actual digits replaced by "X"):

```
--- Terminal on /dev/tty.usbmodem146102 - 115200,8,N,1 ---
[INF] Starting bootloader
[INF] Swap type: none
[INF] Swap type: none
[INF] Bootloader chainload address offset: 0x20000
[INF] Jumping to the first image slot
[Sec Thread] Secure image initializing!
Booting TFM vX.X
PSA Framework Version : XXX
Executing from NS Core... LED Blink rate : 1000 ms
Executing from NS Core... LED Blink rate : 1000 ms
```

For non TFM targets, for example K64F, the serial terminal shows an output similar to:

```
--- Terminal on /dev/tty.usbmodem146102 - 115200,8,N,1 ---
PSA Framework Version : XXX
Executing from NS Core... LED Blink rate : 1000 ms
Executing from NS Core... LED Blink rate : 1000 ms
```

## License and contributions

The software is provided under Apache-2.0 license. Contributions to this project are accepted under the same license. Please see [contributing.md](./CONTRIBUTING.md) for more info.

This project contains code from other projects. The original license text is included in those source files. They must comply with our [license guide](https://os.mbed.com/docs/mbed-os/v6.2/contributing/license.html)

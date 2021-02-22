# PSA Mbed OS example

This is an example application showing how to query the PSA version.

You can build this project with all supported [Mbed OS build tools](https://os.mbed.com/docs/mbed-os/latest/tools/index.html). However, this example project specifically refers to the command-line interface tool [Arm Mbed CLI](https://github.com/ARMmbed/mbed-cli#installing-mbed-cli).

1. Install Mbed CLI.
1. From the command-line, import the example: `mbed import mbed-os-example-psa`
1. Change the current directory to where the project was imported.

## Mbed OS build tools

### Mbed CLI 2
Starting with version 6.5, Mbed OS uses Mbed CLI 2. It uses Ninja as a build system, and CMake to generate the build environment and manage the build process in a compiler-independent manner. If you are working with Mbed OS version prior to 6.5 then check the section [Mbed CLI 1](#mbed-cli-1).
1. [Install Mbed CLI 2](https://os.mbed.com/docs/mbed-os/latest/build-tools/install-or-upgrade.html).
1. From the command-line, import the example: `mbed-tools import mbed-os-example-psa`
1. Change the current directory to where the project was imported.

### Mbed CLI 1
1. [Install Mbed CLI 1](https://os.mbed.com/docs/mbed-os/latest/quick-start/offline-with-mbed-cli.html).
1. From the command-line, import the example: `mbed import mbed-os-example-psa`
1. Change the current directory to where the project was imported.

## Application functionality

The `main()` function queries the PSA version and toggles the state of a digital output connected to an LED on the board.

## Building and running

1. Connect a USB cable between the USB port on the board and the host computer.
1. Run the following command to build the example project and program the microcontroller flash memory:

    * Mbed CLI 2

    ```bash
    $ mbed-tools compile -m <TARGET> -t <TOOLCHAIN> --flash
    ```

    * Mbed CLI 1

    ```bash
    $ mbed compile -m <TARGET> -t <TOOLCHAIN> --flash
    ```

Your PC may take a few minutes to compile your code.

The binary is located at:
* **Mbed CLI 2** - `./cmake_build/<TARGET>/<PROFILE>/<TOOLCHAIN>/mbed-os-example-psa.bin`</br>
* **Mbed CLI 1** - `./BUILD/<TARGET>/<TOOLCHAIN>/mbed-os-example-psa.bin`

Alternatively, you can manually copy the binary to the board, which you mount on the host computer over USB.

**Note:**  The serial terminal baud rate should be set to 115200 for this example.

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

# mbed-os-example-psa

This is an example application showing how to query the PSA version. It also blinks an LED to indicate it is working.

## Prerequisite

* [Mbed CLI](https://github.com/ARMmbed/mbed-cli) - to build the example program. For installation and usage instructions, see the [documentation](https://os.mbed.com/docs/mbed-os/latest/build-tools/mbed-cli.html).

## Building the Mbed OS application

#### Import the example

1. From the command line, clone the repository containing the example:
    ```
    $ git clone https://github.com/ARMmbed/mbed-os-example-psa
    ```

1. Change the current directory to where the project was imported.

1. Update `mbed-os` sources by running `mbed deploy`.

#### Compile the example

Invoke `mbed compile`, and specify the name of your platform and toolchain (`GCC_ARM`, `ARM`). For example, for the ARM_MUSCA_S1 platform and GCC_ARM toolchain:

```
mbed compile -m ARM_MUSCA_S1 -t GCC_ARM
```
Once its compiled, you should see the following result:
```
| Module           |         .text |       .data |          .bss |
|------------------|---------------|-------------|---------------|
| [fill]           |       46(+46) |       0(+0) |       37(+37) |
| [lib]/c.a        |   4792(+4792) | 2108(+2108) |       89(+89) |
| [lib]/gcc.a      |     764(+764) |       0(+0) |         0(+0) |
| [lib]/misc       |     180(+180) |       4(+4) |       28(+28) |
| [misc]           |         0(+0) |       0(+0) |         0(+0) |
| main.o           |     100(+100) |       0(+0) |         0(+0) |
| mbed-os/cmsis    |   6716(+6716) |   240(+240) | 14929(+14929) |
| mbed-os/drivers  |     480(+480) |       0(+0) |         0(+0) |
| mbed-os/hal      |   2670(+2670) |       8(+8) |     232(+232) |
| mbed-os/platform |   4090(+4090) |   260(+260) |     268(+268) |
| mbed-os/rtos     |       28(+28) |       0(+0) |         0(+0) |
| mbed-os/targets  |   3242(+3242) |     36(+36) |       77(+77) |
| Subtotals        | 23108(+23108) | 2656(+2656) | 15660(+15660) |
Total Static RAM memory (data + bss): 18316(+18316) bytes
Total Flash memory (text + data): 25764(+25764) bytes

Image: ./BUILD/ARM_MUSCA_S1/GCC_ARM/mbed-os-example-psa.bin
```
#### Run the example

1. Connect your Mbed Enabled device to the computer over USB.
1. Copy the binary or hex file to the Mbed device.
1. Connect to the Mbed Device using a serial client application of your choice.
1. Press the reset button on the Mbed device to run the program.

**Note:** The default serial port baud rate is 9600 baud.

Expected output:
```
PSA Framework Version : NNN
Executing from NS Core... LED Blink rate : 1000 ms
```

where NNN is the PSA framework version number.

## License and contributions

The software is provided under Apache-2.0 license. Contributions to this project are accepted under the same license. Please see [contributing.md](./CONTRIBUTING.md) for more info.

This project contains code from other projects. The original license text is included in those source files. They must comply with our [license guide](https://os.mbed.com/docs/mbed-os/v6.2/contributing/license.html)

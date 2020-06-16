# mbed-os-example-psa

This is an example application showing how to query the PSA version. It also
blinks an LED to indicate it is working.

## Prerequisite

* [Mbed CLI](https://github.com/ARMmbed/mbed-cli) - to build the example program. For installation and usage instructions, see the [documentation](https://os.mbed.com/docs/mbed-os/v6.0/build-tools/mbed-cli.html).

## Building the Mbed OS application

#### Import the example

1. From the command line, clone the repository containing the example:
    ```
    $ git clone https://github.com/ARMmbed/mbed-os-example-psa
    ```

1. Change the current directory to where the project was imported.

1. Update `mbed-os` sources by running `mbed deploy`.

#### Compile the example

Invoke `mbed compile`, and specify the name of your platform and toolchain (`GCC_ARM`, `ARM`, `IAR`). For example, for the CY8CKIT_064S2_4343W platform and GCC_ARM toolchain:

```
mbed compile -m CY8CKIT_064S2_4343W -t GCC_ARM
```
Once its compiled, you should see the following result:
```
[snip]
| Module           |         .text |       .data |          .bss |
|------------------|---------------|-------------|---------------|
| [fill]           |       98(+98) |     10(+10) |       45(+45) |
| [lib]/c.a        |   4940(+4940) | 2108(+2108) |       89(+89) |
| [lib]/gcc.a      |     832(+832) |       0(+0) |         0(+0) |
| [lib]/misc       |     224(+224) |       4(+4) |       28(+28) |
| [misc]           |         0(+0) |       0(+0) |         0(+0) |
| main.o           |     168(+168) |       0(+0) |         0(+0) |
| mbed-os/drivers  |     480(+480) |       0(+0) |         0(+0) |
| mbed-os/features |   1754(+1754) |       1(+1) |     288(+288) |
| mbed-os/hal      |   2608(+2608) |       8(+8) |     248(+248) |
| mbed-os/platform |   5538(+5538) |   260(+260) |     416(+416) |
| mbed-os/rtos     |   8404(+8404) |   240(+240) | 23472(+23472) |
| mbed-os/targets  | 24874(+24874) |   297(+297) |   1210(+1210) |
| Subtotals        | 49920(+49920) | 2928(+2928) | 25796(+25796) |
Total Static RAM memory (data + bss): 28724(+28724) bytes
Total Flash memory (text + data): 52848(+52848) bytes

Image: ./BUILD/CY8CKIT_064S2_4343W/GCC_ARM/mbed-os-example-psa.hex
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

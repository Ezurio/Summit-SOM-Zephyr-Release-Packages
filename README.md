# Summit-SOM-Zephyr-Release-Packages

## Cloning Firmware

> **WARNING:** On Windows do not clone into a starting folder path longer than 12 characters or else the firmware will not build.

This is a Zephyr `west` manifest repository. To learn more about `west` see [here](https://docs.zephyrproject.org/latest/guides/west/index.html).

To clone this repository properly use the `west` tool. To install `west` you will first need Python3.

Install `west` using `pip3`:

```
# Linux
pip3 install --user -U west

# macOS (Terminal) and Windows (cmd.exe)
pip3 install -U west
```

Once `west` is installed, clone this repository using `west init` and `west update`:

```
# Checkout the manifest at a given release using the format below:
# west init -m https://github.com/LairdCP/Summit-SOM-Zephyr-Release-Packages.git --mr <TAG_NAME> --mf <MANIFEST_FILE>
# For example, for the 0.0.0.26 release:
west init -m https://github.com/LairdCP/Summit-SOM-Zephyr-Release-Packages.git --mr SUMMIT-ZEPHYR-0.0.0.26 --mf summit-mcu-demos_0.0.0.26.yml

# Now, pull all the source described in the manifest
west update
```

## Preparing to Build

If this is your first time working with a Zephyr project on your computer you should follow the [Zephyr getting started guide](https://docs.zephyrproject.org/latest/getting_started/index.html#) to install all the tools.

The firmware uses zephyr 2.7.99, so GCC 10.3 is recommended.
[GNU Arm Embedded Toolchain: 10.3-2021.07](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads) is recommended.

See here to [setup the GNU ARM Embedded tools](https://docs.zephyrproject.org/2.7.0/getting_started/toolchain_3rd_party_x_compilers.html)

If using Linux or macOS, v0.14.0 of the Zephyr SDK is recommended.

## Building the Firmware

> **WARNING:** Before building the firmware, be sure to install all dependencies using the `zephyr/scripts/requirements.txt`

From the directory where you ran `west update`, issue the following command:

```
# Linux
pip3 install --user -r zephyr/scripts/requirements.txt

# macOS and Windows
pip3 install -r zephyr/scripts/requirements.txt
```

See the README for each individual sample application for build commands.
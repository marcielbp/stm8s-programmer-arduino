# stm8s-programmer-arduino
Guidelines to compile and upload program to stm8s

## Setup

* Install arduino board: https://tenbaht.github.io/sduino/
* Install flash tool: https://github.com/vdudouyt/stm8flash

Tool: ST-LINK V2 (don't forget updating udev rules, check [here](https://tenbaht.github.io/sduino/usage/manual-install/)

**Before** flashing, must connect either ST-Link V2 **and** USB Cable.
In arduino IDE: programmer: ST-Link-V2 board: stm8s103f3


In order to remove writting protection:
```shell
echo "00 00 ff 00 ff 00 ff 00 ff 00 ff" | xxd -r -p > factory_defaults.bin
stm8flash -c stlinkv2 -p stm8s103?3 -s opt -w factory_defaults.bin
```

In arduino IDE:
- programmer: ST-Link-V2
- board: stm8s103f3

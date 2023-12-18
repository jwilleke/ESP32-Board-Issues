# ESP32-Board-Issues
ESP32 Board Issues encountered


## Components Used

[FireBeetle 2 ESP32-E](https://www.dfrobot.com/product-2231.html)

### Using:
Arduino IDE: v 2.2.1
Version: 2.2.1
Date: 2023-08-31T14:26:39.874Z
CLI Version: 0.34.0

### on:
ProductName:  macOS
ProductVersion:  14.2
BuildVersion:  23C64

### Also tried with:
FireBeetle 2 ESP32-E IoT Microcontroller with Header

## Errors

### When trying to upload a project:
```A fatal error occurred: Failed to connect to ESP32: Timed out waiting for packet header```



### when asking for board information:
```
Sketch uses 752792 bytes (57%) of program storage space. Maximum is 1310720 bytes.
Global variables use 33476 bytes (10%) of dynamic memory, leaving 294204 bytes for local variables. Maximum is 327680 bytes.
"/Users/jim/Library/Arduino15/packages/DFRobot/tools/esptool_py/3.0.0/esptool" --chip esp32 --port "/dev/cu.URT1" --baud 115200  --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0xe000 "/Users/jim/Library/Arduino15/packages/DFRobot/hardware/esp32/0.2.1/tools/partitions/boot_app0.bin" 0x1000 "/private/var/folders/97/4ntvdgtn4cg6l3rtf1ld56dw0000gn/T/arduino/sketches/6B93324481AFB3499472EFCECB202409/esp32-wifi.ino.bootloader.bin" 0x10000 "/private/var/folders/97/4ntvdgtn4cg6l3rtf1ld56dw0000gn/T/arduino/sketches/6B93324481AFB3499472EFCECB202409/esp32-wifi.ino.bin" 0x8000 "/private/var/folders/97/4ntvdgtn4cg6l3rtf1ld56dw0000gn/T/arduino/sketches/6B93324481AFB3499472EFCECB202409/esp32-wifi.ino.partitions.bin" 
esptool.py v3.1-dev
Serial port /dev/cu.URT1
Connecting........_____....._____....._____....._____....._____....._____....._____

A fatal error occurred: Failed to connect to ESP32: Timed out waiting for packet header
Failed uploading: uploading error: exit status 2
```


Tried different baud rates with the same results.

## What Works

Same setup appears to work fine with Arduino UNO 4.

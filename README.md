# ESP32-Board-Issues

ESP32 Board Issues encountered

## Components Used

[FireBeetle 2 ESP32-E](https://www.dfrobot.com/product-2231.html)

### Using

- Arduino IDE: v 2.2.1
  - Version: 2.2.1
  - Date: 2023-08-31T14:26:39.874Z
  - CLI Version: 0.34.0

### on

- ProductName:  macOS
- ProductVersion:  14.2
- BuildVersion:  23C64

### Also tried with

FireBeetle 2 ESP32-E IoT Microcontroller with Header

## Errors

### When trying to upload a project

``` bash
Sketch uses 763364 bytes (58%) of program storage space. Maximum is 1310720 bytes.
Global variables use 33812 bytes (10%) of dynamic memory, leaving 293868 bytes for local variables. Maximum is 327680 bytes.
"/Users/jim/Library/Arduino15/packages/DFRobot/tools/esptool_py/3.0.0/esptool" --chip esp32 --port "/dev/cu.URT1" --baud 115200  --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0xe000 "/Users/jim/Library/Arduino15/packages/DFRobot/hardware/esp32/0.2.1/tools/partitions/boot_app0.bin" 0x1000 "/private/var/folders/97/4ntvdgtn4cg6l3rtf1ld56dw0000gn/T/arduino/sketches/6B93324481AFB3499472EFCECB202409/esp32-wifi.ino.bootloader.bin" 0x10000 "/private/var/folders/97/4ntvdgtn4cg6l3rtf1ld56dw0000gn/T/arduino/sketches/6B93324481AFB3499472EFCECB202409/esp32-wifi.ino.bin" 0x8000 "/private/var/folders/97/4ntvdgtn4cg6l3rtf1ld56dw0000gn/T/arduino/sketches/6B93324481AFB3499472EFCECB202409/esp32-wifi.ino.partitions.bin" 
esptool.py v3.1-dev
Serial port /dev/cu.URT1
Connecting........_____....._____....._____....._____....._____....._____....._____

A fatal error occurred: Failed to connect to ESP32: Timed out waiting for packet header
Failed uploading: uploading error: exit status 2
```

### when asking for board information

``` bash
Native serial port, can't obtain info.
```

Tried different baud rates with the same results.

## What Works

Same setup appears to work fine with Arduino UNO 4 for both getting Baord Infor and uploads.

However I have not been able to upgrade firmware to the board. May or may not be related.


``` bash
ll /dev/{tty,cu}.*
crw-rw-rw-  1 root  wheel  0x9000003 Dec 18 08:30 /dev/cu.BLTH
crw-rw-rw-  1 root  wheel  0x9000005 Dec 18 07:33 /dev/cu.Bluetooth-Incoming-Port
crw-rw-rw-  1 root  wheel  0x9000001 Dec 18 08:40 /dev/cu.URT1
crw-rw-rw-  1 root  wheel  0x9000007 Dec 18 08:42 /dev/cu.usbmodemF412FAA081C02
crw-rw-rw-  1 root  wheel  0x9000002 Dec 18 07:27 /dev/tty.BLTH
crw-rw-rw-  1 root  wheel  0x9000004 Dec 18 07:27 /dev/tty.Bluetooth-Incoming-Port
crw-rw-rw-  1 root  wheel  0x9000000 Dec 18 07:27 /dev/tty.URT1
crw-rw-rw-  1 root  wheel  0x9000006 Dec 18 08:42 /dev/tty.usbmodemF412FAA081C02
```

## What I do See

``` bash
ll /dev/{tty,cu}.*
crw-rw-rw-  1 root  wheel  0x9000003 Dec 18 08:15 /dev/cu.BLTH
crw-rw-rw-  1 root  wheel  0x9000005 Dec 18 07:33 /dev/cu.Bluetooth-Incoming-Port
crw-rw-rw-  1 root  wheel  0x9000001 Dec 18 07:47 /dev/cu.URT1 
crw-rw-rw-  1 root  wheel  0x9000002 Dec 18 07:27 /dev/tty.BLTH   
crw-rw-rw-  1 root  wheel  0x9000004 Dec 18 07:27 /dev/tty.Bluetooth-Incoming-Port
crw-rw-rw-  1 root  wheel  0x9000000 Dec 18 07:27 /dev/tty.URT1 # <== Works with Ardrunio
```

## What I have tried

Use the "ESP32-S2 Dev Board", got same errors.

## Other Noted Items

- [Comments on DFRbot](https://www.dfrobot.com/product-2231.html#comment-5539242446)
- [FireBeetle 2 ESP32-E wiki](https://wiki.dfrobot.com/FireBeetle_Board_ESP32_E_SKU_DFR0654) Has a lot of details on the board.

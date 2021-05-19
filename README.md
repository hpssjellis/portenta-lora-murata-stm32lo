# portenta-lora-murata-stm32lo


This github has been forked from https://github.com/facchinm/ArduinoCore-stm32l0 by Arduino which in turn was forked from https://github.com/GrumpyOldPizza/ArduinoCore-stm32l0 which allows full control of the murata module on the Portenta H7 LoRa Vision Shield.


Unfortuantely we are not given an enormous amount of memory to work with so I will have to try to get the MKRWAN library working as well to be able to completely use the LoRaWan capabilities.




Presently I install the GrumplyOldPizza Tlera board and then copy all these files to replace the Tlera board, but I am working on a better method. The json file for the Arduino IDA preferences is here 

```https://grumpyoldpizza.github.io/ArduinoCore-stm32l0/package_stm32l0_boards_index.json``` but I am working on a JSON for this board.


Huge Thanks to both the previous repositories for getting this working.


My version of the board deffinitions for the comma seperated preferences Arduino IDE is here.

```https://hpssjellis.github.io/portenta-lora-murata-stm32lo/package_portenta_stm32l0_boards_index.json```
.

.

.



.


.





# The old README.md is below

# Arduino Core for STM32L0 based boards

## What is it ?

ArduinoCore-stm32l0 is targeted at ultra low power scenarios, sensor hubs, with LoRaWAN connectivity.


## Supported boards

### Tlera Corp
 * [Grasshopper-L082CZ](https://www.tindie.com/products/TleraCorp/grasshopper-lora-development-board)
 * [Cricket-L082CZ](https://www.tindie.com/products/TleraCorp/cricket-lorawangnss-asset-tracker)
 * [Cicada-L082CZ](https://www.tindie.com/products/TleraCorp/lorasensortile)

### STMicroelectronics
 * [B-L072Z-LRWAN1](http://www.st.com/en/evaluation-tools/b-l072z-lrwan1.html)
 * [P-NUCLEO-LRWAN1](http://www.st.com/en/evaluation-tools/p-nucleo-lrwan1.html)
 * [NUCLEO-L053R8](http://www.st.com/en/evaluation-tools/nucleo-l053r8.html)
 * [NUCLEO-L073RZ](http://www.st.com/en/evaluation-tools/nucleo-l073rz.html)


## Installing

### Board Manager

 1. [Download and install the Arduino IDE](https://www.arduino.cc/en/Main/Software) (at least version v1.6.8)
 2. Start the Arduino IDE
 3. Go into Preferences
 4. Add ```https://grumpyoldpizza.github.io/ArduinoCore-stm32l0/package_stm32l0_boards_index.json``` as an "Additional Board Manager URL"
 5. Open the Boards Manager from the Tools -> Board menu and install "Tlera Corp STM32L0 Boards"
 6. Select your STM32L0 board from the Tools -> Board menu

#### OS Specific Setup

##### Linux

 1. Go to ~/.arduino15/packages/TleraCorp/hardware/stm32l0/```<VERSION>```/drivers/linux/
 2. sudo cp *.rules /etc/udev/rules.d
 3. reboot

#####  Windows

###### STM32 BOOTLOADER driver setup for Tlera Corp boards

 1. Download [Zadig](http://zadig.akeo.ie)
 2. Plugin STM32L0 board and toggle the RESET button while holding down the BOOT button
 3. Let Windows finish searching for drivers
 4. Start ```Zadig```
 5. Select ```Options -> List All Devices```
 6. Select ```STM32 BOOTLOADER``` from the device dropdown
 7. Select ```WinUSB (v6.1.7600.16385)``` as new driver
 8. Click ```Replace Driver```

###### USB Serial driver setup for Tlera Corp boards (Window XP / Windows 7 only)

 1. Go to ~/AppData/Local/Arduino15/packages/TleraCorp/hardware/stm32l0/```<VERSION>```/drivers/windows
 2. Right-click on ```dpinst_x86.exe``` (32 bit Windows) or ```dpinst_amd64.exe``` (64 bit Windows) and select ```Run as administrator```
 3. Click on ```Install this driver software anyway``` at the ```Windows Security``` popup as the driver is unsigned

###### ST-LINK V2.1 driver setup for STMicroelectronics boards

 1. Plugin STMicroelectronics board
 2. Download and install [ST-Link USB Drivers](http://www.st.com/en/embedded-software/stsw-link009.html)

### From git

 1. Follow steps from Board Manager section above
 2. ```cd <SKETCHBOOK>```, where ```<SKETCHBOOK>``` is your Arduino Sketch folder:
  * OS X: ```~/Documents/Arduino```
  * Linux: ```~/Arduino```
  * Windows: ```~/Documents/Arduino```
 3. Create a folder named ```hardware```, if it does not exist, and change directories to it
 4. Clone this repo: ```git clone https://github.com/grumpyoldpizza/ArduinoCore-stm32l0.git TleraCorp/stm32l0```
 5. Restart the Arduino IDE

## Recovering from a faulty sketch for Tlera Corp Boards

 Sometimes a faulty sketch can render the normal USB Serial based integration into the Arduindo IDE not working. In this case plugin the STM32L0 board and toggle the RESET button while holding down the BOOT button and program a known to be working sketch to go ack to a working USB Serial setup.

## Credits

This core is based on and compatible with the [Arduino SAMD Core](https://github.com/arduino/ArduinoCore-samd)


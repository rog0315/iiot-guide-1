# ThingsPro Installation (for UC-8100-ME)

In this guide, we will be upgrading the UC-8100-ME to the newest firmware and installing ThingsPro onto the UC-8100-ME.

## Prerequisites

* MOXA console cable
* PuTTY or other Terminal Emulator Software
* WinSCP
* SD Card
*  [Latest Firmware image](https://www.moxa.com/support/sarch_result.aspx?type=soft&prod_id=5155&type_id=4) (UC-8100-ME Firmware)
* Latest ThingsPro build
    * Links to the files needed:
        * [ThingsPro v2.3](https://www.dropbox.com/s/r8z299hhecx3at4/thingspro_armhf_20180330-001535.frm?dl=0)
        * [Install.sh](https://moxa-my.sharepoint.com/:u:/p/roger_halftermeyer/EVICUAR8b6VFvFYdLgxp_WoB7bMb389s53fzGhGi--GKMQ?e=WeIlce)


## Preparing the SD Card for firmware upgrade (For Windows)

1. Insert an empty SD card to a Windows PC
2. Reformat the SD card to use the FAT32 file system:
      1. This can be done by right clicking on the SD card and clicking Format
    2. Change File system to FAT32 and click start
    ![SDRight.png](https://github.com/rog0315/Images/blob/master/SDRight.png?raw=true)

3. Once the Reformat is done, copy the newest firmware image onto the reformatted SD card
    * Copy the image's name for later

## Updating the Firmware

1. Connect to the UC-8100-ME using the serial console
2. Once the connection with the UC-8100-ME is made, power down the device
3. Insert the SD card with the Firmware image into the US-8100-ME
4. On the serial console, press and hold the \<DEL>  key, while powering up the device, this will open up the bootloader configuration settings
5. On the bootloader configuration settings, type "1" and press enter
    ![UC8100_1.png](https://github.com/rog0315/Images/blob/master/UC8100_1.png?raw=true)
    ![UC8100_2.png](https://github.com/rog0315/Images/blob/master/UC8100_2.png?raw=true)

6. The computer will then ask for an .img file that is on the SD card and press enter
    * If you had previouly copied it from the Preparing SD Card section this would be the place to paste it and add the .img extention to it

    ![UC8100_3.png](https://github.com/rog0315/Images/blob/master/UC8100_3.png?raw=true)
7. Once the update is completed, press "4" to open the OS command line.
![UC8100_4.png](https://github.com/rog0315/Images/blob/master/UC8100_4.png?raw=true)

## Installing the ThingsPro Gateway

1. Connect to the UC-8100-ME using the serial console
2. Open WinSCP and connect to the UC-8100-ME
![Things1.png](https://github.com/rog0315/Images/blob/master/Things1.png?raw=true)
3. Using WinSCP, copy the ThingsPro v2.3 and Install.<span>sh</span> to the UC-8100-ME
![Things2.png](https://github.com/rog0315/Images/blob/master/Things2.png?raw=true)
4. Once the files have been copied to the UC-8100-ME, using the serial console type `ls` to confirm the files have been transfered
![Things3.png](https://github.com/rog0315/Images/blob/master/Things3.png?raw=true)
5. For the UC-8100-ME: Run `sudo bash install.sh  uc8100me-mxcloud-cg`
    For the UC-8100: Run `sudo bash install.sh  uc8100-mxcloud-cg`
7. Once the installation is done, run `pversion`
![Things5.png](https://github.com/rog0315/Images/blob/master/Things5.png?raw=true)
7. Confirm if the version shown is the one you installed, if so, you have successfully installed ThingsPro

# Ender-5-plus
Installation instructions for Ender 5 Plus (original hardware):
- BIGTREETECH BTT OCTOPUS V1.1 32BIT 
- TMC2209 stepper drivers
- Raspberry Pi 4 Model B 8GB
- OctoPi 0.18.0
- OctoPrint 1.8.1
- Klipper

### Shortcuts
[Board wirings](https://github.com/juldaani/Ender-5-plus#board-wirings)

[Installation and configuration of OctoPi+OctoPrint+Klipper](https://github.com/juldaani/Ender-5-plus#install-octopioctoprintklipper-on-raspberry-pioctopus)

[Physical installation of Octopus board and Raspberry Pi + 3D-models for mounts](https://github.com/juldaani/Ender-5-plus#physical-installation-of-octopus-board-and-raspberry-pi)


### Links
Bigtreetech octopus github:
(https://github.com/bigtreetech/BIGTREETECH-OCTOPUS-V1.0)

Random Octopus installation guide:
https://www.makenprint.uk/3d-printing/3d-printing-guides/3d-printer-mainboard-installation-guides/btt-octopus-guides/btt-octopus-setup-guide/

# Board wirings

## 1. Remove all jumpers from the board
If there are any jumpers attached remove them before proceeding.

## 2. Set jumpers to UART mode for stepper motor drivers
mtp://HMD_Global_Nokia_8_NB1GAD1780406664/Internal%20shared%20storage/DCIM/Camera/IMG_20220811_184935.jpg
mtp://HMD_Global_Nokia_8_NB1GAD1780406664/Internal%20shared%20storage/DCIM/Camera/IMG_20220811_184957.jpg

## 3. Wiring between PSU and board
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/power_wiring.png" width="650">
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/power-wiring2.png" width="650">

## 4. Hot bed wiring
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/hot_bed.jpg" width="650">

## 5. Install TMC2209 stepper motor drivers
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/stepper_drivers.jpg" width="650">

## 7. Plug in stepper motor cables
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/stepper_wires2.jpg" width="650">

- MOTOR0: X
- MOTOR1: Y
- MOTOR2_1: Z
- MOTOR3: Z
- MOTOR4: EXTRUDER (E)

## 8. Change X and Y-axis limit switch connectors to 3-pin
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/limit_switch.jpg" width="250">

## 9. Plug Y-axis limit switch connector to DIAG1
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/limit_switch1.jpg" width="650">

## 10. Plug X-axis limit switch connector to DIAG0
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/limit_switch2.jpg" width="650">

## 11. Connect Nozzle Heat to HE0
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/nozzle_heat.jpg" width="650">

## 12. Connect Bed Thermistor to TB
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/bed_thermistor.jpg" width="550">

## 13. Connect Nozzle Thermistor to T0
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/nozzle_thermistor.jpg" width="550">

## 14. Connect BlTouch
Change original connector to Dupont connector:

<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/bltouch2.jpg" width="350">

Swap wires in connectors according to the image and plug connectors to BlTouch pins:

<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/bltouch.jpg" width="650">

## 15. Connect filament runout sensor to DIAG4
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/filament.jpg" width="550">

## 16. Set fan jumpers
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/fan_jumpers.png" width="950">

## 17. Plug part cooling fan to FAN0 (PWM)
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/part_cooling_fan.jpg" width="650">

## 18. Plug mainboard fan to FAN7 (always on)
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/mainboard_fan.jpg" width="650">

## 19. Plug extruder fan to FAN6 (always on)
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/extruder_fan.jpg" width="650">

## 20. Connect Raspberry to Octopus board
- Connect Raspberry and Octopus via USB-C
- Power Raspberry through GPIO pins
- Raspberry pins 2,4 (5V) -> Octopus Raspberry (J26 connector) 5V pins
- Raspberry pins 6,9 (GND) -> Octopus Raspberry (J26 connector) GND pins
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/rasp_wires1.jpg" width="350">
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/rasp_wires2.jpg" width="450">

# Install OctoPi+OctoPrint+Klipper on Raspberry Pi+Octopus

## 1. Download Raspberry Pi Imager
https://www.raspberrypi.com/software/

## 2. Install OctoPi using Raspberry Pi Imager
- CHOOSE OS -> Other specific-purpose OS -> 3D printing -> OctoPi
- Hit CTRL+SHIFT+X to access advanced options
- Enable SSH and set username and password
- Configure wireless LAN (SSID, Password, Wireless LAN country)
- Set locale settings (Time zone, Keyboard layout)

## 3. Check OctoPi is working
- Plug in power input cable into Raspberry USB-C slot
- Put SD card in
- Type "http://octopi.local" to browser
- If everything works as expected OctoPrint web page should be opened

## 4. Install Klipper
https://www.klipper3d.org/Installation.html#prepping-an-os-image
1. Check that connections and wires are ok (no short circuits etc.)
2. Switch power supply on. Beware that the input voltage to the PSU might be fatal so don't put your fingers to wrong places.  
3. Connect to Raspberry via SSH. Linux command: ```ssh pi@octopi.local```
4. ```git clone https://github.com/Klipper3d/klipper```
5. ```./klipper/scripts/install-octopi.sh```

## 5. Build and flash Octopus board
https://www.klipper3d.org/Installation.html#building-and-flashing-the-micro-controller

https://github.com/bigtreetech/BIGTREETECH-OCTOPUS-V1.0/tree/master/Firmware/Klipper#build-firmware-image

https://github.com/bigtreetech/BIGTREETECH-OCTOPUS-V1.0/tree/master/Firmware/Klipper#option-1-dfu-firmware-install

[https://docs.vorondesign.com/build/software/octopus_klipper.html](https://docs.vorondesign.com/build/software/octopus_klipper.html#option-2-dfu-firmware-install)
1. SSH into raspberry. Linux command: ```ssh pi@octopi.local```
2. ```cd ~/klipper/```
3. ```export LC_ALL=en_GB.UTF-8```
4. ```make menuconfig```
5. Set following configurations: <img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/octopus_f446_klipper_menuconfig.png" width="850">
6. ```make```
7. Power everything off
8. Install jumper to BOOT0 on Octopus board
9. Power on
10. SSH into Raspberry
11. ```cd ~/klipper/```
12. <i>"When flashing for the first time, make sure that OctoPrint is not connected directly to the printer (from the OctoPrint web page, under the "Connection" section, click "Disconnect")."</i>
13. <i>"From your ssh session, run ```lsusb```. and find the ID of the dfu device. The device is typically named STM Device in DFU mode."</i>
14. <i>"If you do not see a DFU device in the list, press the reset button next to the USB connector and run lsusb again."</i>
15. <i>"Run ```make flash FLASH_DEVICE=1234:5678``` replace 1234:5678 with the ID from the previous step"</i>
16. Power everything off
17. Remove jumper from BOOT0
18. Power on
19. SSH into Raspberry
20. <i>"You can confirm that the flash was successful, by running ```ls /dev/serial/by-id```. If the flash was successful, this should now show a klipper device, similar to: <br><img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/dfu_flash.png" width="450"> "</i>

## 6. Configure OctoPrint to use Klipper
https://www.klipper3d.org/Installation.html#configuring-octoprint-to-use-klipper

## 7. Configure Klipper
https://www.klipper3d.org/Installation.html#configuring-klipper

1. SSH into Raspberry
2. ```cp ~/klipper/config/generic-bigtreetech-octopus.cfg ~/printer.cfg```
3. Run ```ls /dev/serial/by-id/*``` command in Raspberry to get the ID number of the Octopus board.
4. Run ```nano ~/printer.cfg``` and set the ID number under ```[mcu]``` section in printer.cfg: <br> ```serial: /dev/serial/by-id/usb-Klipper_stm32f446xx_0E002B00135053424E363620-if00```
5. Power everything off
7. Connect wires to the printer
8. Power on
9. Open http://octopi.local and connect to the printer
10. Open Terminal tab, type ```status``` and hit Send button.
11. If everything is ok a "status" command will report the printer is ready if the Klipper config file is successfully read and the micro-controller is successfully found and configured: <br> <img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/status.png" width="550">

## 8. (Optional) Install sshfs
Install sshfs (for mounting Raspberry's file system over SSH) to avoid serious mental health issues with nano text editor when customizing printer.cfg.

1. Install sshfs, Linux command: ```sudo apt install sshfs```
2. ```sudo mkdir /mnt/ender```
3. Mount Raspberry's filesystem: ```sudo sshfs -o allow_other,default_permissions pi@octopi.local:/ /mnt/ender```
4. Open printer configuration file with gedit: ```gedit /mnt/ender/home/pi/printer.cfg```
5. Set gedit Highlight Mode to YAML to make the text more readable

## 9. Upload printer.cfg to raspberry
https://www.klipper3d.org/Installation.html#configuring-klipper

1. Configuration file: https://github.com/juldaani/Ender-5-plus/blob/main/printer-original-hardware.cfg
2. Rename to "printer.cfg" before using with Klipper
3. Update [mcu] section (https://github.com/juldaani/Ender-5-plus/blob/main/README.md#7-configure-klipper)

<i>"After creating and editing the file it will be necessary to issue a "restart" command in the OctoPrint web terminal to load the config. A "status" command will report the printer is ready if the Klipper config file is successfully read and the micro-controller is successfully found and configured.

When customizing the printer.cfg file, it is not uncommon for Klipper to report a configuration error. If an error occurs, make any necessary corrections to the printer config file and issue "restart" until "status" reports the printer is ready."</i>

## 10. Configuration checks
https://www.klipper3d.org/Config_checks.html

https://www.klipper3d.org/BLTouch.html#initial-tests

## 11. Calibrations and adjustments
### BLTouch and nozzle offsets
[https://www.klipper3d.org/Probe_Calibrate.html](https://www.klipper3d.org/Probe_Calibrate.html)

<i>"During calibration it may be necessary to set the printer's Z position_min to a negative number (eg, position_min = -2). The printer enforces boundary checks even during calibration routines. Setting a negative number allows the printer to move below the nominal position of the bed, which may help when trying to determine the actual bed position."</i> <b>(change this in printer.cfg under [stepper_z] section)</b>

### Bed tilt using bed levelling screws
https://www.klipper3d.org/Manual_Level.html#adjusting-bed-leveling-screws-using-the-bed-probe

### Bed mesh
https://www.klipper3d.org/Bed_Mesh.html

### Extruder rotation distance
https://www.klipper3d.org/Rotation_Distance.html#calibrating-rotation_distance-on-extruders

# Physical installation of Octopus board and Raspberry Pi
FreeCAD and stl models for mounts for Raspberry Pi and Octopus: https://github.com/juldaani/Ender-5-plus/tree/main/3d-models

<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/mounts1.jpg" width="350"><img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/mounts2.jpg" width="462">

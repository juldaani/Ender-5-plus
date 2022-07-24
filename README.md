# Ender-5-plus
Installation instructions of BIGTREETECH BTT OCTOPUS V1.1 32BIT + TMC2209  + OctoPi + Klipper for Ender 5 Plus (original hardware)

Bigtreetech octopus github:
(https://github.com/bigtreetech/BIGTREETECH-OCTOPUS-V1.0)

Some Octopus installation guide:
https://www.makenprint.uk/3d-printing/3d-printing-guides/3d-printer-mainboard-installation-guides/btt-octopus-guides/btt-octopus-setup-guide/

# Board wirings

## 1. Remove all jumpers from the board
If there are any jumpers attached remove them before proceeding.

## 2. Set jumpers to UART mode for stepper motor drivers
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/uart-jumpers.png" width="650">

## 3. Wiring between PSU and board
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/power_wiring.png" width="650">
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/power-wiring2.png" width="650">

## 4. Hot bed wiring
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/hot_bed.jpg" width="650">

## 5. Install TMC2209 stepper motor drivers
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/stepper_drivers.jpg" width="650">

## 6. Swap stepper motor connector wires
This is the connector to be attached to the Octopus board. Swap 1st and 3rd (from the left) wires. Notice the orientation of the connector. Do this for X, Y, Z and extruder wires.

<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/stepper_wires.jpg" width="350">

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

# Install OctoPi+OctoPrint+Klipper on Raspberry Pi

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

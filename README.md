# Ender-5-plus
Installation instructions of BIGTREETECH BTT OCTOPUS V1.1 32BIT + TMC2209  + OctoPi + Klipper for Ender 5 Plus (original hardware)

Bigtreetech octopus github:
(https://github.com/bigtreetech/BIGTREETECH-OCTOPUS-V1.0)

## 1. Remove all jumpers from the board
If there are any jumpers attached remove them before proceeding.

## 2. Remove MCU power jumper
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/mcu-jumper2.png" width="650">

## 3. Set jumpers to UART mode for stepper motor drivers
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/uart-jumpers.png" width="650">

## 4. Wiring between PSU and board
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/power_wiring.png" width="650">
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/power-wiring2.png" width="650">

## 5. Hot bed wiring
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/hot_bed.jpg" width="650">

## 6. Install TMC2209 stepper motor drivers
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/stepper_drivers.jpg" width="650">

## 7. Change stepper motor connector wirings
This is the connector attached to the Octopus board. Swap 1st and 3rd (from the left) wires. Notice the orientation of the connector. Do this for X, Y, Z and extruder wires.

<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/stepper_wires.jpg" width="350">

## 8. Plug in stepper motor cables
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/stepper_wires2.jpg" width="650">

- MOTOR0: X
- MOTOR1: Y
- MOTOR2_1: Z
- MOTOR3: Z
- MOTOR4: EXTRUDER (E)

## 9. Connect Nozzle Heat to HE0
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/nozzle_heat.jpg" width="650">

## 10. Connect Bed Thermistor to TB
<img src="https://github.com/juldaani/Ender-5-plus/blob/main/pics/bed_thermistor.jpg" width="550">

# S.P.R.K.

There are two main parts to this project:
1. The arduino custom asynchronous stepper code.
2. The robot itself.

# Arduino
- Arudino UNO R3 + Stepper CNC Hat
- Controls 3 stepper motors with A4988 controllers
- Connects to Pi via serial

# Robot
- Raspberry Pi 4 B
- Runs the `robot/Main.py` robot program
- Controls the motors and servo over native GPIO via PWM
- Connects to the Arduino over serial
- Connects to the [operator console](https://github.com/WindowsVistaisCool/sprk-controller) over a socket
- Onboard radio and static-ip'd to `10.8.62.2`

## Robot Code
- Fully custom robot framework
- Subsystem based structure
- Smart telemetry for sending data to the operator console
- Autonomous commands built with threads

#### Simulation Support
- Simulates a serial port, as well as any system outputs
- Simulates GPIO


# Project Flaws
- The intention with the Arduino was the create intuiative, precise stepper control, as well as to be able to use a CNC hat for electronics purposes; however, the latency over serial between the Pi and the Arduino is so bad that this ended up not working well, and is practically redundant.

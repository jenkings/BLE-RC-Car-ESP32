# BLE-RC-Car-ESP32
Alternative Hawdware controller for BLE car models released by Shell

# Hardware replacement for stupid bloatware mobile app
The apps that come with the car are full of pointless and features that just drain the battery unnecessarily. It's also likely that sooner or later these apps will run out of support and the car will be useless without it. So I made a simple hardware driver based on ESP32

# What you need:
- ESP32 WROOM 32D (but alternatively any ESP with BLE support)
- few buttons
- 220Ω resistor
- 10kΩ resistors
- some power supply module (i have used some USB-C battery charger/manager module and LDO)

# Wiring:
- buttons connecting the input GPIO pins to ground via 10kΩ resistors. when pressed, they connect +3.3V to GPIO. (pinning by source code in source)
- LED is connected to ground via 220Ω resistor and to GPIO pin defined by code.
- rest of ESP connected by documentation, for minimal wiring to bootup. Power, reset, boot and serial line for programming

# controlls:
  There are two types of Shell cars. From Brandbase and from BBurago. You can control them both by this controller. By default the controller is set to look for Brandbase car. When you boot the device while holding turbo button, it switches to BBurago car. 
  
  
  # notes:
    - service addresses and characteristics of individual cars may vary. If your car has different addresses, you need to change them in the code. You can find them out, for example, by using various android apps used for BLE debugging
    - lights are not implemented, because i have no car that have lights. Code is prepared for handling that, so you just need to add logic for handling the button and pass it to function, that makes packet for these cars

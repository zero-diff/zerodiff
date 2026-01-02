#What's Testable?

When you start a new design, first look at your design stories to figure out what's testable about the design. Record this in a list that you can review during the test creation process. Not everything you want to test derives from the stories - often we know to perform tests based on experience. Add these "expert" tests to the list as well. As you design the object and create the manufacturing artifacts, you should verify that you accommodated each test from your starting list

###Automated Monkey Testing (AMT)

We discuss AMT elsewhere, but generally, design changes can have unintended consequences that you might not be easy to spot in any one design revision. We once had a situation where one of our EEs accidentally changed the net type for differentially driven bus (RS485). Each individual device tested OK, but when put into a chain close to the rated communication speed and bus length, the devices began to glitch. This test wasn't in our AMT at the time, so unfortunately the device went to the CMS for first articles before we discovered the problem. The goal is to use AMT to test your devices as close to Real World as possible.

> The goal should be to capture as many of these tests in automated processes as possible.

## Ideas for Testing

The following lists should jog your memory of the types of things you should test. 

(Likely the your complete list will be longer than this.)

###EE

The kinds of things that are testable in any EE design might include:

* Input Power Range
* Input Power Transients
* Output Power Load
* Current Draw in All Modes: Active, Standby, Sleep
* Battery Life, Charge Cycles/Performance
* SMPS Output Side DC Voltage Ripple
* SMPS Performance around Extreme Power Conditions (Input, Load, Transients, Battery, etc.)
* Ground Loops, Faults
* Data Bus Integrity, Stability, Impedance Match (I2C, SPI, UART, RS485, GPIO)
* I/O Ports Ground Isolation Protection (Body Diode, Etc. As Needed)
* I/O Port Mechanical Strength (Bosses as needed
* Firmware Storage Banks, Special Values
* Immutable Flash Parameters
* Clocks (Crystals, Oscillators, Derived Clocks, Bus Clocks)
* Switches, Buttons
* IR/Proximity Sensors
* EM Noise Generation (Incl Harmonics)
* Displays, Indicator LEDs
* RF Sensitivity (@ Nominal Freq), Stability, Radiated Power
* Regulatory Certifications (UL, CE, FCC/IC)

###Mechanicals

* Material Durability
* Machined, Molded, Printed Parts Durability
* Connector Protections (Strength, Strain Relief, Bend Radii)
* Display Durability (Scratch/Break Avoidance Measures/Resistance)
* IP rating (Dust, Moisture, Water, Cold, Heat)
* Assembled Device Strength (Drop, Rubber Mallet, and Penetration Tests)
* Mount Strength Test
* Cycles Survivability (Levers, Switches, Buttons, Knobs, Rotating Parts, Doors, Touch Sensors)

###User Experience

* Display Readability
* RF Performance (WiFi, BTLE, 802.15.4)
* Look, Fit, and Finish
* Resistance oo, or Acceptance of, Marring, Wear or Blemishes
* On-boarding
* Reset or Recovery from Weird Modalities
* Satisfies Design Stories
* Partial or Complete Solution to Essential User Task
CurrentSense
============

<img src="media/current_sense_v3_1000x839.jpg" width="30%">

CurrentSense is a tool for measuring current in embedded systems.

Usage
-----

Description of the inputs:

- **Power Supply**: 3.3-6 volts that supplies power to the measurement circuitry.
- **Optional Test Input**: This input can be used to power the load under test.
This is particularly useful for energy-harvesting or other systems where the input
power is not stable.
- **I_Sense**: The measurable output signal that is proportional to current.
To calculate current, divide the I_Sense signal (in volts) by the number
that corresponds to the selected range value. This will return the current
in amps.
- **Range**: Select the maximum current you want to measure. Select this as
close to the maximum you wish to measure as possible.
- **Load VCC Select**: This selects how you would like to power the load under
test. The options
  - Power Supply: Use the input from the power supply that is powering the
  measurement circuitry to also power the load.
  - 3V3: Use the onboard regulated 3.3 V rail to power the load.
  - Test Input: Use the external test input to power the load.
- **To Load**: Connect to VCC or the signal you wish to measure.
- **GND**: A set of ground pins for convenience.

Errata
------

The 300 mA range doesn't seem to work on v3.

----

V2 Notes
--------

<img src="media/current_sense_v2.jpg" width="30%">

You need a power selection jumper. You usually want to power the board externally,
in which case you'll want the jumper in the high position as pictured.

 - Connect external power (3.3-6V) to the EXT header at the top right.
   I usually also connect the external power to the GND header up here.
 - Connect the power supply for your target to VIN header.
 - Connect the VCC of your target to the VCC header
 - Connect the GND of your target to the GND header.
   I usually connect target GND to the GND header at the bottom, whose label is
   occluded by the screw.
 - Hook the scope probe to the test point at the top left (and GND anywhere)
 
The rest of the board is the same idea as above. Choose a range, measure voltage,
divide by the number on the board, get amperage.

# firmware
repo for Marlin firmware

Holds two files, configuration.h and configuration_adv.h
Both are C files and need to be compiled along with the rest of the Marlin repo

DO NOT USE THIS ON A STOCK PRINTER it will probably catch fire.

You MUST have an all-metal hotend or you'll melt your bowden tube if you crank it.

This is specifically to modify an Ender 3 to print Prusament PC/CF blend, because PC/CF is the jam and Prusament PC/CF is magic.

STUFF THIS WILL DO:

Rename your printer "The CARBONator"

Update the thermistor/heater settings for an aftermarket thermistor (I don't remember which type but it's the common one)

Set max nozzle temp to 285

Set shutdown temp to 300

Set max bed temp to 110

Set bed shutdown temp (don't remember to what, probably 125)

STUFF YOU WILL STILL NEED TO DO:

Change/calibrate your esteps for your desired hotend

Make sure your Z offset is correct still

Make sure your nozzle home position is where you want it to be and not, say, off the build plate or in the middle

Set custom G-code to heat the bed to full temp BEFORE heating the nozzle. My standard setup goes: 

  heat bed to 65
  
  heat nozzle to 150
  
  heat bed to 110
  
  HOLD nozzle at 150 until bed is at 110
  
  When bed hits 110, heat nozzle to 270

This will prevent your nozzle from heating up much faster than the bed and oozing PC in the meantime. The bed heats up MUCH slower than the nozzle so it needs to get to full temp first before the nozzle moves on from leveling temperature. If you don't do this your PC will ooze out of the nozzle and your first layer will fail to stick.

If you can successfully follow the directions to flash the firmware, you can successfully look through the configs and hunt out all my changes. I encourage you to do so to learn a bit about firmware!

Once you've figured out my changes or made your own, you must compile them with the compiler of your choice following the directions at <a href="https://marlinfw.org/docs/configuration/configuration.html">THIS PAGE</a>

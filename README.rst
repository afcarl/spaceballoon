This is a simple (<100 lines) python script used to log sensor data, take pictures, and sms gps coordinates during a high-altitude balloon launch. The script was (mostly) successful during a launch on Nov 6th 2011. The gps sms messages allowed the package to be recovered however the sensor data was not appropriately logged.

Sensors and Screen Power
========================

It appears that SL4A/Android shuts down the accelerometers, gyroscopes and magnetometers when the screen is turned off. This was unknown prior to launch and resulted in several hours of erroneous, unchanging data. To fix this bug, a wakelock was added (line 27) which keeps the screen on but dim. This most likely will cause a significant hit on battery life. So, if you want sensor data, leave in the lock and add a backup battery. If you don't want the added weight of the backup battery, remove the wake lock, and all sensor (acc,mag,ori) code just leaving pictures, gps, and sms (which all worked!).

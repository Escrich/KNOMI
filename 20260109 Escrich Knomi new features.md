# Escrich Knomi new features

<br>
<p align="left">
<img src="https://github.com/Escrich/KNOMI/blob/master/knomi_new.jpg" alt='New look' width='50%'>
</p>

# **New look**
<br>
<br>

The idea to make those changes has been based on the need to define new macros those doesn't interfere in the normal behaviour of a working machine

At same time the names under icons have been changed, in order to match with the new features

<br>
<p align="left">
<img src="https://github.com/Escrich/KNOMI/blob/master/knomi_old.jpg" alt='New look' width='50%'>
</p>

# **Old look**
<br>
<br>

Then, old factory macros has been replaced by the new ones, and then the changes look as that:

[gcode_macro _KNOMI_STATUS] > [gcode_macro _KNOMI_STATUS] Remains unchanged

[gcode_macro G28] > [gcode_macro KNOMI_G28]

[gcode_macro BED_MESH_CALIBRATE] > [gcode_macro KNOMI_BED_MESH]

[gcode_macro QUAD_GANTRY_LEVEL] > [gcode_macro KNOMI_GANTRY_LEVEL]

- The macros M109 and M190, looks like not necessary to be changed, despite of not have been changed them, you can set the temperature using this Knomi version, like in the manufacturer one.

- The changes has been made in the firmware source, here you have the complete PlatformIO project, and the bin files ready to be uploaded to your knomi V2.0

> [!TIP]
> My recommendation to use this Knomi software, is to create in your printer, at same level where your printer.cfg is located, a new folder called knomi, and include inside my file knomi.cfg


> [!TIP]
> Then you should include a line inside your printer.cfg
> 
> ```[include ./knomi/*.*]  # Opens access to klipper to use everithing inside the folder knomi ```


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

> [!NOTE]
> As an example I'm reproducing here, what I have inside my knomy.cfg, as you could see, I was prepared the new macros, including the calls to other macros, to do in my printer what I expect to be done, every time I generate a Knomi order.
> 
> Here you have the knomi.cfg I was prepared, and I'm using, in the whole of my machines running Knomi:
>
> ```
>[gcode_macro _KNOMI_STATUS] # Internal original Knomi macros you must include
>description: Just fot internal Knomi use
>variable_homing: False
>variable_probing: False
>variable_qgling: False
>variable_heating_nozzle: False
>variable_heating_bed: False
>gcode:
>  M118 Status desde Knomi
>  M117 Status desde Knomi
>
>
>[gcode_macro KNOMI_G28] # Used to make Home in your machine
>description: Captures the homing orders from knomi, you must include here, in the below lines, your orders to make home at your machine.
>gcode:
>  SET_GCODE_VARIABLE MACRO=_KNOMI_STATUS VARIABLE=homing VALUE=True
>  M118 Centrado desde Knomi
>  M117 Centrado desde Knomi
>  CENTRADO
>  SET_GCODE_VARIABLE MACRO=_KNOMI_STATUS VARIABLE=homing VALUE=False
>
> 
>[gcode_macro KNOMI_BED_MESH] # used to make bed leveling in your machine
>description: Captures the bed mesh orders from knomi, of course in the below lines you must include your orders to make bed mesh adj. at your machine
>gcode:
>  SET_GCODE_VARIABLE MACRO=_KNOMI_STATUS VARIABLE=probing VALUE=True
>  M118 Calibrar cama desde Knomi
>  M117 Calibrar cama desde Knomi
>  Leveling_Bed
>  SET_GCODE_VARIABLE MACRO=_KNOMI_STATUS VARIABLE=probing VALUE=False
>
>[gcode_macro KNOMI_GANTRY_LEVEL] # Used to warrant gantry leveling in your machine, a good idea is to make a Gantry level adjust
>description: Captures the bed leveling orders from knomi, you could use it to make Z-tilt, or any other way to make gantry leveling you want, just changing the lines below
>gcode:
>  SET_GCODE_VARIABLE MACRO=_KNOMI_STATUS VARIABLE=qgling VALUE=True
>  M118 Ajuste horizontal desde Knomi
>  M117 Ajuste horizontal desde Knomi
>  NIVELACION_HORIZONTAL
>  SET_GCODE_VARIABLE MACRO=_KNOMI_STATUS VARIABLE=qgling VALUE=False
>  
> ```


> [!NOTE]
> For more information you can contact me here:
> 
> https://t.me/escrich
>
> https://www.tiktok.com/@josemescrich
>
> https://www.youtube.com/@josem.escrich2610
>
> https://www.printables.com/@Escrich
>
> https://www.github.com/escrich

<br>
<br>


  
  





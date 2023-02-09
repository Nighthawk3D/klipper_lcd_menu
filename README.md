# Klipper LCD Menu

A custom menu system for LCD displays on klipper such as a 12864LCD screen.

## InstalL

`mkdir -p $HOME/printer_data/config/menu && git clone https://github.com/DasBurninator/klipper_lcd_menu $HOME/printer_data/config/lcd_menu`

Add the following to printer.cfg:

`[include ./lcd_menu/lcd_menu.cfg]`

Edit the lcd_menu.cfg file and check to make sure the menus you want enabled are uncommented.

```
[include ./prep_menu.cfg]                       ## Enables Prep menu
[include ./lights_menu.cfg]                     ## Enables Lights menu
[include ./klickyprobe_menu.cfg]                ## Enables KlickyProbe menu
[include ./retraction_menu.cfg]                 ## Enables Firmware Retraction menu
[include ./pressure_advance_menu.cfg]           ## Enables Pressure Advance Tuning menu
[include ./printer_limits_menu.cfg]             ## Enables Printer Limites Menu
[include ./disable_delta_menu.cfg]              ## Disables delta pecific menu options
[include ./network_menu.cfg]                    ## Enables Network Status menu from klipper_network_status plugin. Must have plugin installed from # https://github.com/JeremyRuhland/klipper_network_status
```

## Menu Layout

+ Prep (Disabled When Printing)
+ Print (Enabled During Printing)
  + Resume printing
  + Pause printing
  + Cancel printing
+ Tune (Enabled During Printing)
  + Offset Z:00.00
  + Flow: 000%
  + Speed: 000%
  + Retraction
  + Pressure Advance
  + Machine Limits
+ Control (Disabled When Printing)
  + Home All
  + Home Z
  + Home X/Y
  + Steppers off
  + Fan: OFF
  + Fan speed: 000%
  + Move 10mm
    + Move X:000.0
    + Move Y:000.0
    + Move Z:000.0
    + Move E:+000.0
  + Move 1mm
    + Move X:000.0
    + Move Y:000.0
    + Move Z:000.0
    + Move E:+000.0
  + Move 0.1mm
    + Move X:000.0
    + Move Y:000.0
    + Move Z:000.0
    + Move E:+000.0
+ Temperature
  + Ex0:000 (0000)
  + Ex1:000 (0000)
  + Bed:000 (0000)
  + Preheat PLA
    + Preheat all
    + Preheat hotend
    + Preheat hotbed
  + Preheat ABS
    + Preheat all
    + Preheat hotend
    + Preheat hotbed
  + Cooldown
    + Cooldown all
    + Cooldown hotend
    + Cooldown hotbed
+ Filament
  + Ex0:000 (0000)
  + Load Filament
  + Unload Filament
  + Purge Filament
  + Feed: 000.0
+ Setup
  + Save config
  + Restart
    + Restart host
    + Restart FW
  + PID tuning
    + Tune Hotend PID
    + Tune Hotbed PID
  + Calibration
    + Delta cal. auto
    + Delta cal. man
      + Start probing
      + Move Z: 000.00
      + Test Z: ++
      + Accept
      + Abort
    + Bed probe
  + Dump parameters

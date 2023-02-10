# Klipper LCD Menu

A custom menu system for LCD displays on klipper such as a 12864LCD screen.
Intended to extend the functionality beyond the default klipper LCD menu provides, while being printer agnostic.
Layout is organized into what I would consider a more logical workflow.

## InstalL

```
mkdir -p $HOME/printer_data/config/menu && git clone https://github.com/DasBurninator/klipper_lcd_menu $HOME/printer_data/config/lcd_menu
```

Add the following to `printer.cfg`:

`[include ./lcd_menu/lcd_menu.cfg]`

## Updates

### Manual Update

```
cd $HOME/printer_data/config/
git pull
```

### Moonraker Update Manager

Updates require that Moonraker is run in debug mode for unofficial repos. See the Moonraker documentation below:
[Enabling debug mode in Moonraker](https://moonraker.readthedocs.io/en/latest/installation/#the-environment-file)

Once Moonraker is running in debug mode the follow can be added to the `moonraker.conf file`

```
[update_manager client klipper_lcd_menu]
type: git_repo
channel: dev
primary_branch: main
path: ~/printer_data/config/lcd_menu
origin: https://github.com/DasBurninator/klipper_lcd_menu
managed_services: klipper
```

## Menu Layout

+ Prep (Disabled When Printing)
  + Prep ABS
  + Prep PLA
  + Home
  + Z Tilt > Park
  + QGL > Park
  + Park
  + Park Rear
+ Print (Enabled During Printing)
  + Resume printing
  + Pause printing
  + Cancel printing
+ Tune (Enabled During Printing)
  + Offset Z:00.00
  + Flow: 000%
  + Speed: 000%
  + Fan speed: 000%
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
+ Network
  + mDNS
  + Eth IP
  + Wifi SSID
  + Wifi IP

## Changelog

### Feb 9th 2023

+ Initial set of commits and debugging
+ Moved network_status menu into lcd_menu.cfg and enabled conditionally
+ firmware_retraction and pressure_advance tuning menus now conditional of those options being enabled.

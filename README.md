# Klipper LCD Menu

A custom menu system for LCD displays on klipper.

Install:

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

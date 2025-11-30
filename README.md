# Sovol-eddy-current-macros
These macros are intended for the Sovol klipper version that is shipped with the Sovol Eddy Kit. The macros are updated versions for `START_PRINT`, `END_PRINT`, `CLEAN_NOZZLE`. There are also new `PERGE_LINE` and `SAVE_LIVE_Z` macros, to trigger an purge line before starting the print and saving the current live z adjustment, respectively. Add the macros to the `macros.cfg` file (backup the old one before) and restart klipper.

The macros is working good on my printer, but double check everything before adding them to yours. Use them on your own risk.

# Usage in Orca
Backup your configuration, then go to `Machine G-code` -> `Machine start G-code`. Replace all the content in the field with:

`START_PRINT BED=[bed_temperature_initial_layer_single] NOZZLE=[nozzle_temperature_initial_layer] CLEAN=200 IDLE=170`

`PURGE_LINE`

The `CLEAN` is the nozzle tempature when cleaning the nozzle, and `IDLE` is the nozzle temperature when meshing the bed.

Go to `Machine end G-code`. Replace everyting in the field with:
`END_PRINT`

# Live Z adjustment
You can adjust the first layer distance on the printer control panel at the front of the printer. When you are happy with the result, you go to the klipper console and type `SAVE_LIVE_Z`. The adjustment is then saved and will be loaded for future prints!
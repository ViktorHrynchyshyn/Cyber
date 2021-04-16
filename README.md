
# cyber60

A DIY-friendly 60% using nRF52840 and ZMK: the cyber.

## Status:
**CAUTION**: Use Rev A2 for MX, flipped transistor in A1. SMK and ALPS Rev A1 does not have this issue. Revision B1 have been tested and fixes made in B2. B2 should be safe to use, but not prototyped yet.

## Software:
- Link to zmk-fork: https://github.com/4pplet/zmk-config
- Link to zmk-config (uf2-files in actions): https://github.com/4pplet/zmk-config
- Bootloader used: pca10056_bootloader-0.3.2_s140_6.1.1.hex

## Specs cyber60:
- Module: Holyiot YJ-18010
- Standard Tray Mount support
- Non constant drain battery measurement
- Lipo charger for single cell 3.7V li-po/li-ion batteries
- RGB-led under Capslock for multi function indicator (not under switch on SMK-version)
- Possible to build with just a soldering iron (no underside pads etc)
- Three versions running the same FW-implementation. One MX, one ALPS, one SMK
- USB horizontal placement is classic GH60, same as GH60, plain60, voyager60 etc.
- (rev b) Underglow for cozy glow
- (rev b) Buzzer for indicator or sweet tunes
- (rev b) Rotary encoder at right most posision in split backspace or off board
- (rev b) Reverse polarity protection for battery

## Todo:
- Prototype revision B2
- Properly verify current consumption
- Properly verify charge current
- Implement buzzer and RGB capslock-led in ZMK
- Fork bootloader and add support for bootloader indication on capslock led.

# MX-version
## Layout support cyber60 MX-version:
![alt text](./readme-images/layout_support_cyber60-mx_Rev_A2.jpg "Layout support")

## Altium view of - cyber60 MX-version:
![alt text](./readme-images/cyber60-mx_Rev_B2.jpg "PCB View - Rev B")

## MX Revisions:
- A1 - initial revision/prototype
- A2 (prerelease) - flipped PMOS-transistor error in Rev A1. Added pulldown on enable to battery voltage measurement circuit, so it does not have to be disabled in code, only enabled. Minor silkscreen changes.
- B1 (prerelease) - Adding underglow, buzzer and rotary support. Simplifying voltage measurement circuit (tiny bit more leak current). Changing matrix to duplex.
- B2: Fixing underglow issue, adding n mos to fully turn off the p mos that powers the underglow. Adding reverse polarity protection for the battery.

# ALPS-version
## Layout support cyber60 ALPS-version:
![alt text](./readme-images/layout_support_cyber60-alps_Rev_A1.jpg "Layout support")

## Altium view of - cyber60 ALPS-version:
![alt text](./readme-images/cyber60-alps_Rev_B2.jpg "PCB View - Rev B")

## ALPS Revisions:
- A1 - initial revision/prototype, builds on MX rev A2
- B1 (prerelease) - Adding underglow, buzzer and rotary support. Simplifying voltage measurement circuit (tiny bit more leak current). Changing matrix to duplex.
- B2: Fixing underglow issue, adding n mos to fully turn off the p mos that powers the underglow. Adding reverse polarity protection for the battery.

# SMK-version
## Layout support cyber60 SMK-version:
![alt text](./readme-images/layout_support_cyber60-smk_Rev_A1.jpg "Layout support")

## Altium view of - cyber60 SMK-version:
![alt text](./readme-images/cyber60-smk_Rev_B2.jpg "PCB View - Rev B")

## SMK Revisions:
- A1: Initial revision/prototype, builds on ALPS rev A1
- B1: (prerelease) - Adding underglow, buzzer and rotary support. Simplifying voltage measurement circuit (tiny bit more leak current). Changing matrix to duplex.
- B2: Fixing underglow issue, adding n mos to fully turn off the p mos that powers the underglow. Adding reverse polarity protection for the battery.

## Note:
- Voltage measurement and power consumption for revision A1/A2 is not fully verified
- RGB-led is not implemented in ZMK yet
- Buzzer support is not implemented in ZMK yet
- B2-revision should be safe to use. B1 is tested with issues, issues fixed in B2 but not prototyped yet.

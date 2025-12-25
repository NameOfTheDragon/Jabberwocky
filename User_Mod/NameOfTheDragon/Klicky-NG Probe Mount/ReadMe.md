# Klicky-NG Probe Mount for Jabberwocky Toolhead

![Toolhead Mkunt with Klicky-NG probe](<images/Toolhead Mount and Klicky-NG probe.jpg>)

## Why Klicky-NG?

Klicky Probe (and the revised Klick-NG) are the unsung heroes of Voron Design. It uses a simple reliable microswitch in a magnetic detachable probe body. Because it detaches and doesn't have to live right next to the hot end, it's less likely to suffer from melting or thermal issues. A simple switch doesn't suffer from thermal drift like most eddy current and inductive probes, so it requires less calibration and maintenance.

But there's more. Klicky Probe enables one important capability that most fixed probes cannot deliver: Automatic Z-Offset Calibration.

Using the [Klipper Z Calibration add-in](https://github.com/protoloft/klipper_z_calibration), Klicky Probe is able to measure and set the Z offset. When added to your `PRINT_START` macro, this means you will never have to adjust the Z offset because you changed nozzles, build plates, or filament temperature, or doe to thermal expansion in the printer frame.

The Z offset is measured by homing the nozzle on the Z endstop as normal, then homing the probe body on the Z endstop (this is the part other probes can't do without crashing the nozzle) and finally probing the centre of the bed. A bit of simple arithmetic then gives the absolute Z offset of the nozzle. So every first layer comes out perfect.

### Why Klicky-NG and not Klicky or Unklicky?

- The original Klicky probe required the use of glue to hold the magnets in place. CA glue starts to break down as low as 80°C so over time life in a hot printer inevitably leads to the magnets falling out. Klicky-NG ("No Glue") doesn't need any glue and uses screws to hold the parts together.

## Adapting for Jabberwocky Toolhead

The original Klicky Probe design had mounts for the StealthBurner print head, and a selection of brackets for various printers. Unfortunatelt none of these can be used with Jabberwocky Toolhead, which uses a different X-carriage carrier. Therefore, we need a probe mount for the Jabberwocky X-carriage, plus a bracket to mount the docking station onto the rear of the Voron gantry.

You will need to print the following parts from the [Klicky Probe repository](https://github.com/jlas1/Klicky-Probe/tree/main):

- [Klicky-NG probe body](https://github.com/jlas1/Klicky-Probe/blob/main/Probes/KlickyNG/STL/KlickyNG_Probe_body.stl)
- [Klicky-NG probe insert](https://github.com/jlas1/Klicky-Probe/blob/main/Probes/KlickyNG/STL/KlickyNG_Probe_insert_3mm.stl) (note: there are 2.7mm and 3mm variants based on magnet height, I recommend the 6x3 mm magnets)
- [Klicky-NG Dock](https://github.com/jlas1/Klicky-Probe/blob/main/Probes/KlickyNG/STL/KlickyNG_Probe_Dock.stl)
- [Klicky-NG Cap Magnet Helper Body](https://github.com/jlas1/Klicky-Probe/blob/main/Probes/KlickyNG/STL/KlickyNG_cap_magnet_helper_body.stl)
- [Klicky-NG Cap Magnet Helper Cap](https://github.com/jlas1/Klicky-Probe/blob/main/Probes/KlickyNG/STL/KlickyNG_cap_magnet_helper_cap.stl)
- [Klicky ABSB Mount Front](https://github.com/jlas1/Klicky-Probe/blob/main/Probes/KlickyNG/STL/KlickyNG_ABSB_mount_front.stl)
  
Plus the two printed parts from this repository:

- Toolhead Mount
- Voron 2/Trident Gantry Bracket

You will also need:

- Some silicone insulated wire for electrical connections
- An appropriate crimp connector and crimps to attach the probe to your toolhead board
- 4 M3x4mm heat-set brass inserts
- 5 M2 x 10 mm self-tapping screws
- One microswitch, Omron D2F-5 (or D2F-5L with the lever removed)
- At least eight 6 mm diamter x 3 mm tall N35 (or stronger) neodymium magnets, plus another 3 to help with assembly (you will definitely need the help!)
- 2 off M3 x 18mm or 20mm screws (for the dock).
- 2 off M3 x 8mm hex caphead screws for attachment to the Jabberwocky X carriage.
- 2 off M5 x 10mm button head screws (for the gantry bracket)
- 2 off M5 Hammer head T-nut (for the gantry bracket)

## Printing

Use the Voron standard print settings with 4 perimeters and 40% infill.

The toolhead mount needs supports, I recommend "snug" style, here are my settings and print orientations in Orca Slicer:
![Orca Slicer Print Orientation and Supports](pictures/Print-orientation-and-Supports.png)

Use ABS or a reinforced ABS filament material such as ABS-GF.

## Assembly

1. Add heat-set brass inserts M3x4mm into the the two holes on top of the toolhead mount, and the two holes on the front of the gantry bracket.
2. Thread wires through the holes in the `Toolhead Mount` in the same way you would have for the equivalent Voron StealthBurner mount. This is a bit awkward in my design because there's not much room to work, so twist the bare wires tightly and be patient and eventually you'll get it to go through. It may help to clean out the holes with a 1.9 mm drill bit if you have one, or a 2mm bit may also work.
3. Assemble the magnets and the `Klicky ABSB Mount Fron` part, using the helper tool - refer to the Klicky-NG instructions for how to do this.

Follow the Klicky Probe assembly instructions. Assembling the magnets is a bit fiddly and can be frustrating as the magnets want to jump out of position. The Magnet Helper parts are disgned to assist with this.

T

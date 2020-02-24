This OpenSCAD library was created to make it easy to create board game inserts with lids for either horizontal or vertical storage, without any programming required.

Create a settings file, in which you specify the box dimensions and any number of compartments, their sizes, what kind of pieces it holds, etc, and the script will do the rest.

Inserts:

- Pandemic: https://www.thingiverse.com/thing:3412724
- Mice and Mystics: https://www.thingiverse.com/thing:3435429
- Indonesia (upgraded goods): https://www.thingiverse.com/thing:3446879
- Indonesia (upgraded goods and ships ): https://www.thingiverse.com/thing:3454636
- Pax Emancipation: https://www.thingiverse.com/thing:3450282
- Bios: Genesis: https://www.thingiverse.com/thing:3452368
- Greenland/Neanderthal: https://www.thingiverse.com/thing:3469793
- Pax Porfiriana (Collector's Edition): https://www.thingiverse.com/thing:3478944
- Pax Renaissance: https://www.thingiverse.com/thing:3479114
- High Frontier (3rd): https://www.thingiverse.com/thing:3482341
- Bios: Megafauna: https://www.thingiverse.com/thing:3493660
- 1830: https://www.thingiverse.com/thing:3499314
- Sword & Sorcery: https://www.thingiverse.com/thing:3515523
- Mansions of Madness 2nd edition persons container: https://www.thingiverse.com/thing:3527361
- Stuffed Fables: https://www.thingiverse.com/thing:3535505
- Star Trek: Frontiers: https://www.thingiverse.com/thing:3538652
Cheers.

## CHANGE NOTES

### v2.00

Version 2.00 is a major rework and is not compatible with previous versions. 
The major changes are
- "type" has been replaced with explicit specification of a-la-carte features.
- Labels have more options.

### Details: 

- g_b_visualization is now purely for previewing and cannot be exported (accidentally or otherwise)
- components are now colorized for easier debugging of overlaps
- labels
    - New field, "placement" (default "center") specifies where to place the text relative to the compartment. 
        Supported values are "center", "below", "back", "left", "right", "back-wall", "front-wall", "right-wall", "left-wall".
         "center" places the text in the FRONT of the compartment while the others place it on one of the adjacent partitions.
         "-wall" placement places the labels on the wall of the compartment.
    - New field, "offset" (default "[0,0]") specifies the amount to adjust the position of the text, in the x and y directions.
    - New field, "font" (default "Liberation Sans:style=bold") specifies a font to use.
    - The field "rotation" now specifies an angle in degrees and supports any angle.
    - The field "size" now supports (and defaults to) "auto," which attempts to fit the text into its region.
    - When using an array of labels, the labels are no longer read in reverse order and should appear as specified in the array.
- boxes
    - New field "lid_notches" (default "true") specifies whether the box has notches or not.
    - New field "fit_lid_under" (default "true") replaces g_b_fit_lid_underneath and allows per-box specification on whether the box should be printed to allow the lid to fit underneath.
    - New field "lid_hex_radius" (default "4.0") specifies the radius of the honeycomb hexes in the lid.
- components
    - The field "rotation" now respects any value and specifies the rotation of the entire component.
    - The field "type" has been deprecated. All of the functionality has been moved into individual component features.
    - The field "partition_size_adjustment" has been deprecated.
    - New field "padding" (default "[1.0, 1.0]") specifies the size of the partitions between compartments, in the x and y directions.
    - The field "partition_height_adjustment" has been renamed "padding_height_adjust."
    - The global "g_partition_thickness" has been deprecated.
    - The global "g_finger_partition_thickness" has been deprecated.
    - New field "margin" (default "[false,false,false,false]") specifies which sides of the component will have a partition. The sides are [FRONT,BACK,LEFT,RIGHT].
    - New field "cutout_sides" (default "[false,false,false,false]") specifies sides of the compartment to place finger cutouts. Sides are [FRONT,BACK,LEFT,RIGHT]. 
    - New field "shape" (default "square") specifies a geometric shape for the compartments. Supported shapes are "hex", "hex2", "oct", "oct2", "round", "square", "fillet".
    - New field "shape_rotated_90" (default "false") specifies whether the shape should be rotated 90 degrees.
    - New field "shape_vertical" (default "false") specifies whether the shape should be rotated vertically.
    - New field "shear" (default "[0,0]) specifies angles by which to shear the component in the x and y directions.
- misc
    - misc bug fixes

### v1.17

- Updated examples with more properties.
- Added examples of partition_size_adjustment and partition_height_adjustment

### v1.16

- Fixed error in rotated hex chit_stack computation
- Added "hex_rotated" shape, which is has point-side-down

### v1.15

- Bug fixes and cleanup

### v1.13

- Vertical chit stacks now rotate correctly.
- Finger cutouts now go through the bottom. This saves material and makes it easier to get pieces out.
- Added shaped holes in the bottom of vertical stacks.

### v1.12

- Better support for compact fits.
- Bug fixes and optimizations.

### v1.11

- Now supports rotation of features.

### v1.10

- Under-box storage of lid without need for supports.
- Misc optimizations and bug fixes
- Moved Mice and Mystics to its own thing (https://www.thingiverse.com/thing:3435429)

### v1.09

- More work on visualization.
- Added option to print extra thin lids.
- Added option to create insets at box bottom that allow lid to be stowed under during play.
- Added simple solid labeled lid option.
- Misc fixes and optimizations.

### v1.08

- Added ability to visualize the inserts closed and arranged as they will be placed in the
- game box.

### v1.07

- Enlarged lid hexes to shorten Openscad rendering.
- Added lid label offset to help legibility.

### v1.06

- Added native honeycomb lid pattern.
- Added ability to label lids.
- Updated Mice and Mystics insert.

### v1.05

- Added ability to label compartments individually within a component.
- Added Mice and Mystics example.

### v1.04

- Added support for labelling compartments.
- Moved Pandemic to its own thing. (https://www.thingiverse.com/thing:3412724)

### v1.03

- Added support for negative position values, which position relative to the other side of the box.
- Fixed lid fitting issue.
- Clamped max depth of finger cutouts.

### v1.02

- Added support for round and hex chit stacks using the "shape" property.
- Misc bug fixes.

### v1.01

- Added support for a chit stack compartment.
- Added an example SCAD file that features every compartment type.
- Fixed misc bugs.
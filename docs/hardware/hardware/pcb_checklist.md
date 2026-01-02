## PCB Release Checklist

## Directory Setup

* In Git: Select or create repo for a new design.
* In Eagle Control Panel (main window), add the repo or Git folder to “Projects” drop down
         
##Project Setup

*  Within the “Projects” drop down of the Control Panel, select desired folder, right-click the folder and select “New Project”. This will create a RED new project folder inside it which designates a project.
* Double-click the folder to enter into the project (denoted by a GREEN dot next to the folder when it is open) or double-click it again to close it (green light dot turns grey)
         
##Library Setup

* A set of common / past components is currently stored in the Git under “Archive”  -> “Eagle Libraries” -> “GW-devices”; or in the Control Panel under “Libraries” -> “Eagle Libraries”. For KW2-specific parts, there is a library “KW2” in the same directory.

NOTE: Library locations and content should probably be adjusted. Current common parts include a set of SMD resistors, capacitors, inductors, buttons, barrel jacks, several number displays and miscellaneous connectors.
         
##Schematic creation

* If not already open, double-click on Project folder or right-click -> “Open” in the Control Panel to open the project
* In Control Panel, “File” -> “New” -> “Schematic” or right-click on Project folder, then “New” -> “Schematic”. This opens a Schematic Editor window.
* Make sure board and schematic are consistent - ALWAYS have both layers open at the same time in Eagle!
         
##Library creation

* To create a new part, a schematic symbol (“symbol”), footprint (“package”) and association between the two (“device”) is required.
* In the top drop down (“Libraries”) of the Control Panel, navigate to or add your library.
* Double-click to open it, this will generate a new window.
* To create a schematic symbol, click the gate symbol in the menu bar. Select a current symbol to edit or create a new one. This will open a further new window where a symbol can be drawn.
* Draw & place pins, rename pins by datasheet / function if desired
* To create a footprint, click the chip symbol in the menu bar. Select an existing or create a new footprint in the same manner as above.
    *  Name pads by datasheet / function if desired
* To associate the symbol with the footprint, click the button with 4 gates in the menu bar. Either enter a new device name or select an existing one.
    *  Add schematic symbol via the gate button on the left menu panel (under the wrench button) and place it at the origin marker unless otherwise required.
    *  Attach a footprint by selecting the “New” button at the bottom of the right panel.
    *  Click “Connect” in the same panel to associate footprint pads with symbol pins
    *  The part can now be used in schematic creation.
    *  Layout creation

* Once a schematic is completed, convert it to a layout. “File” -> “Switch to board” (in Schematic Editor) will create a layout file with the same name in the project in the Layout Editor. If all symbols are part of a correctly created device, the footprints should all be added automatically.

##Layer settings

* Click on the magnifying glass with wires in it (bottom most button on the right column of the left-side menu panel)
* Select the “Layers” tab and adjust as required. Note: Eagle by default numbers layers starting at 1 for the top layer and 16 for the bottom layer. A 2-layer board thus has top = 1 and bottom = 16, whereas a 4-layer has top = 1, inner1 = 2, inner2 = 15 and bottom = 16. NOTE: The example setup is incorrect; using it will result in a stackup numbered 1,2,3,16 which breaks various other features in Eagle. Ensure your setup is numbered correctly!

##DRC settings

* In the same panel, adjust minimum feature size under “Sizes”, trace / space / board edge clearances under “Clearance” and minimum annular rings for vias and pads under “Restring”. Additionally, in “Misc”, check the “Check angle” box for best results.
             
##Verify a design in Eagle

* DRC (Design review check) should have no warnings or errors.
* ERC check should have no warnings or errors.
         
##Exporting a design

* CAM files accessed via the blue film-reel icon on the top menu or under “File” -> “CAM Processor” of the Layout Editor.
* Manufacturing files:
    * Gerber files (copper, silk, mask, stencil layers)
    * Codeshelf has CAM files under “Archive” -> “CAM_ULP”
    * For each file, ensure the correct layers and features are checked. Defaults for copper are 1,2,15,16 for 4-layer boards and 1,16 for 2-layer. Adding the board outline to each file is not a bad idea either.
    * For each file, ensure the output directory is correct. By default, the file will be created in the project directory. To change this, each file must be adjusted individually (!)
* Drill file (holes)
    * Codeshelf does not have a CAM file for drills. Eagle provides one under “CAM Jobs” in the Control Panel (or under “cam” in the Eagle install directory)
* Centroid
* BOM (from schematic)

##Create a New Library Part

##New Library Part Review

* Schematic symbol corresponds to function / correct number of pins.
* Use a good naming scheme for the schematic pins.
* Pins on schematic match pins on package.
* Package geometric center is the part’s centroid.
* Correct footprint is attached (e.g schematic and symbol have same number of pins).
* Footprint has pins in correct order (check layer for mirroring possibilities).
* Print 1.0 scale version and verify that the footprint matches the part and datasheet.

##Release to Manufacturing Checklist

##Schematic review:

* All parts have assigned and CORRECT manufacturers and part numbers (check assigned datasheet vs symbol pin numbers, for instance)
* Pins on devices labelled as according to datasheets
* Nets named correctly (by function or pins)

##Layout review

* Fiducials for assembly (3 per side)
* Check net connectivity
* Make sure copper pours are present on all layers AND ACTUALLY POURED
* Check Reference Designators & other labelling are on the correct silkscreen layers
* Check DRC for correct trace / space and minimum silk screen width according to manufacturer
* Correct version number applied (out of house do NOT include “P” suffix)
* All polarized components checked
* Check the orientation of all connectors
* Bypass capacitors located close to IC power pins
* PCB has power rail test points, and test points for important signals, all labeled and accessible
* Layout PCB so that any rework or repair of a component does not require removal of other components
* Mounting holes electrically isolated or not
* Proper mounting hole clearance for hardware
* SMD pad shapes checked
* Check for traces running under noisy or sensitive components
* No vias under metal-film resistors and similar poorly insulated parts
* Check for traces which may be susceptible to solder bridging if not masked (OFN pins etc)
* Check for dead-end traces, unless used on purpose
* Provide multiple vias for high current and/or low impedance traces
* Component and trace keepout areas observed
* Ground planes where possible
* Trace width sufficient for current carried
* No silkscreen legend text over vias (if vias not soldermasked) or holes
* All legend text reads in one or two directions
* Company logo in silkscreen legend
* Date code on PCB
* All silkscreen text located to be readable when the board is populated
* All ICs have pin one clearly marked, visible even when chip is installed
    * Ensure it is in silkscreen layer
* CAD design rule checking must be turned on
* High frequency circuitry precautions observed
* Soldermask does or does not cover vias
* PCB thickness, material, copper weight noted
* Thermal reliefs for internal power layers
* Solder paste mask openings are proper size
* Blind and buried vias not allowed on multilayer PCB unless required
* Finished hole sizes are >=10 mils larger than lead
* All capacitors have been designed with a 50 percent voltage margin.
* All new components/suppliers must be reviewed for component obsolescence and component availability
* All PCBA designs must have the revision level released to Document Control and assembly drawing indicating any special assembly/design requirements that violate the standard PCB assembly conventions (i.e. components on the solder side, cuts and jumps, heat-sink assemblies, etc.). - Open question for Calla / Nate
* All power traces wide enough for anticipated current

##Export Production Files

* BOM
    * Check whether existing columns are: 
        * Qty
        * Value
        * Package
        * Parts/Reference Designator
        * MFGN
        * MFGP
        * Notes
    * Gerbers
        * For each file, make sure the right features are selected as well as the board outline
    * Drill file
        * Visual inspection to see if holes line up
    * Centroid

##Review Gerber Files

* Check to see if right files exists
    * Top silk
    * Top mask
    * Top paste
    * Top copper
    * Inner copper 1
    * Inner copper 2
    * Bottom copper
    * Bottom paste
    * Bottom mask
    * Bottom silk
    * Top centroid
    * Board outline
    * DRD (drill file)
* Open in a gerber file viewer (GerbV, ViewMate)
* Check to see if each layer contains what you expect (traces, pours, holes)
* Ensure correct placement of all layers (check whether visually stacks up correctly)

##PCBA DESIGN REMINDERS

* Nets named correctly (by function or pins).
* Lay down ground plane, only after ground traces.
* Check orientation of mating connectors in associated designs

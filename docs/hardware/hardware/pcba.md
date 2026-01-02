##Step 0: Kick-off Development Cycle

The kick-off is essential to inform everyone that the object is now in-flight for another development cycle.  The steps for kick-off are:

* Nominate a "person in charge" to manage this object through the process.
* Send an announce email to the development group.
* Schedule kick-off meeting
* Create a JIRA epic for the object.  E.g. "CHECON-PCBA-New Display"
* Create relevant JIRA stories
* Go to the hardware release page and update the relevant information for the device and any relevant sub-component projects: Current and Planned Hardware Releases
* Print this page and make sure it follows the device through the development cycle.
* **Read with a pen!**

##Step 1: Create Design Artifacts (Engineer)

The first step to the design and manufacture of a PCB/A is to create all of the relevant design and production artifacts (files).
EagleCAD schematic

The first step for any new design is to capture it as an EagleCAD schematic.  This is the architectural design document of the circuit.  The schematic contains all of the parts in the design and is the central source of the BOM for any design by capturing component annotations.  (Later we'll get these annotations from Octopart).  The format for naming our designs is to use a six-character code like POSCTL and then the design files will be POSCTL.sch and POSCTL.brd, etc.
EagleCAD layout

Once the schematic is complete we layout the physical board in what will become the final PCB.  This layout includes the board stack-up, because each layer of the stackup is a layer in EagleCAD.  Once the layout is complete, EagleCAD can generate the Gerber files, Excellon Drill files, Centroid files and BOM for the design that are suitable to manufacture the board to completion.  For this reason any version of the EagleCAD file stored in git should always be able to generate the master files needed to manufacture the part.

##Step 2: Run ERC / DRC checks against manufacturer capabilities file

EagleCAD has the ability to create a design rules check file, and it should match your manufacturer's capabilities for the kind of board you want to make. It's a good idea to have both a "standard" and "advanced" DRC file. The standard file should be for everything that's easy to run (and somewhat cheap). The advanced file should be for when you have tight tolerances, for example when you need narrow vias. Because we are able to cut our own PCBs on a mill, we generally use "standard" to match the mill's capability since it's usually much looser than the "low cost" option at most fab houses. Advanced designs are usually beyond the capability of our mill, or require the machine operator to make special allowances for end mills. (Generally we do not run 0.025mm end mills because they break easily and are somewhat finicky.)

##Step 3: Create a Prototype Release

To validate the design we produce an in-house prototype.  This is a somewhat lightweight process where the engineer commits the Eagle schematic and board files to git.  This is not a tagged release, because there may be many of them.  

* The engineer commits the Eagle schematic and board files.
* The engineer creates a PCB blank template and mails it to the prototype shop manager.
* The engineer creates a prototype BOM and mails is to the prototype shop manager.
* The prototype shop manager schedules the board build and coordinates with the production manager to acquire any missing BOM components.
* The prototype shop converts the Eagle board file into gcode using the "board blank" template.
* The prototype shop cuts the PCB.
* The prototype shop assembles the PCB, that potentially includes new enclosures and mechanicals, and delivers it to the HWTE.

When boards cannot be prototyped in-house:

* Email production files to the ProdMgr along with requested turnaround time and quantities. 
* RFQs will be placed.
* Prototypes will be made at a CMS.

Any sub-assembly which versions separately can be released (to prototype or production) without releasing the other components of the assembly.

##Step 4: Test the Prototype

The HWTE runs all of the relevant tests to validate that the prototype is correct.

* Program and test the device in the manufacturing/test jig.
* Run the MAT, if possible.
* Run the device in the AMT (units tests and E2E tests)

If the HWTE approves the device for production, then proceed to step 4, otherwise go back to step 1.

##Step 5: Create the Pre-Release/Release Package (Engineer)

There are steps to manufacturing a complete PCB/A that the EagleCAD files do not capture.  These include how to resolve ambiguity in the silkscreen (when parts are very close together), any special instructions, UL documentation, PCB stackup notes such as fiberglass type (eg. FR4, copper weights, etc.).

> Note on fab files from the CMS:

> Specify board material, surface finish (pads), electrical (nickel, gold), mask, thickness, already have a drill file, net list testing by fab shop is required. Controlled impedance is not standard – if you don’t want it, don’t include in notes. Include UL related notes for agency approvals – it’s standard for fab shops. We should have UL in drawings and require it in boards. Need for UL has to do with plugging into the wall and certifying for safety. Also, there are specific components that need to be UL rated. All components are UL certified. If we don’t specify, we don’t have a document trail and can get dinged if anybody asks. Term is something about UL flammability rating as an etch on the board.

For a PCB/A manufacturing run, the release package contains the following documents.  The file names derive from the base product ID, e.g. POSCON.  From that all PCB/A files end in POSCON.PCB.

File | Example | Prod/Design Folder
-----|---------|-------------------
Schematic | POSCON.PCB.sch | Design
Board | POSCON.PCB.brd | Design
Board Outline| POSCON.PCB.FAB | Production\Gerber
Top Copper | POSCON.PCB.LAY1 | Production\Gerber
Inner Copper 1 | POSCON.PCB.LAY2	 | Production\Gerber
Inner Copper 2 | POSCON.PCB.LAY3 | Production\Gerber
Bottom Copper | POSCON.PCB.LAY4 | Production\Gerber
Bottom Soldermask | POSCON.PCB.SMB | Production\Gerber
Top Soldermask | POSCON.PCB.SMT | Production\Gerber
Bottom Solderpaste | POSCON.PCB.SPB | Production\Gerber
Top Solderpaste | POSCON.PCB.SPT	 | Production\Gerber
Top Silkscreen | POSCON.PCB.SST | Production\Gerber
Bottom Silkscreen | POSCON.PCB.SSB | Production\Gerber
Excellon Drill File | POSCON.PCB.drd | Production\Gerber
Centroid File | POSCON.PCB_centroid.csv | Production\Gerber
BOM | POSCON.PCB.BOM.xlsx | Production
Fabrication Notes | POSCON.PCB.FAB.txt | Production
Assembly File | POSCON.PCB.ASSY.txt | Production
Test File | POSCON.PCB.TEST.txt | Production
ECO | POSCON.PCB.ECO.xlsx | Production

##Step 6: Commit the Pre-Release Package to Git (Engineer)

* Commit the above files to github.
* Tag the commit ID (the git commit SHA1) as a release candidate (RC).  E.g. V1.1-RC1

##Step 7: Release Checklist (Engineer, HWTE and ProdMgr)

All files in the Release Candidate repository must be checked against a printed Release Checklist and a printed copy of this document for completeness and accuracy. 

Checklist: Codeshelf EE Design Process and Release

##Step 8: Release Tag (Engineer)

This step includes a complete review of the design and BOM. When the checklist is passed, the Git repository will be tagged as a release.

##Step 9: Arena (ProdMgr)

At this point we have an object that is manufacturable and if it passes all pre-production tests it will never, ever change again.  For this reason it is now safe to enter all pre-release package files into the Arena database before continuing the release process.  Reference the Arena process document at: <add link to Confluence document>

##Step 10: Build First Articles (ProdMgr)

Once a part releases prior to manufacture we send the release package to the CMS for a request to quote/manufacture.   The CMS is not allowed to make any changes to this package, including vendor or part substitutions, without first looping back to Codeshelf to obtain an ECO.  The most common case is that the CMS requests permission to swap parts or vendors for passives.  When we receive the ECR from the CMS, we review it and decide if we will approve the change.  If we agree to approve the change then we capture that change into the appropriate documents (BOM, ECO, etc.) and re-release the product with these changes.

When the device comes back from the fab, it gets assembled by the prototype shop (if not already assembled by the outside CMS). 

Check whether CMS has any modifications to the design. If so, the design needs to be revised and re-versioned. 

##Step 11: Test and Validate First Articles (HWTE)

* Program and test the device in the manufacturing/test jig.
* Run the MAT, if possible.
* Run the device in the AMT (units tests and E2E tests)

If approved for production then the proceed to step 12, otherwise proceed to step 1.

##Step 12: Release Announcement (ProdMgr)

If the First Articles are proven good, a release announcement will be issued, the Current and Planned Hardware Releases document will be updated, and the item will be cleared for further production.

##Step 13: Post Release Review (ProdMgr)

* Review the release process with the Engineer
* Change the release process document as needed
* Change the release checklists as needed
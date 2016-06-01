##Glossary

Term | Description | Example
-----|-------------|--------
Raw Material | Any 3rd party item that we purchase and store unaltered. | LED strips
Value Add | A manufacture step or process where Codeshelf modifies one or more raw materials into a WIP or finished good. | Cut holes in NEMA enclosures
Work In Process (WIP) | Raw materials (or other WIP) that have been through a value-add step. | NEMA enclosures with holes cut in them
Finished Good | A complete item ready for installation or sale. | Aisle Controller
Kitting | Combining raw material and WIP into a kit to send to a value add step or to a customer. | A box of parts to make one or more CHEs
Gerber File | A machine file used to generate PCB copper layers.	 
Excellon (Drill) File | A machine file used to generate PCB vias and holes.	 
Centroid File | A machine file used to show the centers of ICs placed on a PCB by a pick-and-place machine	 
Bill of Materials | A list of component parts needed in a kit to build a WIP or finished good part. | Components needed to build a particular PCBA.
PCB Stackup | The number of copper and fiberglass layers, the copper weights, solder mask type/color and silkscreen color.	 
PCB Fabrication File | Instructions on how to manufacture PCB files. Includes notes, UL data, clarifications, revisions, etc.	 
Assembly File (Assy) | Complete assembly instructions for a WIP or finished good item.	LED tube assembly instructions
Flash/Test Jig | A device used to optionally flash and then test a WIP or finished good item during manufacture.	 
Release | An official release of a design from engineering to production for manufacture.	 
Revision/Version	A | named, tracked change to a previous release.	 
Engineering Change Order	 | A document that details all of the changes between two revisions or versions.  It should reference the revision numbers and the changes made between each release.  The CMS is not allowed to make any changes to this package, including vendor or part substitutions, without first looping back to Codeshelf with an ECO.  
Engineering Change Request | An ECR is initiated by a CMS to suggest a change to a released device. The ECR initiates a process of discussion within the organization to determine the impact of a change and the best possible solution, potentially resulting in an ECO.	 
Release Package | A set of immutable documents that specify how to manufacture and test a particular version of a WIP or finished good item.	 
Git | A revision system for tracking document versions through time	 
Git commit | A specific document version committed to git for tracking and sharing.	 
Git tag | A named tag associated with any git commit.	 
Engineer	 | Design or production engineer	 
HWTE | Hardware Test Engineer	 
ProdMgr | Production Manager	 
Assembly File | This is a Word document with images that explains how to do any special assembly to and item.  
PCBAs | Most of our boards can get built entirely in the pick-and-place robots, but if there is some unusual hand-assembly step, etc. then we need to include an assembly file to let the 3rd party manufacturers know how to do these steps.
Mechanicals | Many of our housings are currently assembled in house, but for larger manufacturing runs we need to include an assembly file to let the 3rd party manufacturers know how to assemble the items. For mechanical releases this file may be a step-by-step instruction manual with images and text describing the assembly process.
Test File | This is a Word document file that explains how to flash (optional) and test a WIP or finished goods item during manufacture.  This document is critical because it indicates our quality acceptance criteria from the manufacturer before they ship the part.  Any flaws found after delivery are expensive to resolve and may cost us instead of the 3rd party.	 
DXF or EPS Output file | Autodesk format vector file - allows transmission of 2d build data to computer aided laser or water cutting.
Stereolithography File (STL) | STL files describe only the surface geometry of a three-dimensional object without any representation of color, texture or other common CAD model attributes. The STL format specifies both ASCII and binary representations. It is widely used for rapid prototyping and computer-aided manufacturing.
SLDPRT, STEP and/or IGES File | The native format used by Solidworks to represent 3D geometry. STEP and IGES are portable file formats that are commonly used to represent this same geometry for the purpose of transmitting 3D design intent to a vendor. STEP is a better format than IGES and is preferred by most vendors. Best practices include sending both SLDPRT and STEP (or IGES) files in case the vendor is using a different version of Solidworks—which is not backward-forward compatible.
PDF Drawing File | Essentially a Fabrication file for the mechanicals, containing all dimensions, tolerances, material requirements, etc. for the build.  This is the document a vendor will use to QA a built item.  It is also our assurance of recourse for any incorrect items we may receive. 
AMT | Automated Monkey Testing - The equivalent of TDD/CI for software - usually run in a fixed jig directly from firmware commits.	 
Prototype | Items made internally or externally that are not official production designs. These are not repeatable - they will never be re-made. Prototypes are internal engineering and test development only.	 
First Article | Goods made to test whether the entire release and manufacturing process is sound. These items should be considered completely production-ready. These releases include submitting a Purchase Order to an external vendor.
##Step 0: Kick-off Development Cycle

The kick-off is essential to inform everyone that the object is now in-flight for another development cycle.  The steps for kick-off are:

* Send an announce email to rnd@codeshelf.com
* Schedule Kick-off meeting
* Ensure that the Current and Planned Hardware Releases page in the ZeroDiff Process Home page is accurate for the device (and any related projects or sub-assemblies) at every step of this process document. 
* Print this page and make sure it follows the device through the development cycle.
* Always document while working, and always work with a pen.

For information about how an object is designed, reference In Action Product Design Process. 

For information regarding Testing Criteria, reference Basic Hardware Testing Criteria.

##Step 1: Create Design Artifacts 

The first step of the design and manufacture of mechanicals is to create all of the relevant design and production artifacts (files).

We are currently using Solidworks, Rhino, or Illustrator to design Mechanicals. Production documentation (drawings) is executed in Solidworks and output as PDF. Derivative CAD format files (those sent to vendors) are SLDPRT, STEP or EPS, depending on manufacturing process.

* Upload relevant Solidworks files to GrabCAD
* Be sure that the Solidworks files stay synced to GrabCAD in order to preserve change history

##Step 2: Create a Prototype (Designer, ProtoMgr)

To validate the design we produce an in-house prototype when possible.  This is a somewhat lightweight process and is not a tagged GitHub release, because there may be many of them.  

* If no prior Github repository exists for the project in question, file a JIRA Service Request with DevOps and request one with the appropriate project name.
* The engineer commits the CAD derivative files and PDF drawings to GitHub.
* If the assembly requires a BOM the engineer creates a prototype BOM and mails it to the prototype shop manager.

* Hand off the document package to the Prototype Shop.

    * The prototype shop manager schedules the build and coordinates with the production manager to acquire any missing BOM components.
    * The prototype shop converts the STEP or SLDPRT file into gcode using the HSMWorks plugin for Solidworks.
    * The prototype shop makes the parts.
    * The prototype shop assembles the housing and delivers it to the HWTE. In the absence of the HWTE, prototypes are delivered to the design engineer.

* When mechanical devices cannot be prototyped in-house:

    * Email production files to the ProdMgr along with requested turnaround time and quantities. 
    * ProdMgr will place RFQs and PO.
    * Prototypes will be made at a CMS.
    * Prototypes will be delivered to the HWTE. In the absence of the HWTE, prototypes are delivered to the design engineer.

##Step 3: Test the Prototype (HWTE, Designer)

* The HWTE and design engineer create a complete template object (built to the design intent) to test against.
* The HWTE and design engineer run all of the relevant tests set out in the design process to validate that the prototype is correct. Refer to the Basic Hardware Testing Criteria google doc. 
* The document should be printed and reviewed with a pen.
* If the HWTE approves the device for production then proceed to step 4, otherwise go back to step 1.

Hand off the document package to the Designer.

##Step 4: Create Release Candidate (RC) Artifacts (Designer)

For a mechanical/housing manufacturing run, the release package contains the following documents, as appropriate to the design and type of manufacturing process (in other words, not all designs will require each of the file types below).  The filenames derive from the base product ID, e.g. POSCON.XXXXXX  

 

CNC Manufacturing typical file sets

File | Example | Prod/Design Folder
-----|---------|-------------------
Drawing | POSCON.FACE.dxf | Production
Drawing | POSCON.FACE.pdf | Production
Vector File | POSCON.FACE.eps | Production (if lasercut)
Solidworks File | POSCON.FACE.SLDPRT | Production (if CNC)
STEP file | POSCON.FACE.STEP | Production (if CNC)


Lasercutting File typical file set:

File | Example | Prod/Design Folder
-----|---------|-------------------
Drawing	POSCON.FACE.pdf | Production
Vector File | POSCON.FACE.dxf | Production
Vector File | P2X142 POSCON.FACE.eps | Production (if lasercut)
README | POSCON.FACE.README.docx	 | Production (if lasercut):

Lasercut production file naming convention:

* SheetSize X Part yield per sheet PART.NAME.eps PRODUCTION

3D Printed File typical file set:

File | Example | Prod/Design Folder
-----|---------|-------------------
Drawing | POSCON.FACE.stl | Production
Drawing | POSCON.FACE.pdf | Production

Bill of Materials, Engineering Change Order file set:

File | Example | Prod/Design Folder
-----|---------|-------------------
BOM | POSCON.MECH.BOM.xlsx | Production
ECO | POSCON.FACE.eco.xlsx | Production

A typical release package would include some combination of:

* DXF, AI or EPS Vector file for laser cut parts
* Specific production files for current vendor (eg - Ponoko laser cut layout and ReadMe file)
* Stereolithography File (STL)
* SLDPRT, STEP and/or IGES File
* PDF Drawing File
* Engineering Change Order (ECO)
* Bill Of Materials (BOM)

Editing ECOs:

If changing the design of a previously released object, best practice is to update and commit the ECO as the object is being designed.

If working on a new production object, follow these steps:

* Open the New ECO Template (link here)
* The Commit Message field for a new production object should read "Initial Commit, v1.0" for a new project.
* Create a column in the ECO for each part being released by us to the right of the MISC Changes column in order to record future changes.
* Copy the Commit Message field in the ECO and paste it to the Commit Message field in Github before committing the ECO.

If working on a previously released production object, follow these steps:

* Record changes to each part in its individual column.
* If adding a new part, add a column and name it "Part_Name Changes".
* If deleting a part, note that in the part's column. Do not delete the column.
* Copy the change messages into the Commit Message field in the ECO. If the message is "none", ignore it.
* Copy the Commit Message field in the ECO and paste it to the Commit Message field in Github before committing the ECO.

* Print drawings
* Highlight changes
* Examine the changes for errors and make any needed corrections

These changes should also be reflected in the commit messages in Git.

If there is a design change to any part in the assembly, the entire assembly needs to increment, but other drawings in the same assembly that are separate and not changed do not need to increment. Any levels above the re-versioned assembly will also need to increment. 

Ensure that drawings made for production (other than laser cutting) comply with ANSI Standards:

* Limit dimensions should be used on all individually dimensioned toleranced parts.
* The Baseline dimensioning system should be used to locate toleranced surfaces to avoid an accumulation of tolerance.
* All dimensions should be given in decimals except drill sizes, fillets and rounds, and standard fasteners.
* Each dimension should be given clearly so that it can be interpreted in only one way
* Dimensions should not be duplicated or the same information given in two different ways and no dimensions should be given except those needed to produce or inspect the part.
* Dimensions should be given to finished surfaces or important center lines, in preference to rough surfaces, whenever possible.
* Dimensions should be so given that it will not be necessary for the machinist to calculate, scale, or assume any dimension.
* Dimensions should be given in the view where the shape is best shown.
* Dimensions should be placed in the views where the features dimensioned are shown true shape.
* Dimensions should not be placed on a view unless it eliminates long extension lines and makes the dimension clearer.
* Dimensions applying to two adjacent views should be placed between the views if possible.
* The longer dimensions should be placed outside all intermediate dimensions so that dimension lines will not cross extension lines. 
* Do not force workers to assume that a feature is centered. Provide a location dimension.
* Non-toleranced detail dimensions may be chained if necessary, or avoid a complete chain of detail dimensions by omitting one and providing an overall dimension. 
* Dimension lines should be spaced uniformly (approximately 3/8” apart).

For a complete ANSI checklist, refer to ANSI Dimensioning Guidelines v1.1.

##Step 5: Commit the Release Candidate Package to GitHub 

When working with RC files, best practices dictate that all files being created, edited and committed to GitHub be managed from the same place to keep the workflow consistent.

* Commit the above files to GitHub.
* When doing so, observe that no "lockfiles" are entered into the repository when a commit is made. (These are created when saving XLS files with LibreOffice and look like *.xls#. Right-click on these in Github and choose the "Ignore .XLS#" Be sure you're using the ignore command on the correct file.  
* Diff the files in Github in order to determine which files have been changed
* Examine changed files for errors
* Correct any errors found
* Tag the commit ID as a Release Candidate (RC).  E.g. V1.1-RC1
* Descriptions of changes that have been committed need to be included in the commit message.
* Copy commit messages between the RC release and the final production release into the ECO.
* The RC tag should increment (RC1, RC2) until the object is approved for production and released with the appropriate production version tag (E.g. V1.1).

##Step 6: Release Checklist 

* Download and print all files in the RC package from GitHub. 
* All files in the RC package must be checked against a printed Checklist: Mechanical Production Review v1.4. The document should be printed and reviewed with a pen.
* Any drawings to be released to CMs must be checked by the HTWE or in-house ANSI domain expert.
* If changes need to be made, go back to Step 4.

##Step 7: Build RC Articles (ProdMgr & HWTE)

Once a part releases as RC, we send the release package to the CMS for a request to quote for manufacture.   RC articles are not needed if the same outside CM has manufactured the prototype, and the same design has been approved for production with no changes. If either the design or manufacturing process changes from the approved prototype, RC articles are needed. 

* Email the ProdMgr to request an RC build along with requested turnaround time and quantity. 

Hand off the document package to the Production Manager.

* ProdMgr will place RFQs and PO.
* RC articles will be made at a CMS.

The CMS is not allowed to make any changes to this package without first looping back to Codeshelf to obtain an approved ECO.  If we receive an ECR from the CMS, we review it and decide if we will approve the change.  If we agree to approve the change, then we capture that change in the appropriate documents (BOM, ECO, etc.) and re-release the product with these changes, incrementing the tag. 

Hand off the document package to the Hardware Test Engineer when RC Articles are complete and delivered.

* RC articles will be delivered to the HWTE. In the absence of the HWTE, RC articles are delivered to the design engineer.
* When the device comes back from the CMS, it gets assembled by the prototype shop (if not already assembled by the outside CMS).
* ProdMgr checks whether CMS has made any modifications to the design. If so, the design needs to be revised and re-versioned. 

##Step 8: Test and Validate RC Articles (HWTE & Designer)

RC articles must be approved by the HWTE / designer in order to release for production. 

Hand off the document package to the Hardware Test Engineer.

* Print the Basic Hardware Testing Criteria and review with a pen.
* Run all of the relevant tests set out in the design process to validate that the article is correct.

If the HWTE approves the device for production then proceed to step 9, otherwise go back to step 4.
Step 9: Release Tag (Designer)

Hand off the document package to the designer/engineer.

When RC articles are proven good and approved for production:

* Tag the final commit with with the appropriate production version number. 

Github automatically notifies ProdMgr of the release. 

Hand off the document package to the Production Manager.

##Step 10: Release Announcement (ProdMgr)

    Issue a release announcement
    Update the Current and Planned Hardware Releases and Products in need of release documents. 

The item is then cleared for ongoing production.

##Step 11: Post Release Review (ProdMgr)

* Review the release process with the Engineer
* Change the release process document as needed
* Change the release checklists as needed
#Reminder: review with the following in mind
* Establish baseline workload for releases so they can be used to plan future work
* Identify highest friction areas that can be improved with substantial positive impact
* Make sure everyone is comfortable with the process and tools at hand
* Share tips with other teams to help each other improve their process.

##Review process through following lenses:

* Are there parts of the process that we can automate with a worthwhile outcome?
* Are there steps in the process that can be reworked, improved or eliminated (last resort)
* Are there things I personally need in order to proficiently complete the process or work that is better suited for someone else shared among teams?
* Is there anything missing from the process which would help ensure that our released products are correct and portable.

## Facts about GrabCAD:

* GrabCAD's position is that 2D drawings are dead, and they don't support them in any way other than making it possible to package PDFs along with 3D files when you get ready to submit them to a manufacturer via their Partner Spaces feature. There is no "annotation layer" in GrabCAD, nor do they make it possible to edit drawings in any of their tools. I have this in email from GrabCAD themselves.
* They do have a 3D view with annotations you can add, but as someone who's worked in a machine shop I sincerely question their usefulness (machine shops are likely to request PDFs for estimating purposes whether we use this tool or not). Very often prototyping machinists simply print and mark up the drawings. 
* The Partner Spaces could be useful, but all they do is provide a secure landing page with a download link for manufacturing partners. 
* They provide versioning, but it's not very flexible and doesn't work the way we do. It literally appends a version number to each save you upload to GrabCAD Workbench. It doesn't give us the option to use our own version number and revision scheme.
* Also, there is a provision for creating BOMs. Also not terribly flexible, nor does it have very many features that we need. What it does is kick out a CSV file with the names of the files you've uploaded, with data about those. It won't filter the filetype out of the name when it creates the CSV.  It would take me longer to hand-edit one of these (I did try!) into a workable * BOM than it would be to simply copy-paste or work from a pre-built template of our making.
* The things it does do well
    * Keeping track of historical versions of a file (every save is captured). However, we already do a form of this with Git. I haven't yet looked into what happens when you work out of the Git folder with Solidworks yet, but I suspect it'll work fine.
    * Allowing for visually checking differences between two versions of a 3D CAD file (Github doesn't do this - yet)
    * The things we were hoping to automate with it, BOMs and 2D drawings, are either not possible or more work than they're worth.

##Facts about Solidworks:

* There are a couple of tools that could help us work more efficiently, but they are unlikely to have a huge impact on the amount of time that we spend making drawings to the degree that it's worth slowing down the modeling process. Also, they have up-front setup times that we will need to be conscious of.
* It's possible to set up Solidworks to create BOMs that can be exported along with the drawings. This is probably a one-time endeavor, and will result in something that we can use over and over again. I'm not sure how long it would take to set up, but's unlikely to less than one day.
* It's possible to build Solidworks models in such a way as to start the process of adding annotations while one is working in the model, long before the drawings are started. Although I haven't tried this technique out yet, my suspicion is that working in this way will slow down the modeling process enough to mitigate any time savings we might get from it on the back end (i.e. annotating and preparing 2D drawings after the modeling is done). 

## Things that should go into current process:

* BOMs should be created and maintained from Solidworks (see risks/benefits below)
* Examine drawings in terms of what has changed, only test against what has changed STEP ADDED
* Bring all CAD files together into the same place (GrabCAD?) and practice better & more disciplined data hygiene STEP ADDED
* Use Github at the point of file creation to reduce shuttle time between machines STEP ADDED
* Upload files to GrabCAD STEP ADDED
* Diff files and folders STEP ADDED

## For discussion and potential adoption:

* MECH Release Checklist Google Form
    * Cost 
        * Minimal
    * Benefits
        * speed up and simplify the checklist process by gating out irrelevant steps in the process
    * Risks
        * "Read With A Pen" and "No Gating" are requirements of our current process. Should we re-examine this?
* BOM

    * Solidworks 
        * Steps to a BOM
                1. Do work in the model
                2. Make changes
                3. Changes to model are associative - no work necessary on BOM document
                4. Print along with drawings
    * Benefits 
        * Very little work need be done if proper setup 
        * Associative (BOM changes along with model)
    * Risks
        * CAD data used in production models must be 1:1 match to design intent (all parts must be the ones being specified)
        * Errors might be time-consuming to correct
    * Requirements
        * BOM template must be created
        * Project CAD data must be robust (part numbers correct, etc.)
        * In order to evaluate potential time savings, it might be necessary to create a prototype BOM 

* Solidworks Design Checker 
    * http://www.solidworks.com/sw/products/3d-cad/cad-standards-checking-and-drawing-comparison.htm
    * Cost
        * Upgrade to Solidworks Professional
        * Setup time for templates 
    * Time Savings
        * Reducing the drawing examination to a push-button process
    * Benefits
        * Simplifying the process of checking drawings dramatically
    * Risks
            It might take a while to figure out a good set of rules to build in to the Design Checker
            Upfront build might be expensive in terms of labor
            Only checks what you tell it to check

* What's it going to take to implement this? What's the cost? What's the benefit? What's the risk?
* How is the process testable against our baseline?
* How do these changes impact time to completion?

Documents and associated tools:

* Drawings
    * Created using Solidworks
* BOM
    * Created/updated in LibreOffice
* ECO
    * Created/updated in LibreOffice
* README files
    * Created/updated in LibreOffice

Mech release automation

Suggestions:
* for 2D Drawings
    * Set up templates in such a way as to minimize front-end work
* Model-Based Definition (3D PDF)
    * This is a method of CAD model data output that creates a package that is highly portable
    * http://www.solidworks.com/sw/products/technical-communication/solidworks-mbd.htm

Design Checker is an add-in for Solidworks Professional that allows for rule-based 'diff' operations on Solidworks drawings. Requires that an operator identifies the parts of the drawing that need to conform to standards (e.g. dimensions can not cross one another, can not be less than 3/8" from the model itself, etc.)

Currently, we would need a license upgrade to Professional to try this add-in. I might need to speak with a Solidworks Rep in order to determine if this is a good fit for our needs/worth the upgrade.

Additionally, Professional comes with a huge CAD Toolbox that has thousands of pre-built fasteners (which would speed things up - the operator would spend far less time searching McMaster for CAD files)

http://www.solidworks.com/sw/products/3d-cad/cad-standards-checking-and-drawing-comparison.htm

http://www.solidworks.com/sw/products/3d-cad/cad-library.htm
Mech Acceptance/Conformance Testing

 
Basic Hardware Testing Criteria

Document here:

https://docs.google.com/document/d/1ZpMAv2LG8mZiS7Jtf1E0wzCPsQbAyp7QIwp0flFzmjo/edit

##CAD standards

Solidworks models built for production purposes ought to fulfill the following criteria:

* 1:1 match with production object (This ensures that the BOM and other associated files are accurate)
* Design work is complete before Solidworks work is begun (dimensions are final, any formal studies are complete, etc.)
* Solidworks models are uploaded to GrabCAD
    * For change-tracking
    * To enable multiple users to work on the models concurrently/separately
The purpose of this document is to describe the process for a major revision or creating a new object. The top level party should hold on to this document and use it to organized the development of the object. During the process please write on the document improvements and alterations.

##Step 0: Kick-off Development Cycle

The kick-off is essential to inform everyone that the object is now in-flight for a development cycle.

* Send an announce email to development group that includes the PLM narrative of the object
* Schedule a kick-off meeting and invite whomever will be involved
* Create a top level Github repository if necessary
* Create a JIRA epic for the object “e.g. CHECON- New Display”
* Print this document
* Fill out the top portion
* Top level party should hold on to this document, check, and red pen as the project moves

##Step 1: Kick-off Meeting

The purpose of this step is to identify and start coordinating development of all sub and co components of this top level object.

* Go over design stories that this object will accomplish
* Define the sub-components and co-components of the top level object
    * Examples include:
        * PCB/A
        * Mechanicals
        * Firmware
    * For sub-components and co-components that will need development for this project
        * Assign top level parties to each component who will run those development cycles
* Go to hardware release page and update the relevant information for the top level device, relevant sub-components, and co-components <insert link>

##Step 2: Sketch Session

A sketch sessions should be conducted for mid to large-sized projects or problems where the requirements and solutions are still ambiguous. Sessions include the lead stakeholder (client), product owner, domain experts, designers and facilitators. The group works together on diverging ideas around the problem space, then pair the ideas down to ones that are actionable.

If the object owners decide a sketch session would be helpful have a sketch session. If the problem and/or solution is ambiguous then a sketch session is recommended - otherwise if the solution is unambiguous probably not needed.

##Step 3: Define a six digit alpha code

If necessary define a new six digit alpha code.
Part numbering scheme will probably change
copy from other document

##Step 4: Product Lifecycle Update / Testability

Every finished goods object we produce includes an informal product lifecycle narrative document. The goals of the object should be reflected in the testability of the object. For each goal we should have at least one test. Each time we start a design process loop on a new or existing object we need to update the PLM narrative with answers to questions similar to:

* What are the goals of this object?
* What is testable about the object?

##Step 7: Coordinate the sub-components and co-components development

This is the actual development of all the sub and co components of the top level device. This step could take a very long time depending on the scope of the project. During this time the top level party of this device is responsible for fostering communication between all the sub and co component top level parties so development is as seamless as possible.

* Have regular meetings with at least all of the sub-component and co-component top level parties to discuss the state of this top level object
* The top level party of this object should be made aware of any changes the sub and co components development path so they can be a single point of information (fostering communication)
* Make sure sub-components and co-components are working towards accomplishing the design stories

##Step 8: Verify all released Sub-components and Co-Components

The purpose of this step is to verify that the top level party of this object has all the parts they need to do a top level release.

* When all the sub-components and co-components have finished their development cycles have a meeting with all the sub-component top level parties and verify the finished top level object.
* Verify that all the sub and co components have have released all the parts required to do a top level object
* Did the related components actually follow the release process?
* Are they actually released? 
* Identify any additional parts that need to be created for top level object release
* Create a finished goods checklist
* Combine all the sub and co components

##Step 9: Create the Production Package

* Create the appropriate production package for this device. In general the production package should include at least a BOM and a ECO - it may also include testing information and packaging information.
* Make sure that the file names in the repository match the names in the BOM
* To the extent that is possible the editable versions of the documents should also be put in the Github repository. (e.g. The editable document used to produce a PDF should be also included)

##Step 10: Release Top Level

We need a barebones checklist - ask calla

* Add all finished files to Github repository for this object
* Release the object by tagging the commit
* Announce the release to oakland-staff@codeshelf.com 
* Update the release status page

##Step 11: Post Release Review (ProdMgr)

* Review the release process with the Engineer
* Change the release process document as needed
* Change the release checklists as needed
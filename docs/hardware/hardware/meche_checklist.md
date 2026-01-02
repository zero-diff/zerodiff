##MechE Release Checklist

##Check that all files are included in GitHub pre-release package:

* Does each part have its own folder named after it?
* Does each folder contain a drawing in PDF format, along with the appropriate derivative file (EPS, DXF, SLDPRT, STEP, etc.) format(s)? Refer to the tables in Step 4 of the 3. Mechanicals Development and Release Process if unsure.
* For lasercut parts, is there a README file containing the appropriate info on materials, thicknesses, sheet size, production file name, and any vendor specific information?

##Download the pre-release package from GitHub

##Print all current drawings from GitHub download
* If drawings have been revised, print previews. 
    * Limit dimensions should be used on all individually dimensioned toleranced parts.
    * Dimensions should not be duplicated or the same information given in two different ways and no dimensions should be given except those needed to produce or inspect the part.
    * Dimensions should be given between points or surfaces that have a functional relation to each other or that control the location of mating parts.
    * Dimensioning to hidden lines should be avoided whenever possible.
    * Dimensions applying to two adjacent views should be placed between the views if possible.
    * The longer dimensions should be placed outside all intermediate dimensions so that dimension lines will not cross extension lines.
* Do drawings effectively communicate essential tolerance features?
    * Dimensions
    * Materials
    * Tolerances
    * Review Version Numbers/Revision Numbers

##Review BOM Documents from GitHub download
* Check that the BOM has the following data:
    * Is the project name showing in the BOM's header?
    * Are all parts required to build the device represented?
    * Are parts quantities correct?
    * Are the dates current and correct?
    * Are the manufacturer's part numbers present and correct?
    * Are the Codeshelf part names present and correct?
    * Are feedstocks and their associated dimensions present and correct?
* Does the BOM contain all of the sourcing data needed to acquire the parts?
* Does the BOM contain feedstock and dimensions?
* Does each part have a name that follows the Codeshelf Part Number Scheme?

##Review ECO Documents from GitHub download

* Does the current version number’s row in the spreadsheet describe all changes to this version/revision?
* Does the ECO reflect all design changes noted since the previous release and those noted in the commit messages?

##Review README files (found in production files folders of lasercut parts) from GitHub download

* Is the required material listed?
* Is the thickness of the material called out?
* Is all vendor-specific information listed (eg stock sizes, file names, sheet size, part yield, etc.)

##Cross check Drawings/BOM/ECO from GitHub download

* Do all instances of version numbers/revision letters agree?
    * Drawings (found in drawing title block)
    * Do drawing / Part numbers and version numbers agree with the title blocks on the drawings?
* BOM (Product Number, also in Drawing/Part No. fields)
    * Does the tag on the BOM agree with the release ID row on the ECO?

##POST-RELEASE:

* Has the checklist been checked for necessary items/redundant items?
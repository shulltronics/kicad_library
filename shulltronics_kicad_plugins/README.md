BOM Generator for Shulltronics Inventory System
===============================================

The scripts in the folder are adaptations of the built-in KiCad BOM generator scripts,
with customizations for Shulltronics workflow.

I have a Google Sheet which contains all the parts I use in designs, organized by "SPN" or *shulltronics part number*. This spreadsheet contains, among other useful info, distributor information for up to two distributors (e.g. DigiKey and Mouser).

The `shulltronics_bom_gen.py` script will output a CSV file with matching components collated. The script outputs a Google Sheet formula to fetch the part by SPN from the inventory spreadsheet, and insert the first distributor name and PN for copy-pasting into a distributor's ordering system.

After running this script from the Schematic Editor, upload the CSV file to the spreadsheet, and the distributor information is there!

### Goals
* Consider converting the inventory spreadsheet to a sqlite3 database, and then incorporate that DB into the script instead of using special formulas with Google Sheets.
  * Could I still use a web editor to view and manage the database?
* Incorporate distributor APIs to include real-time availability of components, and produce two or more BOMs with parts available from various distributors.
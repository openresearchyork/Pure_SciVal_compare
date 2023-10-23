## Find potentially missing outputs from Pure

Create a folder that contains two csv files (your pure data and SciVal data to compare) and the ‘compare_pure_scival.Rscript’ file
1.	Pure data is an export from new reporting module: 
-	use any filters you want to create your custom pure file
-	file must be called ‘Pure.csv’ (case sensitive)
-	must contain fields ‘Title’, 'Journal title', ‘DOIs  Digital Object Identifiers ‘, (case sensitive, these are current default pure field names)
-	Fields with more than one output should be set to ‘wide preview’ using the pipe operator (|) to separate items
2.	SciVal data is an export of the publication list from the overview module:
-	Choose the University of York as your entity, or else a researcher group (e.g. ‘Faculty of Social Sciences’) from 2nd entity on left panel (A)
-	Switch on the home institution filter (B) (for researcher groups only)
-	Choose time frame (customised later) (C)
-	Choose ‘View list of Publications’ (D)

-	A list of publications opens; use the left panel to customise the time frame and publication types (exactly 2 filters e.g. Years and Type must be applied or empty lines have to be added to have header on row 20, data starting row 21)
-	choose ‘apply filter’ (bottom left)
-	choose ‘Export spreadsheet’ (top right)
-	Export must include fields ‘Scopus Source title’, ‘Title’, ‘DOI’ (case sensitive, these are current default SciVal field names, other fields possible, will be reflected in missing_from_pure.csv in the end)
-	Choose ‘Export CSV’ 
-	File will be sent via email, save as `SciVal.csv’ (case sensitive)
3.	Ensure R is installed (e.g. via software centre, choose R not RTools, Rstudio etc.)
4.	Double click ‘compare_pure_scival.Rscript’: Running the script for the first time, Windows asks what program you want to associate it with. Find Rscript.exe (Its likely under C:\Program Files\R\R-4.2.3\bin\x64)
5.	A csv called ‘missing_from_pure_scival.csv’ is created (you might have to run the script twice). It shows all the outputs that were in your SciVal.csv file but not in your Pure.csv. The algorithm matches based on DOI (1st step) or title-journal combination (2nd step, allowing for up to 5 characters difference).


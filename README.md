## Find potentially missing outputs from Pure

Create a folder that contains two csv files (your Pure data and SciVal data to compare) and the ‘compare_pure_scival.Rscript’ file (e.g. download as zip from github repo)
1.	Pure data is an export from new reporting module: 
-	use any filters you want to create your custom Pure file
-	file must be called ‘Pure.csv’ (case sensitive)
-	must contain fields ‘Title’, 'Journal title', ‘DOIs  Digital Object Identifiers ‘, (case sensitive, these are current default Pure field names)
-	Fields with more than one output (e.g. DOI) should be set to ‘wide preview’ using the pipe operator (|) to separate items
2.	SciVal data is an export of the publication list from the explore module:
-	Choose your entity (e.g. Faculty of Social Sciences) from 'Researchers & Groups' (A)
-	Switch on the home institution filter (B) (to filter out publications without UoY affiliation for research groups)
-	Choose time frame (customised later) (C)
-	Choose ‘View list of Publications’ (D)
![SciVal screenshot to show steps to download publication list](scival_download_data.png)
-	A list of publications opens; use the left panel to customise the time frame and publication types.
-	choose ‘apply filter’ (bottom left)
-	choose ‘Export spreadsheet’ (top right)
-	Export must include fields ‘Scopus Source title’, ‘Title’, ‘DOI’ (case sensitive, these are current default SciVal field names, other fields possible, will be reflected in missing_from_pure.csv in the end)
-	Choose ‘Export CSV’ 
-	File will be sent via email, save as `SciVal.csv’ (case sensitive). Empty lines might have to be added/removed so that header is on row 20, data starting row 21.
-	The repo includes an example SciVal.csv file.
3.	Ensure R is installed (e.g. via software centre, choose R not RTools, Rstudio etc.)
4.	Double click ‘compare_pure_scival.Rscript’: Running the script for the first time, Windows asks what program you want to associate it with. Find Rscript.exe (Its likely under C:\Program Files\R\R-4.2.3\bin\x64)
5.	A csv called ‘missing_from_pure_scival.csv’ is created. It shows all the outputs that were in your SciVal.csv file (located in same folder) but not in your Pure.csv (same folder). The algorithm matches based on DOI (1st step) or title-journal combination (2nd step, allowing for up to 5 characters difference). If running script for the first time you might have to run it twice to create output.


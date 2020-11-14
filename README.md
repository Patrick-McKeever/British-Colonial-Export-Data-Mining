# British African Colonial Export Dataset
Data mining project performed on pdfs from british colonial office's documents on african colonies from 1920-1938. Contains exports for each colony during that period. Barely warrants a `README`.

## Sources

If you particularly care about checking my results, you can find the sources [here](https://archive.org/search.php?query=creator%3A%22Great+Britain.+Colonial+Office%22&and%5B%5D=year%3A%221938%22&and%5B%5D=year%3A%221937%22&and%5B%5D=year%3A%221936%22&and%5B%5D=year%3A%221935%22&and%5B%5D=year%3A%221934%22&and%5B%5D=year%3A%221933%22&and%5B%5D=year%3A%221932%22&and%5B%5D=year%3A%221931%22&and%5B%5D=year%3A%221930%22&and%5B%5D=year%3A%221929%22&and%5B%5D=year%3A%221927%22&and%5B%5D=year%3A%221922%22&and%5B%5D=year%3A%221921%22&and%5B%5D=year%3A%221920%22&page=2). Only some of these were used in the script, since many were not parsable by a pdf reader.


## Data Mining Methodology

A thorough explanation of data-mining methodology is offered in the repo's '.ipynb' file. We isolated pdfs that were readable (e.g. did not have sideways export tables and did not store pages as images) and employed a slew of regexes to identify and parse tables enumerating exported commodities and their respective values. In doing so, we achieved a high level of accuracy, though several entries to the code-generated `.json` file warrant manual revision.

## Results

At the moment, we have generated a `.json` file containing the relevant export tables for each report, sorted by the name of the colony and the year of the report. Note that export tables span several years, so there may be overlap between multiple tables (discrepancies between tables, however, made me reticent to simplify into a `data[country][year] -> table` configuration). This is stored in the `codeGenerated.json` file.

At some point, I will upload a secondary file containing manually entered data from the PDFs and a handful of PDFs that poppler was unable to read. This will be another `json` file, though it does not exist at the moment. `codeGenerated.json`  will still remain to show the capabilities of the data-mining script.

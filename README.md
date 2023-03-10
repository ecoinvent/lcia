# LCIA
This repository contains important files from the ecoinvent LCIA method implementation procedure for ecoinvent versions ("3.9.1", for example). 
## Data formats and mapping procedure
Several data formats are specified in the "data formats" folder. ecoinvent takes methods as available (from the IPCC reports, for example) and first puts them in an [ecoinvent LCIA method input format](data_formats/ecoinvent_lcia_method_input_format.md). If method developers wish for a quick implementation of their method in ecoinvent, they should deliver their method(s) in this input format. The ecoinvent mapping algorithm then automatically maps elementary flows between ecoinvent and the method using the method input file and some additional files for manual data transformation (this is documented in more detail in the [LCIA Implementation report](https://ecoinvent.org/wp-content/uploads/2022/12/LCIA_implementation_3.9-and-3.9.1.pdf)). The result of this mapping are the "mapped" method files, which show ecoinvent elementary flows next to mapped method elementary flows and characterization factors in an [ecoinvent LCIA method mapped format](data_formats/ecoinvent_lcia_method_mapped_format.md). These mapped files are a work in progress and any review by the LCA community is highly appreciated.

NOTE: Some methods were available with ecoinvent elementary flow UUIDs and names and therefore needed no mapping. These are therefore not part of this repository.
## Metadata JSON file
The ```metadata.json``` file follows the [tabular-data-package](https://dataprotocols.org/tabular-data-package/) standard.
## Author and contact
This repository and the files in it were created by the ecoinvent Association. Feel free to reach out to sonderegger@ecoinvent.org.
## License
The data is licensed [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/)

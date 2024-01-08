# LCIA
This repository contains important files from the ecoinvent LCIA method implementation procedure for ecoinvent versions ("3.9.1", for example). 
## Data formats and mapping procedure
Several data formats are specified in the "data formats" folder. ecoinvent takes methods as available (from the IPCC reports, for example) and first puts them in an [ecoinvent LCIA method input format](data_formats/ecoinvent_lcia_method_input_format.md). If method developers wish for a quick implementation of their method in ecoinvent, they should deliver their method(s) in this input format. The ecoinvent mapping algorithm then automatically maps elementary flows between ecoinvent and the method using the method input file and some additional files for manual data transformation (this is documented in more detail in the [LCIA Implementation report](https://ecoinvent.org/wp-content/uploads/2022/12/LCIA_implementation_3.9-and-3.9.1.pdf)). The result of this mapping are the "mapped" method files, which show ecoinvent elementary flows next to mapped method elementary flows and characterization factors in an [ecoinvent LCIA method mapped format](data_formats/ecoinvent_lcia_method_mapped_format.md). These mapped files are a work in progress and any review by the LCA community is highly appreciated.

Automated mapping tries to map several fields and for v3.10 the types of successful mappings are indicated in the "flow_status" column:

|status		|meaning|
|---		|---|
|name		|mapped on name|
|stripped	|mapped on name with special characters stripped from it|
|synonym	|mappied on a synonym|
|syn_strip	|mapped on a synonms with special characters stripped from it|
|CAS		|mapped based on CAS number|
|formula	|mapped based on formula|

Manual mappings are indicated by the status "mapped: overwrite".

NOTE: Some methods were available with ecoinvent elementary flow UUIDs and names and therefore needed no mapping. These are therefore not part of this repository.

## Note for EF methods (including EN 15804)
The mappings to EF methods consider the [GLAD mapping](https://github.com/UNEP-Economy-Division/GLAD-ElementaryFlowResources/blob/master/Mapping/Output/Mapped_files/ecoinventEFv3.7-ILCD-EFv3.0.xlsx). While v3.9.1 implementations started from there, v3.10 implementations start not from the full list of elementary flows, but only from the list of characterized flows (the “lciamethods_CF” sheet of the [official Excel files](https://eplca.jrc.ec.europa.eu/permalink/EF3_1/EF-LCIAMethod_CF(EF-v3.1).xlsx)). This ensures that what is mapped also is characterized, but it also means that mappings can be different than in the GLAD mapping as the best matching flow is not available anymore.

## Metadata JSON file
The ```metadata.json``` file follows the [tabular-data-package](https://dataprotocols.org/tabular-data-package/) standard.
## Author and contact
This repository and the files in it were created by the ecoinvent Association. Feel free to reach out to sonderegger@ecoinvent.org.
## License
The data is licensed [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/)

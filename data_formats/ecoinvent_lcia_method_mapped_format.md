# ecoinvent LCIA method mapped format
The "mapped" method files are in the form of CSV data with the following fields. They show what method elementary flows were mapped to what ecoinvent elementary flows and can be used for reviewing the ecoinvent method implementation.
|Field	                  |Data type	  |Note   |
|-------------------------|-------------|-------|
|elementary_flow_id   		|string       |ecoinvent elementary flow UUID       |
|elementary_flow_name			|string       |ecoinvent elementary flow name       |	
|cas_number		            |string       |ecoinvent elementary flow CAS number       |		
|formula			            |string       |ecoinvent elementary flow formula       |	
|synonyms			            |string       |synonyms for ecoinvent elementary flow       |	
|compartment				      |string       |ecoinvent elementary flow compartment       |
|subcompartment				    |string       |ecoinvent elementary flow subcompartment        |
|unit_name		            |string       |ecoinvent elementary flow unit name      |		
|flow_status		          |string       |indicates whether the ecoinvent elementary flow was mapped or is an "ecoinvent orphan"|
|flow_used				        |boolean      |indicates whether the ecoinvent elementary flow is used in the ecoinvent database   |
|conversion_factor        |number       |the conversion with which the original characterization factor was multiplied       |
|method_elementary_flow_id|string       |method elementary flow UUID       |
|method_elementary_flow_name|string     |method elementary flow name       |
|method_compartment       |string       |method elementary flow compartment       |
|method_subcompartment    |string       |method elementary flow subcompartment       |
|method_unit              |string       |method elementary flow unit       |
|compartment_status       |string       |indicates whether the ecoinvent compartment/subcompartment was mapped or not       |
|{category 1}\|{indicator 1}|number     |characterization factors of method impact category and indicator |
|...                      |             |        | 
|{category n}\|{indicator n}|           |        | 


## Further explanations for EF methods
"flow status" and "compartment status": The column “flow_status” contains “mapped” if a match has been established between ecoinvent and the method for the flow, otherwise it says “ecoinvent orphan”. Sometimes a matching flow, but no matching compartment/subcompartment can be found. Therefore, some entries have a mapped flow, but not a mapped compartment/sub-compartment. A special case are the mappings to EF, which are based on the [GLAD mapping of elementary flow lists](https://github.com/UNEP-Economy-Division/GLAD-ElementaryFlowResources/). In the EF system, there are some elementary flows, which do not have a characterization factor. Since only those with a characterization factor are fully mapped, there are mapped flows including compartment but the compartment_status is empty. From an LCIA perspective, these mappings can be ignored.

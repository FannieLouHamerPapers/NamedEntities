# Fannie Lou Hamer Papers Project
by Jen Andrella & Brandon Locke

## Process
### Source Data
We used the natural language [Fannie Lou Hamer papers, 1966-1978 dataset](https://listings.lib.msu.edu/fannielouhamer/), focusing on the natural language files hand-transcribed by Joe Karisny, Olivia Ramos, and Kellen Saxton in [LEADR](leadr.msu.edu) with funding provided by the Michigan State University Department of History. Access to the data was provided by the MSU Library (Thomas Padilla, Devin Higgins, Megan Kudzia) via the Amistad Research Center and Gale CENGAGE's [Fannie Lou Hamer: Papers of a Civil Rights Activist, Political Activist, and Woman](https://www.gale.com/binaries/content/assets/gale-us-en/primary-sources/archives-unbound/primary-sources_-archives-unbound_fannie-lou-hamer_papers-of-a-civil-rights-activitist-political-activist-and-woman.pdf) collection. 

You can learn more about the contents and organization from [Amistad Research Center's finding aid](http://amistadresearchcenter.tulane.edu/archon/index.php?p=collections/controlcard&id=3).

### Data Structure
The named entity data was created by the Stanford Named Entity Recognizer (2018-02-27 release) and [NERtwork](https://github.com/brandontlocke/NERtwork).

| doc | doc\_title\_full | doc_description | doc\_imprint\_year | entity | type | count |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| name of txt file  | title of the document from *Archives Unbound* metadata | description of the document from *Archives Unbound* metadata | imprint year from *Archives Unbound* metadata | word or phrase recognized by Stanford NER  | type of entity (person, location, organization)  | number of times the entity & type occurred in the doc |


### Named Entity Refinement
Using OpenRefine, Andrella normalized variants of the same term (N.Y -> New York, NY -> New York) and removed information that wasn't helpful out of context (street addresses with no city, first names with no last name, etc). The entity counts were then updated using a script developed by [Devin Higgins](https://github.com/devinhiggins) to reflect merged rows. 

### Issues, Considerations, and Shortcomings
OCR quality is near 100% (hand transcribed), but errors do exist

StanfordNER's algorithmic entity tagging is far from perfect, and can miss or miscategorize entities.

Note: While a signfiicant amount of effort has gone into refining the named entity output, due to the scale of the project, many redudnancies and unclear entity names remain.

When people are referred to by just their first or last name, they may not be distinguished and counted with other occurrences.

Many decisions were made about merging or not merging entities that had similar names or meanings, and these edits were not cataloged.

## File Description
- `flh_ner_all.csv`  
  - All entity types, all occurrences.  
- `flh_ner_all_freq5.csv`  
  - All entity types, only rows with 'count' over five  
- `flh_ner_all_freq10.csv`  
  - All entity types, only rows with 'count' over ten  
- `flh_ner_location.csv`  
  - Location entity types only, all rows  
- `flh_ner_organization.csv`  
  - Organization entity types only, all rows  
- `flh_ner_person.csv`  
  - Person entity types only, all rows  

### Series Subsets
We are also providing subsets for each series, based on metadata provided to MSU Libraries by Gale CENGAGE. The series are as follows: Personal Papers, Mississippi Freedom Democratic Party (MFDP), Freedom Farms Corporation (FFC), Delta Ministry, Delta Opportunities Corporation (DOC), Mississippians United to Elect Negro Candidates, Other Organization Series I, Other Organization Series II, Other Organizational Series I, Other Organizational Series II, and Other Material. 

_Note: It's likely, though unclear, that 'Other Organization'/Other Organizational' Series are only separated due to an error in the metadata, but we have left them separate in accordance with the provided data._

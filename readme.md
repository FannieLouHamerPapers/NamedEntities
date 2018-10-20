# Fannie Lou Hamer Papers Project
Brandon Locke & Jen Andrella

## Process
### Source Data
We used the natural language [Fannie Lou Hamer papers, 1966-1978 dataset](https://listings.lib.msu.edu/fannielouhamer/) from MSU Libraries, focusing on the natural language files hand-transcribed by Joe Karisny, Olivia Ramos, and Kellen Saxton in [LEADR](leadr.msu.edu) with funding provided by the Michigan State University Department of History.

### Data Structure
The named entity data was created by the Stanford Named Entity Recognizer (2018-02-27 release) and [BatchNER](https://github.com/brandontlocke/batchner).

| doc | entity | type | count |
| ------------- | ------------- | ------------- | ------------- |
| name of txt file  | word or phrase recongized by Stanford NER  | type of entity (person, location, organization)  | number of times the entity & type occurred in the doc |


### Named Entity Refinement
Using OpenRefine, Andrella normalized variants of the same term (N.Y -> New York, NY -> New York) and removed information that wasn't helpful out of context (street addresses with no city, first names with no last name, etc). The entity counts were then updated using a script developed by [Devin Higgins](https://github.com/devinhiggins) to reflect merged rows.

### Issues, Considerations, and Shortcomings
OCR quality is near 100% (hand transcribed)

StanfordNER's algorithmic entity tagging is far from perfect, and can miss or miscategorize entities.

When people are referred to by just their first or last name, they may not be distinguished and counted with other occurrences.

A number of scholarly decisions were made about merging or not merging entities.

## Dataset Description
`flh_ner_all.csv`
All entity types, all occurrences.
`flh_ner_all_freq5.csv`
All entity types, only rows with 'count' over five
`flh_ner_location.csv`
Location entity types only, all rows
`flh_ner_organization.csv`
Organization entity types only, all rows
`flh_ner_person.csv`
Person entity types only, all rows

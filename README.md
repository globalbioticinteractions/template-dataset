[![GloBI Review by Elton](../../actions/workflows/review.yml/badge.svg)](../../actions/workflows/review.yml) [![DOI](https://zenodo.org/badge/26293374.svg)](https://zenodo.org/badge/latestdoi/26293374) [![GloBI](https://api.globalbioticinteractions.org/interaction.svg?accordingTo=globi:globalbioticinteractions/template-dataset)](https://globalbioticinteractions.org/?accordingTo=globi:globalbioticinteractions/template-dataset) 

This repository provides an example on how to make your interaction data available through Global Biotic Interactions (GloBI, http://globalbioticinteractions.org).

If you have comments or questions please [open an issue](https://github.com/globalbioticinteractions/globalbioticinteractions/issues/new).

## Share Your Interaction Data
If you want to make your own data discoverable through GloBI:

1. Create a repository from this template dataset by visiting  https://github.com/globalbioticinteractions/template-dataset/generate or clicking the "use this template" button.
2. Edit your ```README.md``` and describe your data in a human readable form.
3. Ensure that your README.md contains a reference to ```http://globalbioticinteractions.org```.
4. Edit your ```globi.json``` to provide a machine readable description of your dataset (e.g. citation, license, version, files, format).
5. Edit the name of your repository and description to make it easy for others to understand what your data is about.

After you do this, the data will be available through GloBI within a day or so.

If you don't feel comfortable being indexed by GloBI because your data isn't ready yet, or no longer up-to-date, you can set ```"deprecated": true``` in ```globi.json``` to unlist (or opt-out) the dataset to be indexed and made visible via https://globalbioticinteractions.org (see https://github.com/globalbioticinteractions/globalbioticinteractions/issues/372). 

## Enable Automated Dataset Preservation/Publication
Preserving and publishing your valuable data is now easier than ever. 

To enable automated preserving and publishing your data:

1. login/register with [zenodo](https://zenodo.org)
2. enable automated preservation and publication of your dataset using instructions at  https://zenodo.org/account/settings/github/ or https://guides.github.com/activities/citable-code/
3. edit your zenodo publication and add it to zenodo's [Global Biotic Interactions community](https://zenodo.org/communities/globalbioticinteractions/). 

For a completed example, see the publication of this template repository at [![DOI](https://zenodo.org/badge/26293374.svg)](https://zenodo.org/badge/latestdoi/26293374).

## Enable Integration Testing
Integration testing, also known as "GloBI review by Elton", is currently supported through GitHub actions, and is enable automatically. 

If you'd like to learn more about GitHub actions in general, please see https://github.com/features/actions . For reviewing the review script, please see [./.github/workflows/review.yml](./.github/workflows/review.yml). You'll find that most of the review logic is captured in [https://github.com/globalbioticinteractions/globinizer/blob/master/check-dataset.sh](https://github.com/globalbioticinteractions/globinizer/blob/master/check-dataset.sh) . 

For any remaining questions about the review process, please [open an issue](https://github.com/globalbioticinteractions/globalbioticinteractions/issues) or contact folks [by email](https://globalbioticinteractions.org/contribute). There's plenty of ways to review species interaction datasets, and your questions, ideas and suggestions help to find more intuitive ways to do so. Thank in advance for sharing your ideas!  

By the way, on a successful review, you should see a badget similar to the one below: 


Now, whenever you make a change to data repository that is incompatible with GloBI, you receive a notification. If you'd like, you can include a build badge on your own html pages to see the health of your data. Here's an example of a "green" review badge:  

![image](https://github.com/globalbioticinteractions/template-dataset/assets/1084872/776dbabc-c99e-4d8c-86bb-2dc07bc2a155)

However, if you see a "red" review badge like:

![image](https://github.com/globalbioticinteractions/template-dataset/assets/1084872/155cfe55-94a4-4dfa-84e1-d8ea68657161)

please check your review logs, or ask questions if you'd like to have some guidance on how to access or interpret the review reports. 

## Data Format and Dictionary
The file [interactions.tsv](./interactions.tsv) is a suggestion on how to encode your interaction data using a tab separated file format (tsv) in combination with columns described below. This provides an example on how to capture your data in a human and machine friendly way and keep it relatively doable to update the file using a basic text editor. Other formats are supported, just let us know about the syntax, and we'll make it work.

Each term has two columns: one for an id and another for a label. The former is to make the term machine readable, the latter to make is easy to read for humans. With both id and name present possible typos or other transcription errors can be detected with a (somewhat) straightforward algorithm.


term | example | description | 
--- | --- | ---
argumentTypeId | https://en.wiktionary.org/wiki/refute | a URI that points to a definition of how this records support, refutes or provides other kind of arguments in the context of described interaction. When unspecified, the argument is assumed to be in support of the documented interaction claim.
 argumentTypeName | refute | a human readable name that qualifies whether the record is in support or refutes of a particular interaction
sourceOccurrenceId | 83742b5e-f0fd-4c12-a0af-c97191ea7722 | globally unique id to reference the individual originating organism, specimen. Inspired by http://rs.tdwg.org/dwc/terms/#occurrenceID .
 sourceTaxonId | EOL:328583 | taxon classification id of originating organism in some taxon name authority
 sourceTaxonName | Enhydra lutris | scientific name of taxon classification of originating organism 
 sourceTaxonKingdomName | Animalia | name of kingdom of taxon classification of originating organism 
 sourceTaxonPhylumName | Chordata | name of phylum of taxon classification of originating organism 
 sourceTaxonClassName | Gastropoda | name of class of taxon classification of originating organism 
 sourceTaxonOrderName | Carnivora | name of order of taxon classification of originating organism 
 sourceTaxonFamilyName | Mustelidae | name of family of taxon classification of originating organism 
 sourceTaxonGenusName | Enhydra | name of genus of taxon classification of originating organism 
 sourceTaxonSpecificEpithetName | lutris | name of specific epithet of taxon classification of originating organism 
 sourceTaxonSubspecificEpithetName | nereis | name of subspecific epithet of taxon classification of originating organism 
 sourceBodyPartId | http://purl.obolibrary.org/obo/UBERON_0000178 | identifier of description of source body part is interacted with
 sourceBodyPartName | blood | human readable description of source body part (e.g., "blood", "fruit")
 sourceLifeStageId | http://purl.obolibrary.org/obo/UBERON_0007023 | identifier of description of source life stage
 sourceLifeStageName | adult | human readable description of source life stage (e.g., "adult", "juvenile")
 sourcePhysiologicalStateId | http://purl.obolibrary.org/obo/PATO_0001422 | identifier of description of source physiological state
 sourcePhysiologicalStateName | dead | human readable description of source physiological state (e.g., "dead", "rotten")
 interactionTypeId | RO:0002470 | id of interaction as described by the [OBO Relations Ontology](https://github.com/oborel/obo-relations)
 interactionTypeName | eats | human readable description of interactions
 targetOccurrenceId | a5ee64b5-081b-4fff-8adc-2b0c74b1f40a | globally unique id to reference the individual target organism, specimen. Inspired by http://rs.tdwg.org/dwc/terms/#occurrenceID .
 targetTaxonId |  EOL:1971 | taxon classification id of target organism. 
 targetTaxonName | Echinoidea | scientific name of taxon classification of target organism of interaction
 targetTaxonKingdomName | Animalia | name of kingdom of taxon classification of target organism of interaction
 targetTaxonPhylumName | Chordata | name of phylum of taxon classification of target organism of interaction
 targetTaxonClassName | Gastropoda | name of class of taxon classification of target organism of interaction
 targetTaxonOrderName | Carnivora | name of order of taxon classification of target organism of interaction
 targetTaxonFamilyName | Mustelidae | name of family of taxon classification of target organism of interaction
 targetTaxonGenusName | Enhydra | name of genus of taxon classification of target organism of interaction
 targetTaxonSpecificEpithetName | lutris | name of specific epithet of taxon classification of target organism of interaction
 targetTaxonSubSpecificEpithetName | nereis | name of subspecific epithet of taxon classification of target organism of interaction
 targetBodyPartId | http://purl.obolibrary.org/obo/UBERON_0000178 | identifier of description of target body part is interacted with
 targetBodyPartName | Echinoidea | human readable description of target body part (e.g., "blood")
 targetLifeStageId | http://purl.obolibrary.org/obo/UBERON_0007023 | identifier of description of target life stage
 targetLifeStageName | adult | human readable description of target life stage (e.g., "adult", "juvenile")
 targetPhysiologicalStateId | http://purl.obolibrary.org/obo/PATO_0001422 | identifier of description of target's phyiological state
 targetPhysiologicalStateName | dead | human readable description of target's physiological state (e.g., "dead", "rotten")
 habitatId | ENVO:00000067 or http://purl.obolibrary.org/obo/ENVO_00000067 | reference to a habitat classification like Environmental Ontology (http://environmentontology.org/), Coastal and Marine Classification Standards (CMECS, https://iocm.noaa.gov/standards/cmecs-home.html).
 habitatName | cave | human readable description of habitat
 localityId | GEONAMES:5391961 | reference to geo classification like geonames.org, gazetteer or other.
 localityName | San Francisco Bay, California, USA | human readable description of locale
 decimalLatitude | -41.0983423 | latitude of geographic center of interaction observation location http://rs.tdwg.org/dwc/terms/index.htm#decimalLatitude
 decimalLongitude | -121.1761111 | longtide of geographic center of interaction observation location http://rs.tdwg.org/dwc/terms/index.htm#decimalLongitude
 depth | 123.2 | distance below surface in meters
 altitude | 4553.2 | height above sea level in meters
 observationDateTime | 2014-11-18T06:37:04Z | [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) formatted date time string 
 referenceDoi | doi:10.1126/science.200.4340.403 | Digital Object Id (DOI, http://doi.org) is commonly used to give papers, datasets or other digital object a permanent id
 referenceUrl | http://eol.org/data_objects/13596344 | some resolvable url that point to information related to species interaction record
 referenceCitation| C. A. Simenstad, J. A. Estes, K. W. Kenyon, Aleuts, sea otters, and alternate stable-state communities, Science 200:403-411, from p. 404 (1978). | human readable reference 

## Term Id Sources
Rather than only supplying a name for a taxon and/or locality, a reference to some established taxonomy and/or geo database is preferred. Commonly used taxon id sources include, but are not limited to [GBIF](http://gbif.org), [EOL](http://eol.org),  [ITIS](http://itis.gov) and [WoRMS](http://marinespecies.org). Geo database or vocabularies include [geonames](http://geonames.org) and [Gazetteer Ontology](http://bioportal.bioontology.org/ontologies/GAZ).
 
## Interaction Id Cheatsheet

For more terms, please see [OBO Relations Ontology](https://github.com/oborel/obo-relations).
 
interactionTypeId | interactionTypeName 
--- | ---
[RO:0002470](http://www.ontobee.org/browser/rdf.php?o=RO&iri=http://purl.obolibrary.org/obo/RO_0002470) | eats
[RO:0002444](http://www.ontobee.org/browser/rdf.php?o=RO&iri=http://purl.obolibrary.org/obo/RO_0002444) | parasite of
[RO:0002455](http://www.ontobee.org/browser/rdf.php?o=RO&iri=http://purl.obolibrary.org/obo/RO_0002455) | pollinates
[RO:0002556](http://www.ontobee.org/browser/rdf.php?o=RO&iri=http://purl.obolibrary.org/obo/RO_0002556) | pathogen of

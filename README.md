This repository provides an example on how to make your interaction data available through Global Biotic Interactions (GloBI, http://globalbioticinteractions.org).

If you have comments or questions please [open an issue](https://github.com/jhpoelen/eol-globi-data/issues/new).

## Share Your Interaction Data
If you want to share your own data through GloBI:

1. Fork this repository.
2. Edit your ```README.rd``` to describe your data in a human readable form.
3. Ensure that your README.rd contains a reference to ```http://globalbioticinteractions.org```.
4. Edit your ```globi.json``` to provide a machine readable description of your dataset (e.g. citation, license, version, files, format).
5. Edit the name of your repository and description to make it easy for others to understand what your data is about.

After you do this, the data will be available through GloBI within a day or so.

## Data Format and Dictionary
The file [interactions.tsv](./interactions.tsv) is a suggestion on how to encode your interaction data using a tab separated file format (tsv) in combination with columns described below. This provides an example on how to capture your data in a human and machine friendly way and keep it relatively doable to update the file using a basic text editor. Other formats are supported, just let us know about the syntax, and we'll make it work.

Each term has two columns: one for an id and another for a label. The former is to make the term machine readable, the latter to make is easy to read for humans. With both id and name present possible typos or other transcription errors can be detected with a (somewhat) straightforward algorithm.


term | example | description | 
--- | --- | ---
 sourceTaxonId | EOL:328583 | taxon classification id of originating organism in some taxon name authority
 sourceTaxonName | Enhydra lutris  | scientific name of taxon classification of originating organism 
 interactionTypeId | RO:0002470 | id of interaction as described by the [OBO Relations Ontology](https://code.google.com/p/obo-relations/)
 interactionTypeName | eats | human readable description of interactions
 targetTaxonId |  EOL:1971 | taxon classification id of originating organisms 
 targetTaxonName | Echinoidea | scientific name of taxon classification of target organism of interaction
 localityId | GEONAMES:5391961 | reference to geo classification like geonames.org, gazetteer or other.
 localityName | San Francisco Bay, California, USA | human readable description of locale
 decimalLatitude | -41.0983423 | latitude of geographic center of interaction observation location http://rs.tdwg.org/dwc/terms/index.htm#decimalLatitude
 decimalLongitude | -121.1761111 | longtide of geographic center of interaction observation location http://rs.tdwg.org/dwc/terms/index.htm#decimalLongitude
 observationDateTime | 2014-11-18T06:37:04Z | [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) formatted date time string 
 referenceDoi | doi:10.1126/science.200.4340.403 | Digital Object Id (DOI, http://doi.org) is commonly used to give papers, datasets or other digital object a permanent id
 referenceCitation| C. A. Simenstad, J. A. Estes, K. W. Kenyon, Aleuts, sea otters, and alternate stable-state communities, Science 200:403-411, from p. 404 (1978). | human readable reference 

## Term Id Sources
Rather than only supplying a name for a taxon and/or locality, a reference to some established taxonomy and/or geo database is preferred. Commonly used taxon id sources include, but are not limited to [GBIF](http://gbif.org), [EOL](http://eol.org),  [ITIS](http://itis.gov) and [WoRMS](http://marinespecies.org). Geo database or vocabularies include [geonames](http://geonames.org) and [Gazetteer Ontology](http://bioportal.bioontology.org/ontologies/GAZ).
 
## Interaction Id Cheatsheet

For more terms, please see [OBO Relations Ontology](https://code.google.com/p/obo-relations/).
 
interactionTypeId | interactionTypeName 
--- | ---
[RO:0002470](http://www.ontobee.org/browser/rdf.php?o=RO&iri=http://purl.obolibrary.org/obo/RO_0002470) | eats
[RO:0002444](http://www.ontobee.org/browser/rdf.php?o=RO&iri=http://purl.obolibrary.org/obo/RO_0002444) | parasite of
[RO:0002455](http://www.ontobee.org/browser/rdf.php?o=RO&iri=http://purl.obolibrary.org/obo/RO_0002455) | pollinates
[RO:0002556](http://www.ontobee.org/browser/rdf.php?o=RO&iri=http://purl.obolibrary.org/obo/RO_0002556) | pathogen of

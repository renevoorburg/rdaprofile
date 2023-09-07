# rdaprofile

A SPARQL query intented to create an ontology based on, and derived from, the [official RDA definitions](http://www.rdaregistry.info).

It helps to:

* publish a specific subset of RDA elements,
* described only in selected languages,
* using IRI's that are human readable,
* add aditionial elements if desired.

Thus it intends to make it easier to work with RDA in a specific context.


## why

This query was developed to formalize the creation of the RDF definition of the [RDANL application profile](https://netwerk-digitaal-erfgoed.github.io/rdanl/).

## example

As provided, the SPARQL will run on any triple store that has loaded [official RDA definitions](http://www.rdaregistry.info).  

In this form (specifically mind the n*amed graph* that is used in the **WHERE** clause), it will run on [https://data.digitopia.nl/yasgui/](https://data.digitopia.nl/yasgui/) .

### PS...
The default Virtuoso SPARQL query editor (tested in Virtuoso 07.29.3237) will not runs the query since it is too long for a GET and should be POSTed, which it doesn't. It will run in the query editor available in the Virtuoso Conductor, or indeed in [Yasgui](https://data.digitopia.nl/yasgui/).


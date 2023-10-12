# rdaprofile

`rdanl.sparql` is a SPARQL query intented to create an ontology based on, and derived from, the [official RDA definitions](http://www.rdaregistry.info).

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

#back & forth
The scripts `rda_to_rdanl.sparql `and `rdanl_to_rda.sparql `are provided to convert official RDA RDF to rdanl or the other way around. Make sure the rdanl-definitions, as generated by `rdanl.sparql`, are loaded in named graph  `<http://data.bibliotheken.nl/rdanl#> `.

### ps..
The default Virtuoso SPARQL query editor (tested in Virtuoso 07.29.3237) will not runs the query since it is too long for a GET and should be POSTed, which it doesn't. It will run in the query editor available in the Virtuoso Conductor, or indeed in [Yasgui](https://data.digitopia.nl/yasgui/).

### pps...
I experienced problems feeding `rdanl.sparql` to `isql` because it interprets the **$**-sign as a macro specifier. This can be circumvented by replacing it with `\u0024` like:

 	CONCAT(?rdanl_base, REPLACE(REPLACE(STR(?lexical_alias), "^.*/([^/]*)\u0024", "\u00241"), CONCAT("\\", ?lexical_suffix, "\u0024"), "", "i"))
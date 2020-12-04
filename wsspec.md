API Spec
========

User: kuckuck
Group: nest
Artifact: eier
Version: 2020.10.10

# General note
`GET` should show HTML as default, but return linked data with the specific content-types.
The query can be either answered via 
1. SPARQL DESCRIBE or CONSTRUCT from the store.
2. redirecting to the file in git

In the examples only "text/turtle" is shown, but we should implement most of the formats provided by virtuoso. Note that it might make sense to return the JSON-LD from GIT as it is rendered more nicely than the generic jsonld from virtuoso. 

# Context
See [context.jsonld].
Issues:
* 


# Group
File used [group.jsonld]

```
curl -X PUT http://databus.dbpedia.org/kuckuck/nest --data-urlencode "@group.jsonld"
curl -X DELETE http://databus.dbpedia.org/kuckuck/nest
curl -X GET -H "Accept: text/turtle" http://databus.dbpedia.org/kuckuck/nest

```
Behaviour: 
* PUT: create or overwrite, save in git as jsonld, upload to SPARQL store under graph "http://databus.dbpedia.org/kuckuck/nest"
* DELETE: remove file from git, delete graph
* GET: query
```
CONSTRUCT {
# same as in where
}{

?s dataid:group <http://databus.dbpedia.org/kuckuck/nest> .
?s ?p ?o .
?s dcat:distribution ?dist.
?dist ?p2 ?o2 .
}
```
TODO:
* check construct query, if it selects all data, can be done with SHACL. 

# Version

File use [version.jsonld]
```
curl -X PUT http://databus.dbpedia.org/kuckuck/nest/eier/2020.10.10 --data-urlencode "@version.jsonld"
curl -X DELETE http://databus.dbpedia.org/kuckuck/nest/eier/2020.10.10
curl -X GET -H "Accept: text/turtle" http://databus.dbpedia.org/kuckuck/nest/eier/2020.10.10

```

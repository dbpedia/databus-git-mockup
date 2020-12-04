API Spec

User: kuckuck
Group: nest
Artifact: eier
Version: 2020.10.10

# General note
`GET` should show HTML as default, but return linked data with other content-types.
The query can be answered via SPARQL DESCRIBE or CONSTRUCT from the store.
Only "text/turtle" is shown here, but we should implement most of the formats provided by virtuoso


# Group

```
curl -X PUT http://databus.dbpedia.org/kuckuck/nest --data-urlencode "@group.jsonld"
curl -X DELETE http://databus.dbpedia.org/kuckuck/nest
curl -X GET -H "Accept: text/turtle" http://databus.dbpedia.org/kuckuck/nest

```
Behaviour: 
* PUT: create or overwrite, save in git as jsonld, upload to SPARQL store under graph "http://databus.dbpedia.org/kuckuck/nest"
* GET: see above
* DELETE: obvious

# Version

```


```

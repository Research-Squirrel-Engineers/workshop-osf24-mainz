# nomisma.org Mints

```
SELECT ?item ?lat ?lon WHERE {
 ?item a <http://nomisma.org/ontology#Mint>.
 ?item geo:location ?loc .
 ?loc wgs84_pos:lat ?lat .
 ?loc wgs84_pos:long ?lon .
}
```

# Roman Open Data

```
PREFIX : <http://www.semanticweb.org/ontologies/2015/1/EPNet-ONTOP_Ontology#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dcterms: <http://purl.org/dc/terms/>
SELECT ?item ?amphtype ?lat ?lon (count(?item) as ?count)
WHERE {
 ?amph a :Amphora .
 ?amph :hasAmphoraType ?amphtypeo .
 ?amphtypeo dcterms:title ?amphtype .
 FILTER (?amphtype = "Gauloise 4")
 ?amph :carries ?inscription .
 ?amph :hasFindingPlace ?findplace .
 ?findplace :fallsWithin ?mun . 
 ?mun a :Municipality .
 ?mun dcterms:title ?item . 
 ?mun :hasLatitude ?lat . 
 ?mun :hasLongitude ?lon .  
} ORDER BY ?item DESC(?count)
```
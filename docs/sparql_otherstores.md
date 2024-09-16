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

# Hadrians Wall Forts

via [Research-Squirrel-Engineers / HadriansWall](https://github.com/Research-Squirrel-Engineers/HadriansWall)

```
SELECT ?item ?geo ?name ?latin_name ?typeLabel WHERE {
 ?item rdf:type hw:Fort .
 ?item geosparql:hasGeometry ?item_geom .
 ?item_geom geosparql:asWKT ?geo . 
 ?item hw:name ?name .
 ?item hw:latin_name ?latin_name .
 ?item a ?type .
 ?type rdfs:label ?typeLabel.
 FILTER NOT EXISTS { 
  FILTER (?typeLabel = "Fort"@en)
 }
}
```

# Ogham Stones with MAQI

```
SELECT DISTINCT ?item ?geo ?itemLabel ?stone ?stoneLabel ?readingLabel WHERE {
 ?stone oghamonto:shows ogham:OW6.
 ?stone rdfs:label ?stoneLabel .
 ?stone a oghamonto:OghamStone_CIIC .
 ?stone oghamonto:disclosedAt ?item .
 ?item rdfs:label ?itemLabel .
 ?item <http://www.opengis.net/ont/geosparql#hasGeometry> ?geom_obj .
 ?geom_obj geosparql:asWKT ?geo .
 ?stone oghamonto:carries ?inscription .
 ?inscription oghamonto:identifiedAs ?reading .
 ?reading rdfs:label ?readingLabel .
 FILTER(regex(?readingLabel, "MAQI"))
}
```
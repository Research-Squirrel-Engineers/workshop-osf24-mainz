# Hospitals in Germany as Map

via [https://w.wiki/BBHb](https://w.wiki/BBHb)

```
#Hospitals in Germany
#defaultView:Map
SELECT DISTINCT ?item ?itemLabel ?geo WHERE {
 ?item (wdt:P31/(wdt:P279*)) wd:Q16917.
 ?item wdt:P17 wd:Q183.
 ?item wdt:P625 ?geo.
 SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
}
```

# International Airports in Germany as Map

via [https://w.wiki/BBHg](https://w.wiki/BBHg)

```
#International Airports in Germany
#defaultView:Map
SELECT DISTINCT * WHERE {
 ?item (wdt:P31/(wdt:P279*)) wd:Q644371.
 ?item wdt:P17 wd:Q183.
 ?item wdt:P625 ?geo.
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
}
```

# Museums in Germany as Map

via [https://w.wiki/BBHi](https://w.wiki/BBHi)

```
#Museums in Germany
#defaultView:Map
SELECT DISTINCT ?item ?itemLabel ?geo ?museumtype ?museumtypeLabel WHERE {
 ?item (wdt:P31/(wdt:P279*)) wd:Q33506.
 ?item wdt:P17 wd:Q183.
 ?item wdt:P625 ?geo.
 ?item wdt:P31 ?museumtype.
 SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
}
```

# Museums in Germany by type as BubbleChart

via [https://w.wiki/BBHk](https://w.wiki/BBHk)

```
#Museums in Germany (by type)
#defaultView:BubbleChart
SELECT DISTINCT ?museumtype ?museumtypeLabel (COUNT(?item) AS ?count) WHERE {
 ?item (wdt:P31/(wdt:P279*)) wd:Q33506.
 ?item wdt:P17 wd:Q183.
 ?item wdt:P625 ?geo.
 ?item wdt:P31 ?museumtype.
 SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
}
GROUP BY ?museumtype ?museumtypeLabel
ORDER BY DESC(?count)
```

# Museums (type: natural history) in Germany as Map

via [https://w.wiki/BBHo](https://w.wiki/BBHo)

```
#Museums (type: natural history) in Germany
#defaultView:Map
SELECT DISTINCT ?item ?itemLabel ?geo ?museumtype ?museumtypeLabel WHERE {
 ?item (wdt:P31/(wdt:P279*)) wd:Q33506.
 ?item wdt:P17 wd:Q183.
 ?item wdt:P625 ?geo.
 ?item wdt:P31 wd:Q1970365.
 SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
}
```
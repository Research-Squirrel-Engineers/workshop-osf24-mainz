# Hospitals in Germany as Map

```#Hospitals in Germany
#defaultView:Map
SELECT DISTINCT ?item ?itemLabel ?geo WHERE {
  ?item (wdt:P31/(wdt:P279*)) wd:Q16917;
    wdt:P17 wd:Q183;
    wdt:P625 ?geo.
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
}```
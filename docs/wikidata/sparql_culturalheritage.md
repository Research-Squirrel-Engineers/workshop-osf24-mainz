# Archaeological Sites in Rhineland-Palatinate (Germany) as Map with images

via [https://w.wiki/BBHy](https://w.wiki/BBHy)

```
#Archaeological Sites in Rhineland-Palatinate (Germany)
#defaultView:Map
SELECT DISTINCT ?item ?itemLabel ?geo ?img WHERE {
 ?item (wdt:P31/(wdt:P279*)) wd:Q839954.
 ?item wdt:P17 wd:Q183.
 ?item wdt:P131 wd:Q1200.
 ?item wdt:P625 ?geo.
 OPTIONAL { ?item wdt:P18 ?img }
 SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```
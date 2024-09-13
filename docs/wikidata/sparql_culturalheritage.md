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

# Caves with prehistoric art as Map with images

via [https://w.wiki/BBJP](https://w.wiki/BBJP)

```
#Caves with prehistoric art
#defaultView:Map
SELECT DISTINCT ?item ?itemLabel ?geo ?img WHERE {
 ?item (wdt:P31/(wdt:P279*)) wd:Q11269813.
 ?item wdt:P625 ?geo.
 OPTIONAL { ?item wdt:P18 ?img }
 SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```

# castrum (Roman fortification) as Map with images

via [https://w.wiki/BBJf](https://w.wiki/BBJf)

```
#castrum (Roman fortification)
#defaultView:Map
SELECT DISTINCT ?item ?itemLabel ?geo ?img WHERE {
 ?item (wdt:P31/(wdt:P279*)) wd:Q88205.
 ?item wdt:P625 ?geo.
 OPTIONAL { ?item wdt:P18 ?img }
 SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```

# Limes castrum (Roman fortification) as Map with images

via [https://w.wiki/BBJd](https://w.wiki/BBJd)

```
#Limes castrum (Roman fortification)
#defaultView:Map
SELECT DISTINCT ?item ?itemLabel ?geo ?img WHERE {
 ?item (wdt:P31/(wdt:P279*)) wd:Q88205.
 ?item wdt:P625 ?geo.
 OPTIONAL { ?item wdt:P18 ?img }
 ?item wdt:P361 ?part.
 ?part wdt:P31 wd:Q146924.
 SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```

# Samian Ware Discovery Sites as Map and SamianURI

via [https://w.wiki/BBVn](https://w.wiki/BBVn)

```
#Samian Ware Discovery Sites
#defaultView:Map
SELECT ?item ?samianURI ?itemLabel ?geo
WHERE 
{
  ?item wdt:P31 wd:Q102202066.
  ?item wdt:P361 wd:Q90412636.
  ?item wdt:P625 ?geo.
  ?item wdt:P2888 ?samianURI.
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```

# Samian Ware Production Centres as Map and SamianURI

via [https://w.wiki/BBVr](https://w.wiki/BBVr)

```
#Samian Ware Production Centres
#defaultView:Map
SELECT ?item ?samianURI ?itemLabel ?geo
WHERE 
{
  ?item wdt:P31 wd:Q102202026.
  ?item wdt:P361 wd:Q90412636.
  ?item wdt:P625 ?geo.
  ?item wdt:P2888 ?samianURI.
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```

# Samian Ware Kiln Regions as Map and SamianURI

via [https://w.wiki/BBVt](https://w.wiki/BBVt)

```
SELECT ?item ?samianURI ?itemLabel ?geo
#Samian Ware Production Centres
#defaultView:Map
SELECT ?item ?samianURI ?itemLabel ?geo
WHERE 
{
  ?item wdt:P31 wd:Q102202026.
  ?item wdt:P361 wd:Q90412636.
  ?item wdt:P625 ?geo.
  ?item wdt:P2888 ?samianURI.
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```

# Ogham Sites as Map

via [https://w.wiki/BBWL](https://w.wiki/BBWL)

```
# Ogham Sites (Q72617071)
#defaultView:Map{"hide":["?geo"]}
SELECT ?item ?itemLabel ?geo ?layerLabel ?layer WHERE {
  ?item wdt:P31 wd:Q72617071;
    wdt:P361 wd:Q100530634;
    wdt:P625 ?geo;
    wdt:P131 ?layer.
  ?layer wdt:P31 wd:Q202156.
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```

# Ogham Sites from the Dingle Peninsula (Barony Corkaguiny) as Map

via [https://w.wiki/BBWL](https://w.wiki/BBWL)

```
# Ogham Sites in Barony Corkaguiny (Q59419929)
#defaultView:Map{"hide":["?geo"]}
SELECT ?item ?itemLabel ?geo WHERE {
  ?item wdt:P31 wd:Q72617071;
    wdt:P361 wd:Q100530634;
    wdt:P625 ?geo;
    wdt:P131 wd:Q59419929.
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```

# Ogham Sites (Dingle Peninsula) w/ inscription containing "MAQI" as Map

via [https://w.wiki/BBWr](https://w.wiki/BBWr)

```
# Ogham Sites (Dingle Peninsula) w/ inscription containing "MAQI"
#defaultView:Map{"hide":["?geo"]}
SELECT ?geo ?stone ?stoneLabel ?itemLabel ?inscription WHERE {
  ?item wdt:P31 wd:Q72617071;
    wdt:P361 wd:Q100530634;
    wdt:P625 ?geo;
    wdt:P131 wd:Q59419929.
  ?stone wdt:P189 ?item.
  ?stone wdt:P31 wd:Q106602599.
  ?stone wdt:P1684 ?inscription.
  FILTER(contains(str(?inscription),'MAQI' ))
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```

# Holy Wells as Map with images

via [https://w.wiki/BBJm](https://w.wiki/BBJm)

```
#Holy Wells
#defaultView:Map
SELECT DISTINCT ?item ?itemLabel ?img ?geo ?osm WHERE {
  ?item wdt:P31 wd:Q1371047, wd:Q126443332.
  OPTIONAL { ?item wdt:P18 ?img. }
  OPTIONAL { ?item wdt:P625 ?geo. }
  OPTIONAL { ?item wdt:P11693 ?osm. }
  SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }
}
```

# Holy Wells by etymology as BubbleChart

via [https://w.wiki/BBJt](https://w.wiki/BBJt)

```
#title:holy wells by etymology
#illustrates bubblechart view, count
#defaultView:BubbleChart
SELECT ?etymology ?etymologyLabel (COUNT(?HW) AS ?count)
WHERE
{
  ?HW wdt:P31 wd:Q126443332.
  ?HW wdt:P131 wd:Q180231.
  ?HW wdt:P138 ?etymology.
  SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }
}
GROUP BY ?etymology ?etymologyLabel
ORDER BY DESC(?count)
```
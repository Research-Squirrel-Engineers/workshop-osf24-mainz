# Masonic lodges by systems and obediences as Map

via [https://tinyurl.com/2fzngjj8](https://tinyurl.com/2fzngjj8)

```
#masonic lodges
#defaultView:Map
SELECT DISTINCT ?lodge ?lodgeLabel ?layerLabel ?coord
WHERE  {
 VALUES ?system { wd:Q99758 wd:Q141414 wd:Q11283}
  ?layer wdt:P2/wdt:P3*  ?system .
  ?lodge wdt:P2 wd:Q11211 ;
         wdt:P83 ?place.
 ?lodge wdt:P430 | wdt:P521 | wdt:P319 | wdt:P336   ?layer . 
  ?place wdt:P48 ?coord .
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". } # le label viendra de préférence dans votre langue, et autrement en anglais
}
```

# Houses in Leipzig 

via [https://tinyurl.com/27yld7yu](https://tinyurl.com/27yld7yu)

```
#defaultView:Map
#defaultView:Map{"hide":["?point", "?line"]}
SELECT 
  ?address (STRDT(?polygonn, geo:wktLiteral) AS ?polygon)
WHERE{
    ?subject wdt:P153 ?address .
    ?subject wdt:P1035 ?polygonn .
}
```

# Poets in Paris as Map

via [https://tinyurl.com/yb2nejbm](https://tinyurl.com/yb2nejbm)

```
#defaultView:Map
#poets
SELECT ?poet ?poetLabel ?addressLabel ?coord
WHERE 
{
  ?poet wdt:P2 wd:Q7;
        wdt:P165/wdt:P3* wd:Q38831;
        wdt:P208 ?address.
  ?address wdt:P47 wd:Q10441;
           wdt:P48 ?coord.
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". } # le label viendra de préférence dans votre langue, et autrement en anglais
}
```

# Adherents of French Prophets and religious affiliations as BubbleChart

via [https://tinyurl.com/2a65xc3g](https://tinyurl.com/2a65xc3g)

```
#defaultView:BubbleChart
SELECT ?ReligionLabel (count(distinct(?A)) as ?count) WHERE {
  
  SELECT ?A ?ALabel ?ADescription ?family_nameLabel ?Entry ?BnF_ID ?Date_of_birth ?Religion ?ReligionLabel WHERE {
    SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }
    ?A wdt:P300 wd:Q255080.
    OPTIONAL { ?A (p:P300/pq:P49) ?Entry. }
    OPTIONAL { ?A wdt:P247 ?family_name. }
    ?A wdt:P172 ?Religion. 
}
  
  } group by ?ReligionLabel
```

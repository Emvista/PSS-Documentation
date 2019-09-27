Highlighter
==

<img src="../images/ic_pss_highlighter.png" alt="drawing" width="80"/>

La reconnaissance des entités nommées vise à identifier dans un texte les noms de personnes, les noms de lieux, les noms d'organisations, les noms de produits, etc.

Query
--
* Method : GET
* Header : Content-Type: application/json
* Basic Auth : BASIC_AUTH
* Poa-Token : TOKEN
* Server : https://api-pss.prevyo.com/pss/api/highlight
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Marie enverra la facture demain à Pierre de chez Emvista."
}
```

OUTPUT
--
HTTP Status : 200

Body :

```JSON
{
  "originalText": "Marie enverra la facture demain à Pierre de chez Emvista.",
  "globalTypesCount": {
    "Time": 1,
    "Organization": 1,
    "Person": 1,
    "Location": 1
  },
  "entities": [
    {
      "entityType": "nerd:Person>Individual>FirstName",
      "wiki": "",
      "value": "Marie",
      "indexEnd": 4,
      "indexStart": 0,
      "depiction": ""
    },
    {
      "entityType": "nerd:Time",
      "wiki": "",
      "value": "demain",
      "indexEnd": 30,
      "indexStart": 25,
      "depiction": ""
    },
    {
      "entityType": "nerd:Location",
      "wiki": "http://dbpedia.org/resource/Pierre",
      "value": "Pierre",
      "indexEnd": 39,
      "indexStart": 34,
      "depiction": ""
    },
    {
      "entityType": "nerd:Organization",
      "wiki": "",
      "value": "Emvista",
      "indexEnd": 55,
      "indexStart": 49,
      "depiction": ""
    }
  ],
  "entityTypes": [
    "Organization",
    "Time",
    "Person",
    "Location"
  ]
}
```

TEST
--

`curl -X GET "https://api-pss.prevyo.com/pss/api/highlight" -H "accept: application/json" -H "Basic Auth: YYYYYY" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Marie enverra la facture demain à Pierre de chez Emvista."}` 

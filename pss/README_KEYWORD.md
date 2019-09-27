Keywords
==

<img src="../images/ic_pss_mot_cle.png" alt="drawing" width="80"/>

L'extraction de mots clés fournit une liste ordonnée des termes les plus pertinents dans le contexte donné.

Query
--
* Method : GET
* Header : Content-Type: application/json
* Basic Auth : BASIC_AUTH
* Poa-Token : TOKEN
* Server : https://api-pss.prevyo.com/pss/api/keywords
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Emvista est une société créée à Montpellier en février 2018. Emvista développe des briques logicielles pour comprendre le langage naturel."
}
```

OUTPUT
--
HTTP Status : 200

Body :

```JSON
{
  "original": "Emvista est une société créée à Montpellier en février 2018. Emvista développe des briques logicielles pour comprendre le langage naturel. ",
  "keywords": {
    "3-gram": {
      "NC": {}
    },
    "10-gram": {
      "NC": {}
    },
    "5-gram": {
      "NC": {}
    },
    "9-gram": {
      "NC": {}
    },
    "4-gram": {
      "NC": {}
    },
    "8-gram": {
      "NC": {}
    },
    "7-gram": {
      "NC": {}
    },
    "1-gram": {
      "NC": {}
    },
    "2-gram": {
      "NC": {
        "briques logicielles": 1,
        "langage naturel": 1,
        "une société": 1
      }
    },
    "6-gram": {
      "NC": {}
    }
  },
  "max-gram": 10
}
```

TEST
--

`curl -X GET "https://api-pss.prevyo.com/pss/api/keyword" -H "accept: application/json" -H "Basic Auth: YYYYYY" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Emvista est une société créée à Montpellier en février 2018. Emvista développe des briques logicielles pour comprendre le langage naturel."}` 


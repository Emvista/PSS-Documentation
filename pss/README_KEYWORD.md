Keywords
==

<img src="../images/ic_pss_mot_cle.png" alt="drawing" width="80"/>

L'extraction de mots clés fournit une liste ordonnée des termes les plus pertinents dans le contexte donné.

Query
--
* Method : POST
* Header : Content-Type: application/json
* Poa-Token : TOKEN
* Server : https://pss-api.prevyo.com/pss/api/keywords
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
  "original": "Emvista est une société créée à Montpellier en février 2018. Emvista développe des briques logicielles pour comprendre le langage naturel.",
  "keywords": {
    "NC": [
      {
        "occurence": 1,
        "ShortForm": "société",
        "word": "société"
      },
      {
        "occurence": 1,
        "ShortForm": "briques logicielles",
        "word": "brique"
      },
      {
        "occurence": 1,
        "ShortForm": "langage naturel",
        "word": "langage"
      }
    ],
    "V": [
      {
        "occurence": 1,
        "ShortForm": "développer",
        "word": "développer"
      }
    ],
    "ADJ": [
      {
        "occurence": 1,
        "ShortForm": "briques logicielles",
        "word": "logiciel"
      },
      {
        "occurence": 1,
        "ShortForm": "langage naturel",
        "word": "naturel"
      }
    ],
    "NPP": [
      {
        "occurence": 2,
        "ShortForm": "Emvista",
        "word": "Emvista"
      },
      {
        "occurence": 1,
        "ShortForm": "Montpellier",
        "word": "Montpellier"
      }
    ]
  },
  "max-gram": 10
}
```

TEST
--

`curl -X GET "https://pss-api.prevyo.com/pss/api/keyword" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Emvista est une société créée à Montpellier en février 2018. Emvista développe des briques logicielles pour comprendre le langage naturel."}` 


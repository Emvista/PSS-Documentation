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
        "word": "société",
        "fullword": [
          "société"
        ]
      },
      {
        "occurence": 1,
        "word": "brique",
        "fullword": [
          "briques logicielles"
        ]
      },
      {
        "occurence": 1,
        "word": "langage",
        "fullword": [
          "langage naturel"
        ]
      }
    ],
    "V": [
      {
        "occurence": 1,
        "word": "développer",
        "fullword": [
          "développer"
        ]
      }
    ],
    "ADJ": [
      {
        "occurence": 1,
        "word": "logiciel",
        "fullword": [
          "briques logicielles"
        ]
      },
      {
        "occurence": 1,
        "word": "naturel",
        "fullword": [
          "langage naturel"
        ]
      }
    ],
    "NPP": [
      {
        "occurence": 2,
        "word": "Emvista",
        "fullword": [
          "Emvista"
        ]
      },
      {
        "occurence": 1,
        "word": "Montpellier",
        "fullword": [
          "Montpellier"
        ]
      }
    ]
  },
  "max-gram": 10
}
```

TEST
--

`curl -X GET "https://pss-api.prevyo.com/pss/api/keyword" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Emvista est une société créée à Montpellier en février 2018. Emvista développe des briques logicielles pour comprendre le langage naturel."}` 


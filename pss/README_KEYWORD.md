Keywords
==

<img src="../images/ic_pss_mot_cle.png" alt="drawing" width="80"/>

L'extraction de mots clés fournit une liste ordonnée des termes les plus pertinents dans le contexte donné.

Query
--
* Method : POST
* Header : Content-Type: application/json
* Poa-Token : TOKEN
* Server : https://api-pss.prevyo.com/pss/api/keyword
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
        "word": "briques logicielles",
        "iteration": 1
      },
      {
        "word": "langage naturel",
        "iteration": 1
      },
      {
        "word": "briques logicielles",
        "une société": 1
      }
    ],
    "V": [
      {
        "word": "développer",
        "iteration": 1
      },
      {
        "word": "comprendre",
        "iteration": 1
      }
    ],
    "ADJ": [],
    "NPP": [
      {
        "word": "Montpellier",
        "iteration": 1
      },
      {
        "word": "Emvista",
        "iteration": 1
      }
    ]
  },
  "max-gram": 10
}
```

TEST
--

`curl -X GET "https://api-pss.prevyo.com/pss/api/keyword" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Emvista est une société créée à Montpellier en février 2018. Emvista développe des briques logicielles pour comprendre le langage naturel."}` 


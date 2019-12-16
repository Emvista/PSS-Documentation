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
    "text": "Emvista est une société créée à Montpellier en février 2018. Emvista développe des briques logicielles pour comprendre le langage naturel. À partir de ces briques technologiques, Emvista propose Prevyo, un assistant virtuel intelligent de gestion d’e-mails."
}
```

OUTPUT
--
HTTP Status : 200

Body :

```JSON
{
  "original": "Emvista est une société créée à Montpellier en février 2018. Emvista développe des briques logicielles pour comprendre le langage naturel. À partir de ces briques technologiques, Emvista propose Prevyo, un assistant virtuel intelligent de gestion d'e-mails.",
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
        "occurence": 2,
        "word": "brique",
        "fullword": [
          "briques technologiques",
          "briques logicielles"
        ]
      },
      {
        "occurence": 1,
        "word": "langage",
        "fullword": [
          "langage naturel"
        ]
      },
      {
        "occurence": 1,
        "word": "assistant",
        "fullword": [
          "assistant virtuel intelligent de gestion d' e-mails"
        ]
      },
      {
        "occurence": 1,
        "word": "gestion",
        "fullword": [
          "assistant virtuel intelligent de gestion d' e-mails"
        ]
      },
      {
        "occurence": 1,
        "word": "e-mail",
        "fullword": [
          "assistant virtuel intelligent de gestion d' e-mails"
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
      },
      {
        "occurence": 1,
        "word": "proposer",
        "fullword": [
          "proposer"
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
      },
      {
        "occurence": 1,
        "word": "technologique",
        "fullword": [
          "briques technologiques"
        ]
      },
      {
        "occurence": 1,
        "word": "virtuel",
        "fullword": [
          "assistant virtuel intelligent de gestion d' e-mails"
        ]
      },
      {
        "occurence": 1,
        "word": "intelligent",
        "fullword": [
          "assistant virtuel intelligent de gestion d' e-mails"
        ]
      }
    ],
    "NPP": [
      {
        "occurence": 3,
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
      },
      {
        "occurence": 1,
        "word": "Prevyo",
        "fullword": [
          "Prevyo"
        ]
      }
    ]
  },
  "max-gram": 10
}
```

TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/keyword" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Emvista est une société créée à Montpellier en février 2018. Emvista développe des briques logicielles pour comprendre le langage naturel."}` 


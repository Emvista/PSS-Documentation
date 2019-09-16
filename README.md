Prevyo Semantic Services
==

Briques logicielles pour comprendre le langage naturel.

1. [Anonymiser](#anonymiser)
2. [Sentiment](#sentiment)
3. [Concepts](#concepts)
4. [Keywords](#keywords)
5. [NLU](#nlu)
6. [Résumés](#resumes)
7. [Actions](#actions)
8. [Highlighter](#highlighter)

Glodal
==

Query
--
* Method : GET
* Header : Content-Type: application/json
* Basic Auth : BASIC_AUTH
* Poa-Token : TOKEN



Anonymiser
==

L'anonymiseur a pour objectif d'anonymiser toutes les entités que l'utilisateur souhaite (noms de personnes, de marques, d'organisations, lieux, dates, etc.).

Query
--
* Server : https://api-pss.prevyo.com/pss/api/anonymise
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Bonjour Jean, peux tu appeler demain midi, la société Emvista pour parler à Paul ?"
}
```

OUTPUT
--
HTTP Status : 200

Body :

```JSON
{
    "entities": [
        {
            "idSentence": 0,
            "anonymizedValue": "[PERS]",
            "id": 1,
            "type": "nerd:Person>Individual>FirstName",
            "initialValue": ""
        },
        {
            "idSentence": 0,
            "anonymizedValue": "[TIME]",
            "id": 6,
            "type": "nerd:Time",
            "initialValue": ""
        },
        {
            "idSentence": 0,
            "anonymizedValue": "[ORGA]",
            "id": 11,
            "type": "nerd:Organization",
            "initialValue": ""
        },
        {
            "idSentence": 0,
            "anonymizedValue": "[PERS]",
            "id": 15,
            "type": "nerd:Person>Individual>FirstName",
            "initialValue": ""
        }
    ],
    "anonymised": "Bonjour [PERS] , peux tu appeler [TIME] , la société [ORGA] pour parler à [PERS] ?"
}
```

TEST
--

`curl -X GET "https://api-pss.prevyo.com/pss/api/anonymise" -H "accept: application/json" -H "Basic Auth: YYYYYY" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Bonjour Jean, peux tu appeler demain midi, la société Emvista pour parler à Paul."}` 

Sentiment
==

L'analyse d’opinion (<i>opinion mining</i> ou <i>sentiment analysis</i>) consiste à analyser un texte pour identifier les sentiments ainsi que les émotions qui y sont exprimés.

Query
--
* Server : https://api-pss.prevyo.com/pss/api/sentiments
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Paul n'aime pas la très bonne pomme de Marie."
}
```

OUTPUT
--
HTTP Status : 200

Body :

```JSON
{
    "sentiments": [
        {
            "predicate": {
                "lemma": "ne pas aimer(bonne pomme)"
            },
            "emotions": [
                "sadness"
            ],
            "idAction": -1,
            "opinion": "negative",
            "agents": [
                {
                    "form": "Paul"
                }
            ]
        }
    ],
    "text": "Paul n'aime pas la très bonne pomme de Marie."
}
```

TEST
--

`curl -X GET "https://api-pss.prevyo.com/pss/api/sentiments" -H "accept: application/json" -H "Basic Auth: YYYYYY" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Paul n'aime pas la très bonne pomme de Marie."}` 

Concepts
==

L'identification des concepts permet de faire émerger des concepts qui n'apparaissent pas explicitement dans le texte à analyser.

Query
--
* Server : https://api-pss.prevyo.com/pss/api/concepts
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Bonjour Jean, peux tu appeler demain midi, la société Emvista pour parler à Paul ?"
}
```

OUTPUT
--
HTTP Status : 200

Body :

```JSON
{
    "entities": [
        {
            "idSentence": 0,
            "anonymizedValue": "[PERS]",
            "id": 1,
            "type": "nerd:Person>Individual>FirstName",
            "initialValue": ""
        },
        {
            "idSentence": 0,
            "anonymizedValue": "[TIME]",
            "id": 6,
            "type": "nerd:Time",
            "initialValue": ""
        },
        {
            "idSentence": 0,
            "anonymizedValue": "[ORGA]",
            "id": 11,
            "type": "nerd:Organization",
            "initialValue": ""
        },
        {
            "idSentence": 0,
            "anonymizedValue": "[PERS]",
            "id": 15,
            "type": "nerd:Person>Individual>FirstName",
            "initialValue": ""
        }
    ],
    "anonymised": "Bonjour [PERS] , peux tu appeler [TIME] , la société [ORGA] pour parler à [PERS] ?"
}
```

TEST
--

`curl -X GET "https://api-pss.prevyo.com/pss/api/concepts" -H "accept: application/json" -H "Basic Auth: YYYYYY" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Bonjour Jean, peux tu appeler demain midi, la société Emvista pour parler à Paul."}` 

Keywords
==
L'extraction de mots clés fournit une liste ordonnée des termes les plus pertinents dans le contexte donné.

NLU
==
Le NLU (<i>Natural Language Understanding</i>) sert à extraire les intentions exprimées dans une phrase.

Résumés
==
Le générateur de résumés crée une synthèse du texte, dont le niveau d'abstraction est paramétrable.

Actions
==
La reconnaissance d'actions vise à extraire les actions que doit faire une personne, pour quand, comment, pour qui, etc.

Highlighter
==
La reconnaissance des entités nommées vise à identifier dans un texte les noms de personnes, les noms de lieux, les noms d'organisations, les noms de produits, etc.

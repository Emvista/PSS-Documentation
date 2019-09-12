Prevyo Semantic Services
==

Briques logicielles pour comprendre le langage naturel.

1. [Anonymiser](#anonymiser)
2. [Sentiment](#sentiment)
3. [Concepts](#concepts)
4. [Keywords](#keywords)
5. [NLU](#nlu)

Anonymiser
==

Query
--
* Server : https://api-pss.prevyo.com/pss/api/anonymise
* Method : POST
* Header : Content-Type: application/json
* Basic Auth : BASIC_AUTH
* Poa-Token : TOKEN
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

`curl -X POST "https://api-pss.prevyo.com/pss/api/anonymise" -H "accept: application/json" -H "Basic Auth: YYYYYY" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Bonjour Jean, peux tu appeler demain midi, la société Emvista pour parler à Paul."}` 

Sentiment
==

Query
--
* Server : https://api-pss.prevyo.com/pss/api/sentiments
* Method : POST
* Header : Content-Type: application/json
* Basic Auth : BASIC_AUTH
* Poa-Token : TOKEN
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

`curl -X POST "https://api-pss.prevyo.com/pss/api/sentiments" -H "accept: application/json" -H "Basic Auth: YYYYYY" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Paul n'aime pas la très bonne pomme de Marie."}` 

Concepts
==

Keywords
==

NLU
==
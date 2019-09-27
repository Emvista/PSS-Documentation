Sentiment
==

<img src="images/ic_pss_sentiment.png" alt="drawing" width="80"/>

L'analyse d’opinion (<i>opinion mining</i> ou <i>sentiment analysis</i>) consiste à analyser un texte pour identifier les sentiments ainsi que les émotions qui y sont exprimés.

Query
--
* Method : GET
* Header : Content-Type: application/json
* Basic Auth : BASIC_AUTH
* Poa-Token : TOKEN
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


NLU
==
<img src="images/ic_pss_nlu.png" alt="drawing" width="80"/>

Le NLU (<i>Natural Language Understanding</i>) sert à extraire les intentions exprimées dans une phrase.

Query
--
* Method : GET
* Header : Content-Type: application/json
* Basic Auth : BASIC_AUTH
* Poa-Token : TOKEN
* Server : https://api-pss.prevyo.com/pss/api/nlu
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Peux-tu envoyer une facture à Marie ?"
}
```

OUTPUT
--
HTTP Status : 200

Body :

```JSON
{
  "intents": [
    {
      "responseType": "giveBooleanAnswer",
      "initialText": "Peux-tu envoyer une facture à Marie ?",
      "negative": false,
      "reaction": {
        "questions": [
          "getMoreInformation()",
          "getRewording()"
        ],
        "behaviour": []
      },
      "entities": {
        "Agent": "Receiver of the text",
        "Theme": "une facture",
        "Recipient": "Marie"
      },
      "toSolve": true,
      "properNouns": [
        "Marie"
      ],
      "commonNouns": [
        "facture"
      ],
      "verbs": [
        "envoyer"
      ],
      "intent": "give-13.1"
    },
    {
      "responseType": "giveBooleanAnswer",
      "initialText": "Peux-tu envoyer une facture à Marie ?",
      "negative": false,
      "reaction": {
        "questions": [
          "getMoreInformation()",
          "getRewording()"
        ],
        "behaviour": []
      },
      "entities": {
        "Theme": "une facture",
        "Recipient": "Marie",
        "Source": "Receiver of the text"
      },
      "toSolve": false,
      "intent": "obtain-13.5.2"
    }
  ],
  "responseType": "giveBooleanAnswer",
  "vulgar": false,
  "message": "Peux-tu envoyer une facture à Marie ?"
}
```

TEST
--

`curl -X GET "https://api-pss.prevyo.com/pss/api/nlu" -H "accept: application/json" -H "Basic Auth: YYYYYY" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Peux-tu envoyer une facture à Marie ?"}` 


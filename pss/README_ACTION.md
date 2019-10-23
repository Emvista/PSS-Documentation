Action
==

<img src="../images/ic_pss_action.png" alt="drawing" width="80"/>

La reconnaissance d'actions vise à extraire les actions que doit faire une personne, pour quand, comment, pour qui, etc.

Query
--
* Method : POST
* Header : Content-Type: application/json
* Poa-Token : TOKEN
* Server : https://api-pss.prevyo.com/pss/api/action
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Marie enverra la facture demain."
}
```

OUTPUT
--
HTTP Status : 200

Body :

```JSON
{
  "text": "Marie enverra la facture demain.",
  "actions": [
    {
      "predicate": {
        "verbalForm": "active",
        "idSentence": 0,
        "idToken": 1,
        "lemma": "envoyer"
      },
      "negative": false,
      "idSentence": 0,
      "roleMap": {
        "Agent": {
          "idSentence": 0,
          "entityType": "nerd:Person>Individual>FirstName",
          "idToken": 0,
          "lemma": "Marie",
          "wsd": "Thing>Concrete>Animate>Livingbeing>Person",
          "corefLemma": ""
        },
        "TimeExact": {
          "idSentence": 0,
          "entityType": "nerd:Time",
          "idToken": 4,
          "lemma": "2019-09-28",
          "wsd": "Thing>Abstract>Inanimate>Time",
          "corefLemma": ""
        },
        "Theme": {
          "idSentence": 0,
          "entityType": "",
          "idToken": 3,
          "lemma": "la facture",
          "wsd": "Thing>Abstract>Inanimate>Archive | Thing>Concrete>Inanimate>Archive",
          "corefLemma": ""
        }
      },
      "idAction": 1,
      "frame": "give-13.1"
    }
  ]
}
```

TEST
--

`curl -X GET "https://api-pss.prevyo.com/pss/api/anonymise" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Marie enverra la facture demain."}` 

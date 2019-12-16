Concepts
==

<img src="../images/ic_pss_concept.png" alt="drawing" width="80"/>

L'identification des concepts permet de faire émerger des concepts qui n'apparaissent pas explicitement dans le texte à analyser.

Query
--
* Method : POST
* Header : Content-Type: application/json
* Poa-Token : TOKEN
* Server : https://pss-api.prevyo.com/pss/api/concepts
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
    "original": "Bonjour Jean, peux tu appeler demain midi, la société Emvista pour parler à Paul ?",
    "concepts": [
        {
          "concept" : "communication",
          "source" : [
                "appeler",
                "parler"
            ],
            "score" : "0,5"
        },{
          "concept" : "personne",
          "source" : [
                "Jean",
                "Paul"
            ],
            "score" : "0,4"
        }
    ]
}
```

TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/concepts" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Bonjour Jean, peux tu appeler demain midi, la société Emvista pour parler à Paul."}` 

Concepts
==

<img src="../images/ic_pss_concept.png" alt="drawing" width="80"/>

L'identification des concepts permet de faire émerger des concepts qui n'apparaissent pas explicitement dans le texte à analyser.

Query
--
* Method : GET
* Header : Content-Type: application/json
* Poa-Token : TOKEN
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

`curl -X GET "https://api-pss.prevyo.com/pss/api/concepts" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Bonjour Jean, peux tu appeler demain midi, la société Emvista pour parler à Paul."}` 

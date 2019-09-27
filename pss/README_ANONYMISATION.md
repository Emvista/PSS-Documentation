Anonymiser
==

<img src="images/ic_pss_anonymisation.png" alt="drawing" width="80"/>

L'anonymiseur a pour objectif d'anonymiser toutes les entités que l'utilisateur souhaite (noms de personnes, de marques, d'organisations, lieux, dates, etc.).

Query
--
* Method : GET
* Header : Content-Type: application/json
* Basic Auth : BASIC_AUTH
* Poa-Token : TOKEN
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

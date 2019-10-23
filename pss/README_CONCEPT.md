Concepts
==

<img src="../images/ic_pss_concept.png" alt="drawing" width="80"/>

L'identification des concepts permet de faire émerger des concepts qui n'apparaissent pas explicitement dans le texte à analyser.

Query
--
* Method : POST
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
    "original": "Bonjour Jean, peux tu appeler demain midi, la société Emvista pour parler à Paul ?",
    "concepts": {
        "sud": 4,
        "lieu de rencontre": 1,
        "astronomie": 1,
        "mode de vie": 1,
        "poétique": 1,
        "organisation": 1,
        "monde de l'entreprise": 1,
        "commerce": 1,
        "moment": 1,
        "unité institutionnelle": 1,
        "religion": 1,
        "sociologie": 1,
        "géographie": 1,
        "jour": 1,
        "comportements": 1,
        "zoologie": 1,
        "jour de la semaine": 1,
        "religions": 1,
        "partie du jour": 1,
        "droit": 1,
        "christianisme": 1,
        "lieu": 1
    }
}
```

TEST
--

`curl -X GET "https://api-pss.prevyo.com/pss/api/concepts" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Bonjour Jean, peux tu appeler demain midi, la société Emvista pour parler à Paul."}` 

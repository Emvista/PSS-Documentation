Concepts
==

<img src="../images/ic_pss_concept.png" alt="drawing" width="80"/>

L'identification des concepts permet de faire émerger des concepts qui n'apparaissent pas explicitement dans le texte à analyser.

Query
--
* Method : POST
* Header : Content-Type: application/json
* Poa-Token : TOKEN
* Server : https://pss-api.prevyo.com/pss/api/v1/concepts
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Paris est une belle ville."
}
```

OUTPUT
--
HTTP Status : 200


* endTime (Time Stamp Unix) : Indication temporelle de la fin de l'analyse. Time Stamp Unix en millisecondes.

* concepts (List) : Liste de concepts.

* refSource (String) : Indique l'identifiant du terme. Cet identifiant existe dans plusieurs services ce qui permet de croiser des informations provenant de ces services.

* result (List) : Liste des résultats retournés par le service.

* score (Integer) : Score de l'élément auquel cet attribut est rattaché.

* source (String) : Terme à partir duquel un resultat a été généré.
Dans "Luc envoie une facture proforma", le concept "administratif" pourrait être généré à partir de la source "facture".

* startTime (Time Stamp Unix) : Indication temporelle du début de l'analyse. Time Stamp Unix en millisecondes.

* value (String) : Valeur de l'élément auquel cet attribut est rattaché.

Body :

```JSON
{
  "startTime" : 1597234837453,
  "endTime" : 1597234839091,
  "result" : {
    "concepts" : [ {
      "value" : "département",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "pays",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "monde",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "Terre",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "canton",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "région",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "zone",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 3
    }, {
      "value" : "agglomération",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 3
    }, {
      "value" : "métropole",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "campagne",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "Amérique",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "Europe",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "province",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "continent",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "mégalopole",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "::",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "état",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "planète",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "carte",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "communauté urbaine",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "cité",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "lieu",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 2
    }, {
      "value" : "localité",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "endroit",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 2
    }, {
      "value" : "commune",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 2
    }, {
      "value" : "collectivité territoriale",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "division administrative",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "zone urbaine",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "zone géographique",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "milieu physique",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "municipalité",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "classification",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "division territoriale",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "architecture",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "politique",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "médecine",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "commerce",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "prévention",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "tissu associatif",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "automobile",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "droit",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "histoire",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "administration",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "électricité",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "sociologie",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "économie",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "géographie",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    }, {
      "value" : "urbanisme",
      "source" : [ "ville" ],
      "refSource" : [ "0-4" ],
      "score" : 1
    } ]
  }
}
```

TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/v1/concepts" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Bonjour Jean, peux tu appeler demain midi, la société Emvista pour parler à Paul."}` 

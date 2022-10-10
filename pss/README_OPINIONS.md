Opinions
==

<img src="../images/ic_pss_sentiment.png" alt="drawing" width="80"/>

L'analyse d'opinions (<i>opinion mining</i> ou <i>sentiment analysis</i>) consiste à identifier les opinions (positif/négatif/neutre) 
qui sont exprimées dans le texte à analyser. Ce service permet d'identifier quelle est l'opinion ("value" dans l'output), qui l'exprime ("emitter" dans l'output) et sur quoi porte-t-elle ("target" dans l'output). De surcroit, ce service fournit pour chaque texte un score global d'opinion compris entre -1 et 1. Par exemple dans "Luc déteste ce produit alors que Sophie l'adore." le produit est positif du point de vue de Luc mais négatif du point de vue de Marie.

Query
--
* Method : POST
* Header : "Content-Type: application/json"
* Header : "Poa-Token : TOKEN"
* Server : https://pss-api.prevyo.com/pss/api/v1/sentiments
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Luc déteste les e-mails."
    "parameters": [
        {
          "name": "lowercase",
          "value": "false"
        },
      {
        "name": "emitter",
        "value": "Author"
      },
        {
			    "name": "lang",
			    "value": "LANG"
		    }
    ]
}
```


OUTPUT
--

HTTP Status : 200
Body :

```JSON

{
  "startTime" : 1665129391467,
  "endTime" : 1665129391467,
  "code" : 0,
  "message" : null,
  "result" : {
    "opinions" : [ {
      "target" : "e-mails",
      "refTarget" : "0-3",
      "context" : null,
      "value" : -1.0,
      "emitter" : "Luc"
    } ],
    "globalScore" : -1.0
  }
}
```

La sortie de ce service fournit :

* code (Integer) : Code d'erreur

* context (String) : Indication du contexte dans lequel l'opinion est repérée.

* emitter (String) : Emetteur de l'élément auquel cet attribut est rattaché. 

* endTime (Integer) : Indication temporelle qui correspond à la fin de l'analyse

* message (String) : Message d'erreur

* opinions (List) : Liste des opinions positives et négatives détectées dans le texte.

* refTarget (String) : Indique l'identifiant du terme sous la forme x-y avec x l'identifiant de la phrase et y l'identifiant du token. Cet identifiant existe dans plusieurs services ce qui permet de croiser des informations provenant de ces services.

* startTime (Integer) : Indication temporelle qui correspond au début de l'analyse

* target (String) : Cible sur laquelle porte l'élément auquel il est rattaché (l'opinion par exemple).

* value (String) : Valeur de l'élément auquel cet attribut est rattaché.


TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/v1/sentiments" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Je déteste les e-mails."}` 


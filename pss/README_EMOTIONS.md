Emotions
==

<img src="../images/ic_pss_sentiment.png" alt="drawing" width="80"/>


L'analyse d'émotions consiste à identifier les émotions (joie, colère, tristesse, dégoût, surprise, peur)
qui sont exprimées dans le texte à analyser. Ce service permet d'identifier quelle est l'émotion ("value" dans l'output), qui la ressent ("emitter" dans l'output) et ce qui la déclenche ("trigger" dans l'output). Par exemple dans "Luc déteste les e-mails.", l'émetteur Luc a une émotion colérique envers le produit.

Query
--
* Method : POST
* Header : "Content-Type: application/json"
* Header : "Poa-Token : TOKEN"
* Server : https://pss-api.prevyo.com/pss/api/v1/emotions
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
  "startTime" : 1665130587708,
  "endTime" : 1665130587708,
  "code" : 0,
  "message" : null,
  "result" : {
    "emotions" : [ {
      "trigger" : "e-mails",
      "refTrigger" : "0-3",
      "emitter" : "Luc",
      "value" : "anger"
    } ]
  }
}
```
La sortie de ce service fournit :

* code (Integer) : Code d'erreur

* emitter (String) : Emetteur de l'émotion.

* endTime (Integer) : Indication temporelle qui correspond à la fin de l'analyse

* message (String) : Message d'erreur

* refTrigger (String) : Indique l'identifiant du terme sous la forme x-y avec x l'identifiant de la phrase et y l'identifiant du token. Cet identifiant existe dans plusieurs services ce qui permet de croiser des informations provenant de ces services.

* startTime (Integer) : Indication temporelle qui correspond au début de l'analyse

* trigger (String) : Ce qui provoque une émotion.

* value (String) : Valeur de l'émotion parmi joie, tristesse, peur, colère, dégoût, surprise.



TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/v1/emotions" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Je déteste les e-mails."}` 


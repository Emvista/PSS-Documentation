Summarizer
==

<img src="../images/ic_pss_resume.png" alt="drawing" width="80"/>

The Summarizer service generates a textual abstract from a given text. The abstract is generated according to a compression rate defined by the user (from 1 to 10).

Query
--
* Method : POST
* Header : "Content-Type: application/json"
* Header : "Poa-Token : TOKEN"
* Server : https://pss-api.prevyo.com/pss/api/v1/summarizer
* Body : 

```JSON
{
	"text": "TEXT",
	"parameters": [
		{
			"name": "lang",
			"value": "LANG"
		}
	]
}
```

With LANG : fr (default) ou en.

INPUT
--

```JSON
{
    "text": "Emvista est une société (montpelliéraine) qui développe des briques logicielles pour comprendre le langage naturel."
}
```

OUTPUT
--
HTTP Status : 200
Body :

```JSON
{
  "startTime" : 1585838031451,
  "endTime" : 1585838036498,
  "result" : {
    "sentences" : [ {
      "id" : 0,
      "value" : "Emvista est une société qui développe des briques logicielles pour comprendre le langage naturel . ",
      "level" : 1
    }, {
      "id" : 0,
      "value" : "Emvista est une société qui développe des briques logicielles pour comprendre le langage naturel . ",
      "level" : 2
    }, {
      "id" : 0,
      "value" : "Emvista est une société qui développe des briques logicielles pour comprendre le langage naturel . ",
      "level" : 3
    }, {
      "id" : 0,
      "value" : "Emvista est une société qui développe des briques logicielles pour comprendre le langage naturel . ",
      "level" : 4
    }, {
      "id" : 0,
      "value" : "Emvista est une société qui développe des briques logicielles pour comprendre le langage naturel . ",
      "level" : 5
    }, {
      "id" : 0,
      "value" : "Emvista est une société qui développe des briques logicielles pour comprendre le langage naturel . ",
      "level" : 6
    }, {
      "id" : 0,
      "value" : "Emvista est une société qui développe des briques pour comprendre le langage . ",
      "level" : 7
    }, {
      "id" : 0,
      "value" : "Emvista est une société . ",
      "level" : 8
    }, {
      "id" : 0,
      "value" : "Emvista est une société . ",
      "level" : 9
    }, {
      "id" : 0,
      "value" : "Emvista est une société . ",
      "level" : 10
    } ]
  }
```

* endTime (Time Stamp Unix) : Indication temporelle de la fin de l'analyse. Time Stamp Unix en millisecondes.

* id (Integer) : Identifiant de l'élément auquel cet attribut est rattaché.

* level (Integer) : niveau d'analyse. Dans le cadre du service Summarizer, "level" est un niveau d'abstraction compris entre 1 et 10 : 1 indique un résumé proche du texte d'origine, 10 indique un texte le plus fortement résumé.

* result (List) : Liste des résultats retournés par le service.

* sentences (List) : Phrases analysées.

* startTime (Time Stamp Unix) : Indication temporelle du début de l'analyse. Time Stamp Unix en millisecondes.

* value (String) : Valeur de l'élément auquel cet attribut est rattaché.


TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/v1/summarizer" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Emvista est une société créée à Montpellier en février 2018. Emvista développe des briques logicielles pour comprendre le langage naturel. Les technologies d’intelligence artificielle mises en œuvre sont fondées à la fois sur du machine learning (système d'apprentissage) et sur des ontologies. À partir de ces briques technologiques, Emvista propose Prevyo, un assistant virtuel intelligent de gestion d’e-mails."}` 


Keywords
==

<img src="../images/ic_pss_mot_cle.png" alt="drawing" width="80"/>

L'extraction de mots clés fournit une liste ordonnée des termes les plus pertinents dans le contexte donné.

Query
--
* Method : POST
* Header : "Content-Type: application/json"
* Header : "Poa-Token : TOKEN"
* Server : https://pss-api.prevyo.com/pss/api/v1/keywords
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
avec LANG : fr (par défaut) ou en.

INPUT
--

```JSON
{
    "text": "Luc et Marc Dupont aiment les pommes rouge."
    "parameters": [
        {
            "name": "lowercase",
            "value": "false"
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
  "startTime" : 1597227690925,
  "endTime" : 1597227691933,
  "result" : {
    "keywords" : [ {
      "value" : "Luc",
      "refValue" : "0-0",
      "contexts" : [ "Luc" ],
      "score" : 1,
      "pos" : "NPP"
    }, {
      "value" : "et",
      "refValue" : "0-1",
      "contexts" : [ "et" ],
      "score" : 1,
      "pos" : "CC"
    }, {
      "value" : "Marc",
      "refValue" : "0-2",
      "contexts" : [ "Marc Dupont" ],
      "score" : 1,
      "pos" : "NPP"
    }, {
      "value" : "Dupont",
      "refValue" : "0-3",
      "contexts" : [ "Marc Dupont" ],
      "score" : 1,
      "pos" : "NPP"
    }, {
      "value" : "aimer",
      "refValue" : "0-4",
      "contexts" : [ "aimer" ],
      "score" : 1,
      "pos" : "V"
    }, {
      "value" : "le",
      "refValue" : "0-5",
      "contexts" : [ "pommes rouge" ],
      "score" : 1,
      "pos" : "DETD"
    }, {
      "value" : "pomme",
      "refValue" : "0-6",
      "contexts" : [ "pommes rouge" ],
      "score" : 1,
      "pos" : "NC"
    }, {
      "value" : "rouge",
      "refValue" : "0-7",
      "contexts" : [ "pommes rouge" ],
      "score" : 1,
      "pos" : "ADJ"
    }, {
      "value" : ".",
      "refValue" : "0-8",
      "contexts" : [ "." ],
      "score" : 1,
      "pos" : "PONCT"
    } ]
  }
}

```

* context (String) : Ensemble de mots constituant le contexte de value.
Dans "Luc envoie une facture proforma", "proforma" a pour contexte "facture proforma".

* contexts (List) : Liste de contextes. Cf. "context" dans le glossaire.

* endTime (Time Stamp Unix) : Indication temporelle de la fin de l'analyse. Time Stamp Unix en millisecondes.

* keywords (List) : Liste de mots clés.

* pos (String) : Catégorie grammaticale. Voir la liste des catégories grammaticales gérées. 

* refValue (String) : Indique l'identifiant du terme. Cet identifiant existe dans plusieurs services ce qui permet de croiser des informations provenant de ces services.

* result (List) : Liste des résultats retournés par le service.

* score (Integer) : Score de l'élément auquel cet attribut est rattaché.

* startTime (Time Stamp Unix) : Indication temporelle du début de l'analyse. Time Stamp Unix en millisecondes.

* value (String) : Valeur de l'élément auquel cet attribut est rattaché.



TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/v1/keywords" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Emvista est une société créée à Montpellier en février 2018. Emvista développe des briques logicielles pour comprendre le langage naturel."}` 


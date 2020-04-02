Keywords
==

<img src="../images/ic_pss_mot_cle.png" alt="drawing" width="80"/>

L'extraction de mots clés fournit une liste ordonnée des termes les plus pertinents dans le contexte donné.

Query
--
* Method : POST
* Header : Content-Type: application/json
* Poa-Token : TOKEN
* Server : https://pss-api.prevyo.com/pss/api/keywords
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Luc et Marc Dupont aiment les pommes rouge."
}
```

OUTPUT
--
HTTP Status : 200

* context (String) : Ensemble de mots constituant le contexte de value.
Dans "Luc envoie une facture proforma", "proforma" a pour contexte "facture proforma".

* contexts (List) : Liste de contextes. Cf. "context" dans le glossaire.

* endTime (Time Stamp Unix) : Indication temporelle de la fin de l'analyse. Time Stamp Unix en millisecondes.

* keywords (List) : Liste de mots clés.

* pos (String) : Catégorie grammaticale. Voir la liste des catégories grammaticales gérées. 

* result (List) : Liste des résultats retournés par le service.

* score (Integer) : Score de l'élément auquel cet attribut est rattaché.

* startTime (Time Stamp Unix) : Indication temporelle du début de l'analyse. Time Stamp Unix en millisecondes.

* value (String) : Valeur de l'élément auquel cet attribut est rattaché.

Body :

```JSON
{
  "startTime" : 1585836099260,
  "endTime" : 1585836103015,
  "result" : {
    "keywords" : [ {
      "value" : "Luc",
      "contexts" : [ "Luc" ],
      "score" : 1,
      "pos" : "NPP"
    }, {
      "value" : "Marc",
      "contexts" : [ "Marc Dupont" ],
      "score" : 1,
      "pos" : "NPP"
    }, {
      "value" : "Dupont",
      "contexts" : [ "Marc Dupont" ],
      "score" : 1,
      "pos" : "NPP"
    }, {
      "value" : "aimer",
      "contexts" : [ "Luc et Marc Dupont aiment les pommes rouge." ],
      "score" : 1,
      "pos" : "V"
    }, {
      "value" : "pomme",
      "contexts" : [ "pommes rouge" ],
      "score" : 1,
      "pos" : "NC"
    }, {
      "value" : "rouge",
      "contexts" : [ "pommes rouge" ],
      "score" : 1,
      "pos" : "ADJ"
    } ]
  }
}
```

TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/keyword" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Emvista est une société créée à Montpellier en février 2018. Emvista développe des briques logicielles pour comprendre le langage naturel."}` 


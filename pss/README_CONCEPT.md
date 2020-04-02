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
    "text": "Luc aime les pommes."
}
```

OUTPUT
--
HTTP Status : 200


* endTime (Time Stamp Unix) : Indication temporelle de la fin de l'analyse. Time Stamp Unix en millisecondes.

* concepts (List) : Liste de concepts.

* result (List) : Liste des résultats retournés par le service.

* score (Integer) : Score de l'élément auquel cet attribut est rattaché.

* source (String) : Terme à partir duquel un resultat a été généré.
Dans "Luc envoie une facture proforma", le concept "administratif" pourrait être généré à partir de la source "facture".

* startTime (Time Stamp Unix) : Indication temporelle du début de l'analyse. Time Stamp Unix en millisecondes.

* value (String) : Valeur de l'élément auquel cet attribut est rattaché.

Body :

```JSON
{
  "startTime" : 1585837488962,
  "endTime" : 1585837492390,
  "result" : {
    "concepts" : [ {
      "value" : "douche",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "gâteau",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "salade",
      "source" : [ "pomme" ],
      "score" : 3
    }, {
      "value" : "sablés bretons et leur duo de confiture de lait",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "Terre",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "pommier",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "Fondue au chocolat",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "mélange sucré salé",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "miam aux fruits",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "pomme d'amour",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "pizza gorgonzola pommes et noix",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "salade de fruits",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "fruit",
      "source" : [ "pomme" ],
      "score" : 3
    }, {
      "value" : "ingrédient de cuisine",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "produit végétal",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "fruit à pépin",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "aliment périssable",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "aliment",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "produit alimentaire",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "personne",
      "source" : [ "pomme" ],
      "score" : 2
    }, {
      "value" : "individu",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "être humain",
      "source" : [ "pomme" ],
      "score" : 2
    }, {
      "value" : "être vivant",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "fruit comestible",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "ingrédient de recette de cuisine",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "organe végétal",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "objet",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "fruit à pépins",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "gastronomie",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "biologie",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "botanique",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "cuisine",
      "source" : [ "pomme" ],
      "score" : 2
    }, {
      "value" : "agriculture",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "marine",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "architecture",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "nutrition",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "alimentation",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "fruits",
      "source" : [ "pomme" ],
      "score" : 1
    }, {
      "value" : "pomme de terre",
      "source" : [ "pomme" ],
      "score" : 1
    } ]
  }
}
```

TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/concepts" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Bonjour Jean, peux tu appeler demain midi, la société Emvista pour parler à Paul."}` 

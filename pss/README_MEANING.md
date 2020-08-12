Meaning Representation
==

<img src="../images/ic_pss_action.png" alt="drawing" width="80"/>

Meaning Representation retourne une représentation sémantique du texte donné en entrée.

Query
--
* Method : POST
* Header : Content-Type: application/json
* Poa-Token : TOKEN
* Server : https://pss-api.prevyo.com/pss/api/v1/meaningrepresentation
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Marie enverra la facture demain."
}
```

OUTPUT
--
HTTP Status : 200

* arguments (Object) : Sémantiquement un prédicat exprime une propriété ou une relation, c'est-à-dire quelque chose d'attribuable à une ou plusieurs entités (en l'occurrence les arguments).
Dans "Luc envoie une facture proforma", "envoyer" est un prédicat ayant pour arguments "Luc" et "facture proforma".

* endTime (Time Stamp Unix) : Indication temporelle de la fin de l'analyse. Time Stamp Unix en millisecondes.

* id (Integer) : Identifiant de l'élément auquel cet attribut est rattaché.

* negation (Boolean : true/false) : Indique si le token, la valeur ou le prédicat considéré est négatif ou affirmatif.
Dans "Luc envoie une facture proforma", l'attribut negation vaut false car la phrase est affirmative.

* predicate (String) : Sémantiquement un prédicat exprime une propriété ou une relation, c'est-à-dire quelque chose d'attribuable à une ou plusieurs entités (en l'occurrence les arguments).
Dans "Luc envoie une facture", "envoyer" est un prédicat ayant pour arguments "Luc" et "facture".

* refSource (String) : Indique l'identifiant du terme. Cet identifiant existe dans plusieurs services ce qui permet de croiser des informations provenant de ces services.

* refValue (String) : Indique l'identifiant du terme. Cet identifiant existe dans plusieurs services ce qui permet de croiser des informations provenant de ces services.

* result (List) : Liste des résultats retournés par le service.

* role (String) : Role sémantique parmis : vn:Agent, vn:Theme, vn:Patient, vn:Time, vn:Beneficiary, vn:Location, vn:Recipient, vn:Pivot, etc.
Dans "Luc envoie une facture proforma", "Luc" a pour rôle Agent et "facture proforma" a pour rôle Theme.

* score (Integer) : Score de l'élément auquel cet attribut est rattaché.

* start (Integer) : Index de début (en nombre de caractères).
Dans "Luc envoie une facture proforma", la valeur de end pour le mot "une" est 11.

* tags (List) : Liste d'étiquettes sémantiques. Cf. "tag".

* value (String) : Valeur de l'élément auquel cet attribut est rattaché.


Body :

```JSON
{
  "startTime" : 1597235443769,
  "endTime" : 1597235445413,
  "result" : {
    "predicates" : [ {
      "id" : 6,
      "value" : [ "give-13.1" ],
      "source" : "envoyer",
      "refSource" : "envoyer",
      "negation" : false,
      "arguments" : [ {
        "id" : 0,
        "role" : "Agent",
        "tags" : [ "nerd:Person>Individual>FirstName" ],
        "value" : "Marie",
        "refValue" : "0-0"
      }, {
        "id" : 25,
        "role" : "TimeExact",
        "tags" : [ "nerd:Time" ],
        "value" : "demain",
        "refValue" : "0-4"
      }, {
        "id" : 17,
        "role" : "Theme",
        "tags" : [ "" ],
        "value" : "facture",
        "refValue" : "0-3"
      } ]
    }, {
      "id" : 14,
      "value" : [ "cardinality" ],
      "source" : "le",
      "refSource" : "le",
      "negation" : false,
      "arguments" : [ {
        "id" : 17,
        "role" : "Theme",
        "tags" : [ "" ],
        "value" : "facture",
        "refValue" : "0-3"
      }, {
        "id" : -1,
        "role" : "Measureexact",
        "tags" : [ "" ],
        "value" : "1",
        "refValue" : null
      } ]
    }, {
      "id" : 0,
      "value" : [ "rdf:type" ],
      "source" : "Marie",
      "refSource" : "Marie",
      "negation" : false,
      "arguments" : [ {
        "id" : 0,
        "role" : "Experiencer",
        "tags" : [ "nerd:Person>Individual>FirstName" ],
        "value" : "Marie",
        "refValue" : "0-0"
      }, {
        "id" : -1,
        "role" : "Attribute",
        "tags" : [ "" ],
        "value" : "nerd:Person",
        "refValue" : null
      } ]
    }, {
      "id" : 0,
      "value" : [ "isA" ],
      "source" : "Marie",
      "refSource" : "Marie",
      "negation" : false,
      "arguments" : [ {
        "id" : 0,
        "role" : "Experiencer",
        "tags" : [ "nerd:Person" ],
        "value" : "Marie",
        "refValue" : "0-0"
      }, {
        "id" : -1,
        "role" : "Attribute",
        "tags" : [ "" ],
        "value" : "feminine",
        "refValue" : null
      } ]
    } ]
  }
}
```

TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/v1/meaningrepresentation" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Marie enverra la facture demain."}` 

Highlighter
==

<img src="../images/ic_pss_highlighter.png" alt="drawing" width="80"/>

La reconnaissance des entités nommées vise à identifier dans un texte les noms de personnes, les noms de lieux, les noms d'organisations, les noms de produits, etc.

Query
--
* Method : POST
* Header : Content-Type: application/json
* Poa-Token : TOKEN
* Server : https://pss-api.prevyo.com/pss/api/v1/highlighter
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
    "text": "Luc et Marc Dupont aiment les pommes.",
    "parameters": [
        {
            "name": "lowercase",
            "value": "true"
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
  "startTime" : 1597235911116,
  "endTime" : 1597235912146,
  "result" : {
    "namedEntities" : [ {
      "value" : "Luc",
      "refValue" : "0-0",
      "tags" : [ "nerd:Person" ],
      "start" : 0,
      "end" : 3
    }, {
      "value" : "Marc Dupont",
      "refValue" : "0-2",
      "tags" : [ "nerd:Person" ],
      "start" : 7,
      "end" : 18
    } ],
    "annotatedValue" : "<nerd:Person>Luc</nerd:Person> et <nerd:Person>Marc Dupont</nerd:Person> aiment les pommes ."
  }
}
```

* annotatedValue (String) : Donnée textuelle annotée avec le langage de balisage XML. Dans ce service, une balise est de la forme <TAG>VALUE</TAG> avec TAG correspondant à un type d'entité (cf. "tag") et VALUE correspondant à la chaîne de caractères annotée.

* end (Integer) : Index de fin (en nombre de caractères).
Dans "Luc envoie une facture proforma", la valeur de end pour le mot "une" est 14.

* endTime (Time Stamp Unix) : Indication temporelle de la fin de l'analyse. Time Stamp Unix en millisecondes.

* namedentities (List) : Liste des entités nommées (noms de personnes, de lieux, d'organisations, etc. ; cf. les tags ayant pour préfixe "nerd:" dans l'entrée "tag" du glossaire).

* refValue (String) : Indique l'identifiant du terme. Cet identifiant existe dans plusieurs services ce qui permet de croiser des informations provenant de ces services.

* result (List) : Liste des résultats retournés par le service.

* start (Integer) : Index de début (en nombre de caractères).
Dans "Luc envoie une facture proforma", la valeur de end pour le mot "une" est 11.

* startTime (Time Stamp Unix) : Indication temporelle du début de l'analyse. Time Stamp Unix en millisecondes.

* tags (List) : Liste d'étiquettes sémantiques. Cf. "tag".

* tag (String) : Etiquette sémantique faisant partie de l'ontologie NERD ou de l'otologie WSD : nerd:Date, nerd:Animal, nerd:Function, nerd:Nation, nerd:Time, nerd:Timemin, nerd:Timemax, nerd:Timefuzzy, nerd:Timeduration, nerd:Person, nerd:Facility, nerd:Location, nerd:LocationSource, nerd:LocationDestination, nerd:LocationFuzzy, nerd:LocationSpan, nerd:Money, nerd:Organization, nerd:Measure, nerd:PhoneNumber, nerd:EMail, nerd:Duration, nerd:Set, nerd:Url, nerd:Brand, nerd:Event, nerd:FictionalCharacter, nerd:Language, nerd:TransportLine, nerd:Sportsteam, nerd:Sport, nerd:Media, nerd:Method, nerd:Product, nerd:ProductRange, nerd:ReferenceDocument, nerd:Reference, nerd:Reward, nerd:Species, nerd:Ingredient, wsd:Concrete, wsd:Abstract, wsd:Animate, wsd:Inanimate, wsd:LivingBeing, wsd:Animal, wsd:Vehicle, wsd:Vegetal, wsd:Location, wsd:Time, wsd:TimeMin, wsd:TimeMax, wsd:TimeFuzzy, wsd:Sport, wsd:Color, wsd:MusicalInstrument, wsd:Religion, ...
Dans "Luc envoie une facture proforma", "Luc" a pour tag nerd:Person.

* value (String) : Valeur de l'élément auquel cet attribut est rattaché.

TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/v1/highlighter" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Marie enverra la facture demain à Pierre de chez Emvista."}`

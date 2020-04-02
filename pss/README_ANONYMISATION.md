Anonymiser
==

<img src="../images/ic_pss_anonymisation.png" alt="drawing" width="80"/>

L'anonymiseur a pour objectif d'anonymiser toutes les entités que l'utilisateur souhaite (noms de personnes, de marques, d'organisations, lieux, dates, etc.).

Query
--
* Method : POST
* Header : Content-Type: application/json
* Poa-Token : TOKEN
* Server : https://pss-api.prevyo.com/pss/api/anonymise
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Le numéro de Luc est le 06 21 32 43 54."
}
```

OUTPUT
--
HTTP Status : 200

* annotatedValue (String) : Donnée textuelle annotée avec le langage de balisage XML. Dans ce service, une balise est de la forme <TAG_INT/> avec TAG correspondant à un type d'entité et INT correspondant à "start" qui sert d'identifiant.

* end (Integer) : Index de fin (en nombre de caractères).
Dans "Luc envoie une facture proforma", la valeur de end pour le mot "une" est 14.

* endTime (Time Stamp Unix) : Indication temporelle de la fin de l'analyse. Time Stamp Unix en millisecondes.

* namedentities (List) : Liste des entités nommées (noms de personnes, de lieux, d'organisations, etc. ; cf. les tags ayant pour préfixe "nerd:" dans l'entrée "tag" du glossaire).

* result (List) : Liste des résultats retournés par le service.

* source (String) : Terme à partir duquel un resultat a été généré.
Dans "Luc envoie une facture proforma", le concept "administratif" pourrait être généré à partir de la source "facture".

* start (Integer) : Index de début (en nombre de caractères).
Dans "Luc envoie une facture proforma", la valeur de end pour le mot "une" est 11.

* startTime (Time Stamp Unix) : Indication temporelle du début de l'analyse. Time Stamp Unix en millisecondes.

* tags (List) : Liste d'étiquettes sémantiques. Cf. "tag".

* tag (String) : Etiquette sémantique faisant partie de l'ontologie NERD ou de l'otologie WSD : nerd:Date, nerd:Animal, nerd:Function, nerd:Nation, nerd:Time, nerd:Timemin, nerd:Timemax, nerd:Timefuzzy, nerd:Timeduration, nerd:Person, nerd:Facility, nerd:Location, nerd:LocationSource, nerd:LocationDestination, nerd:LocationFuzzy, nerd:LocationSpan, nerd:Money, nerd:Organization, nerd:Measure, nerd:PhoneNumber, nerd:EMail, nerd:Duration, nerd:Set, nerd:Url, nerd:Brand, nerd:Event, nerd:FictionalCharacter, nerd:Language, nerd:TransportLine, nerd:Sportsteam, nerd:Sport, nerd:Media, nerd:Method, nerd:Product, nerd:ProductRange, nerd:ReferenceDocument, nerd:Reference, nerd:Reward, nerd:Species, nerd:Ingredient, wsd:Concrete, wsd:Abstract, wsd:Animate, wsd:Inanimate, wsd:LivingBeing, wsd:Animal, wsd:Vehicle, wsd:Vegetal, wsd:Location, wsd:Time, wsd:TimeMin, wsd:TimeMax, wsd:TimeFuzzy, wsd:Sport, wsd:Color, wsd:MusicalInstrument, wsd:Religion, ...
Dans "Luc envoie une facture proforma", "Luc" a pour tag nerd:Person.

* value (String) : Valeur de l'élément auquel cet attribut est rattaché.


Body :

```JSON
{
  "startTime" : 1585833674415,
  "endTime" : 1585833678144,
  "result" : {
    "namedentities" : [ {
      "value" : "Luc",
      "tags" : [ "nerd:Person" ],
      "start" : 13,
      "end" : 16,
      "source" : null
    }, {
      "value" : "le 06 21 32 43 54 .",
      "tags" : [ "nerd:PhoneNumber" ],
      "start" : 24,
      "end" : 43,
      "source" : null
    } ],
    "annotatedValue" : "Le numéro de <PERSON_13/> est le <PHONENUMBER_24/>"
  }
}
```

TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/anonymise" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Bonjour Jean, peux tu appeler demain midi, la société Emvista pour parler à Paul."}` 

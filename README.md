Prevyo Semantic Services
=

Briques logicielles pour comprendre le langage naturel.

Pour tester les Prevyo Semantic Services vous pouvez soit utiliser l'interface web [https://pss.prevyo.com/](https://pss.prevyo.com/) soit utiliser l'API REST. Pour utiliser l'API REST, vous devez créer un compte Prevyo sur [https://pss.prevyo.com/](https://pss.prevyo.com/) puis nous contacter à [dev@emvista.com](mailto:dev@emvista.com) pour obtenir votre Token d'authentifcation.

Version
==
- 2020.03 [changelog](CHANGELOG.md)
- 2020.03 [changelog](CHANGELOG.md)
- 2019.12

Glossaire
==

Le glossaire décrit les attributs fournis en sortie des services.

* Agent, Theme, Beneficiary, Recipient, Patient, Pivot, Attribut, ... : Roles sémantiques faisant partie de l'ontologie VN : vn:Agent, vn:Theme, vn:Patient, vn:Time, vn:Beneficiary, vn:Location, vn:Recipient, vn:Pivot, etc.
Dans "Luc envoie une facture proforma", "Luc" a pour rôle Agent et "facture proforma" a pour rôle Theme.

* arguments (Object) : Sémantiquement un prédicat exprime une propriété ou une relation, c'est-à-dire quelque chose d'attribuable à une ou plusieurs entités (en l'occurrence les arguments)
Dans "Luc envoie une facture proforma", "envoyer" est un prédicat ayant pour arguments "Luc" et "facture proforma".

* context (String) : Ensemble de mots constituant le contexte de value.
Dans "Luc envoie une facture proforma", "proforma" a pour contexte "facture proforma".

* emotions (List) : Liste d'émotions parmi : joie, tristesse, peur, colère, dégoût, surprise.
Dans "Luc déteste envoyer des e-mails", la colère et le dégoût sont des émotions déclenchées.

* end (Integer) : Index de fin (en nombre de caractères).
Dans "Luc envoie une facture proforma", la valeur de end pour le mot "une" est 14.

* id (Integer) : Identifiant de l'élément auquel cet attribut est rattaché.

* NC, ADJ, VB, NPP : Etiquettes grammaticales faisant référence respectivement à : nom commun, adjectif, verbe, nom propre
Dans "Luc envoie une facture proforma", "Luc" est NPP (nom propre) et "facture" est NC (nom commun).

* negation (Boolean : true/false) : Indique si la valeur ou le prédicat considéré est négatif ou affirmatif.
Dans "Luc envoie une facture proforma", l'attribut negation vaut false car la phrase est affirmative.

* point-of-view (String) : Indication sur la personne qui émet une information, un jugement, un sentiment, une émotion, ...
Dans "Luc déteste envoyer des e-mails", la colère et le dégoût sont des émotions portées sur l'envoie d'e-mails, du point de vue de Luc.

* predicate (String) : Sémantiquement un prédicat exprime une propriété ou une relation, c'est-à-dire quelque chose d'attribuable à une ou plusieurs entités (en l'occurrence les arguments).
Dans "Luc envoie une facture", "envoyer" est un prédicat ayant pour arguments "Luc" et "facture".

* results (List) : Liste des résultats retournés par le service.

* score (Integer) : Score de l'élément auquel cet attribut est rattaché.

* sentiment (String) : Sentiment positif, négatif ou neutre exprimé dans le texte.
Dans "Luc envoie une facture", "envoyer" est un prédicat ayant pour arguments "Luc" et "facture".

* source (String) : Terme à partir duquel un resultat a été généré.
Dans "Luc envoie une facture proforma", le concept "administratif" pourrait être généré à partir de la source "facture".

* start (Integer) : Index de début (en nombre de caractères).
Dans "Luc envoie une facture proforma", la valeur de end pour le mot "une" est 11.

* tag (String) : Etiquette sémantique faisant partie de l'ontologie NERD ou de l'otologie WSD : nerd:Date, nerd:Animal, nerd:Function, nerd:Nation, nerd:Time, nerd:Timemin, nerd:Timemax, nerd:Timefuzzy, nerd:Timeduration, nerd:Person, nerd:Facility, nerd:Location, nerd:LocationSource, nerd:LocationDestination, nerd:LocationFuzzy, nerd:LocationSpan, nerd:Money, nerd:Organization, nerd:Measure, nerd:PhoneNumber, nerd:EMail, nerd:Duration, nerd:Set, nerd:Url, nerd:Brand, nerd:Event, nerd:FictionalCharacter, nerd:Language, nerd:TransportLine, nerd:Sportsteam, nerd:Sport, nerd:Media, nerd:Method, nerd:Product, nerd:ProductRange, nerd:ReferenceDocument, nerd:Reference, nerd:Reward, nerd:Species, nerd:Ingredient, wsd:Concrete, wsd:Abstract, wsd:Animate, wsd:Inanimate, wsd:LivingBeing, wsd:Animal, wsd:Vehicle, wsd:Vegetal, wsd:Location, wsd:Time, wsd:TimeMin, wsd:TimeMax, wsd:TimeFuzzy, wsd:Sport, wsd:Color, wsd:MusicalInstrument, wsd:Religion, ...
Dans "Luc envoie une facture proforma", "Luc" a pour tag nerd:Person.

* value (String) : Valeur de l'élément auquel cet attribut est rattaché. La valeur est soit un mot tel qu'il apparaît dans le contexte, soit sa forme lemmatisée (entrée dictionnairique).

* passive (Boolean: true/false) : Indique la voix active ou passive.
Dans "Luc envoie une facture proforma", l'attribut "passive" vaut false car la phrase est à la voix active.

USAGE
==

Postman
===

Télécharger et installer [POSTMAN](https://www.getpostman.com/)

Téléchargez le fichier collection Postman : [Postman Collection](postman/PSS.postman_collection.json) et importez-le dans Postman

Créez 2 variables :
* PSS-SERVER : https://pss-api.prevyo.com/
* POA-TOKEN : votre token Prevyo

REST API
=

Keywords
==

<img src="images/ic_pss_mot_cle.png" alt="drawing" width="80"/>

L'extraction de mots clés fournit une liste ordonnée des termes les plus pertinents dans le contexte donné.

[Rest API](pss/README_KEYWORD.md)

Sentiment
==

<img src="images/ic_pss_sentiment.png" alt="drawing" width="80"/>

L'analyse d’opinion (<i>opinion mining</i> ou <i>sentiment analysis</i>) consiste à analyser un texte pour identifier les sentiments (positif/négatif/neutre) ainsi que les émotions ( joie, tristesse, peur, colère, dégoût, surprise) qui y sont exprimés.

[Rest API](pss/README_SENTIMENT.md)

Anonymiser
==

<img src="images/ic_pss_anonymisation.png" alt="drawing" width="80"/>

L'anonymiseur a pour objectif d'anonymiser toutes les entités que l'utilisateur souhaite (noms de personnes, de marques, d'organisations, lieux, dates, etc.).

[Rest API](pss/README_ANONYMISATION.md)

Concepts
==

<img src="images/ic_pss_concept.png" alt="drawing" width="80"/>

L'identification des concepts permet de faire émerger des concepts qui n'apparaissent pas explicitement dans le texte à analyser.

[Rest API](pss/README_CONCEPT.md)

NLU 
==

<img src="images/ic_pss_nlu.png" alt="drawing" width="80"/>

Le NLU (<i>Natural Language Understanding</i>) sert à extraire les intentions exprimées dans une phrase.

[Rest API](pss/README_NLU.md)

Résumés
==

<img src="images/ic_pss_resume.png" alt="drawing" width="80"/>

Le générateur de résumés crée une synthèse du texte, dont le niveau d'abstraction est paramétrable.

[Rest API](pss/README_RESUME.md)

Actions
==

<img src="images/ic_pss_action.png" alt="drawing" width="80"/>

La reconnaissance d'actions vise à extraire les actions que doit faire une personne, pour quand, comment, pour qui, etc.

[Rest API](pss/README_ACTION.md)

Highlighter
==

<img src="images/ic_pss_highlighter.png" alt="drawing" width="80"/>

La reconnaissance des entités nommées vise à identifier dans un texte les noms de personnes, les noms de lieux, les noms d'organisations, les noms de produits, etc.

[Rest API](pss/README_HIGHLIGHTER.md)

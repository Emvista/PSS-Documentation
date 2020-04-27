Prevyo Semantic Services
=

Tools for natural language processing.

To use Prevyo Semantic Services: web interface [https://pss.prevyo.com/](https://pss.prevyo.com/) and REST API are available. 
To use the REST API you will need to create an Prevyo account on [https://pss.prevyo.com/](https://pss.prevyo.com/) then to contact [dev@emvista.com](mailto:dev@emvista.com) asking for an authentification token.

Version
==
- 2020.05 [changelog](CHANGELOG.md#version-202005)
- 2020.03 [changelog](CHANGELOG.md#version-202003)
- 2019.12


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


Sentiment analysis aims at identifying sentiments (positive, negative, and neutral) and emotions (joy, sadness, fear, anger, disgust, surprise) which are embedded in the text to analyse. This Sentiment service provides words and multiwords level analysis. Hence, it is possible in a very fine-grained way to identify several sentiments and emotions within a given sentence. For instance, in "Luc hates this product whereas Marie likes it.", the "product" is negative from Luc's point of view but not from Maries's one.

[Rest API](pss/README_SENTIMENT-en.md)

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

Summarizer
==

<img src="images/ic_pss_resume.png" alt="drawing" width="80"/>

The Summarizer service generates a textual abstract from a given text. The abstract is generated according to a compression rate defined by the user (from 1 to 10).

[Rest API](pss/README_RESUME-en.md)

Meaning Representation
==

<img src="images/ic_pss_action.png" alt="drawing" width="80"/>

Meaning Representation retourne une représentation sémantique du texte donné en entrée.

[Rest API](pss/README_MEANING.md)

Highlighter
==

<img src="images/ic_pss_highlighter.png" alt="drawing" width="80"/>

La reconnaissance des entités nommées vise à identifier dans un texte les noms de personnes, les noms de lieux, les noms d'organisations, les noms de produits, etc.

[Rest API](pss/README_HIGHLIGHTER.md)

Parser
==

Le parser fournit une analyse syntaxique du texte, c'est-à-dire indique les catégories grammaticales de chaque mot, leur nature, leur lemme, etc., ainsi que les relations syntaxiques entre ces mots (sujet, objet, compléments, etc.).

[Rest API](pss/README_PARSER.md)


Glossaire général
==

* annotatedValue (String) : Donnée textuelle annotée en utilisant le langage de balisage XML.

* arguments (Object) : Sémantiquement un prédicat exprime une propriété ou une relation, c'est-à-dire quelque chose d'attribuable à une ou plusieurs entités (en l'occurrence les arguments).
Dans "Luc envoie une facture proforma", "envoyer" est un prédicat ayant pour arguments "Luc" et "facture proforma".

* concepts (List) : Liste de concepts.

* context (String) : Ensemble de mots constituant le contexte de value.
Dans "Luc envoie une facture proforma", "proforma" a pour contexte "facture proforma".

* contexts (List) : Liste de contextes. Cf. "context" dans le glossaire.

* definite (Boolean) : Indication sur le caractère défini ou indéfini de l'élément auquel cet attribut est rattaché (un token par exemple).

* depRel (String) : Type de la relation de dépendance syntaxique entre deux tokens : sujet, objet, complément, etc. Voir la liste des dépendances gérées.

* emotions (List) : Liste d'émotions parmi : joie, tristesse, peur, colère, dégoût, surprise.
Dans "Luc déteste envoyer des e-mails", la colère et le dégoût sont des émotions déclenchées.

* end (Integer) : Index de fin (en nombre de caractères).
Dans "Luc envoie une facture proforma", la valeur de end pour le mot "une" est 14.

* endTime (Time Stamp Unix) : Indication temporelle de la fin de l'analyse. Time Stamp Unix en millisecondes.

* form (String) : mot ou locution tel qu'il apparaît dans le contexte (accordé en genre et en nombre par exemple). Par exemple la forme "envoyées" a pour lemme "envoyer". Voir "lemma" dans le glossaire.

* head (String) : Tête syntaxique d'un token.

* id (Integer) : Identifiant de l'élément auquel cet attribut est rattaché.

* keywords (List) : Liste de mots clés.

* lemma (String) : Forme canonique, considérée par convention comme non fléchie, d’un nom, d’un adjectif, d’un verbe, d’un pronom, présentée comme entrée principale, dans un dictionnaire. Par exemple la forme "envoyées" a pour lemme "envoyer". Voir "form" dans le glossaire.

* level (Integer) : niveau d'analyse. Dans le cadre du service Summarizer, "level" est un niveau d'abstraction compris entre 1 et 10 : 1 indique un résumé proche du texte d'origine, 10 indique un texte le plus fortement résumé.

* namedentities (List) : Liste des entités nommées (noms de personnes, de lieux, d'organisations, etc. ; cf. les tags ayant pour préfixe "nerd:" dans l'entrée "tag" du glossaire).

* negation (Boolean : true/false) : Indique si le token, la valeur ou le prédicat considéré est négatif ou affirmatif.
Dans "Luc envoie une facture proforma", l'attribut negation vaut false car la phrase est affirmative.

* person (String) : Indique la première personne ("1"), la deuxième personne ("2") ou la troisième personne ("3"). Par exemple, "vous" est la deuxième personne du pluriel (voir "plural").

* pointOfView (String) : Indication sur la personne qui émet une information, un jugement, un sentiment, une émotion, ...
Dans "Luc déteste envoyer des e-mails", la colère et le dégoût sont des émotions portées sur l'envoie d'e-mails, du point de vue de Luc.

* plural (String) : Indication sur le caractère singulier ("false") ou pluriel ("true") de l'élément auquel il est rattaché. 

* polarity (Double between -1 and +1) : Sentiment positif, négatif ou neutre exprimé dans le texte.
Dans "Luc déteste envoyer une facture", un sentiment négatif est déclenchée.

* pos (String) : Catégorie grammaticale. Voir la liste des catégories grammaticales gérées. 

* predicate (String) : Sémantiquement un prédicat exprime une propriété ou une relation, c'est-à-dire quelque chose d'attribuable à une ou plusieurs entités (en l'occurrence les arguments).
Dans "Luc envoie une facture", "envoyer" est un prédicat ayant pour arguments "Luc" et "facture".

* pronominal (Boolean) : Indique si le verbe est pronominal.

* result (List) : Liste des résultats retournés par le service.

* role (String) : Role sémantique parmis : vn:Agent, vn:Theme, vn:Patient, vn:Time, vn:Beneficiary, vn:Location, vn:Recipient, vn:Pivot, etc.
Dans "Luc envoie une facture proforma", "Luc" a pour rôle Agent et "facture proforma" a pour rôle Theme.

* score (Integer) : Score de l'élément auquel cet attribut est rattaché.

* sentences (List) : Phrases analysées.

* source (String) : Terme à partir duquel un resultat a été généré.
Dans "Luc envoie une facture proforma", le concept "administratif" pourrait être généré à partir de la source "facture".

* start (Integer) : Index de début (en nombre de caractères).
Dans "Luc envoie une facture proforma", la valeur de end pour le mot "une" est 11.

* startTime (Time Stamp Unix) : Indication temporelle du début de l'analyse. Time Stamp Unix en millisecondes.

* tags (List) : Liste d'étiquettes sémantiques. Cf. "tag".

* tag (String) : Etiquette sémantique faisant partie de l'ontologie NERD ou de l'otologie WSD : nerd:Date, nerd:Animal, nerd:Function, nerd:Nation, nerd:Time, nerd:Timemin, nerd:Timemax, nerd:Timefuzzy, nerd:Timeduration, nerd:Person, nerd:Facility, nerd:Location, nerd:LocationSource, nerd:LocationDestination, nerd:LocationFuzzy, nerd:LocationSpan, nerd:Money, nerd:Organization, nerd:Measure, nerd:PhoneNumber, nerd:EMail, nerd:Duration, nerd:Set, nerd:Url, nerd:Brand, nerd:Event, nerd:FictionalCharacter, nerd:Language, nerd:TransportLine, nerd:Sportsteam, nerd:Sport, nerd:Media, nerd:Method, nerd:Product, nerd:ProductRange, nerd:ReferenceDocument, nerd:Reference, nerd:Reward, nerd:Species, nerd:Ingredient, wsd:Concrete, wsd:Abstract, wsd:Animate, wsd:Inanimate, wsd:LivingBeing, wsd:Animal, wsd:Vehicle, wsd:Vegetal, wsd:Location, wsd:Time, wsd:TimeMin, wsd:TimeMax, wsd:TimeFuzzy, wsd:Sport, wsd:Color, wsd:MusicalInstrument, wsd:Religion, ...
Dans "Luc envoie une facture proforma", "Luc" a pour tag nerd:Person.

* tense (String) : Indique le temps utilisé ("past", "present", ou "future").

* tokens (List) : Ensemble de tokens, c'est-à-dire de mots ou locutions.

* type : Type de la phrase analysée : declarative, exclamative, interrogative ou imperative. 

* value (String) : Valeur de l'élément auquel cet attribut est rattaché.

* verbalForm (String) : Forme verbale : active ou passive.

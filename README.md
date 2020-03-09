Prevyo Semantic Services
=

Briques logicielles pour comprendre le langage naturel.

Pour tester les Prevyo Semantic Services vous pouvez soit utiliser l'interface web [https://pss.prevyo.com/](https://pss.prevyo.com/) soit utiliser l'API REST. Pour utiliser l'API REST, il vous faudra créer un compte Prevyo sur [https://pss.prevyo.com/](https://pss.prevyo.com/) puis nous contacter à [dev@emvista.com](mailto:dev@emvista.com) pour avoir votre Token d'authentifcation.

USAGE
==

Postman
==

Télécharger et installer [POSTMAN](https://www.getpostman.com/)

Téléchargez le fichier collection Postman : [Postman Collection](postman/PSS.postman_collection.json) et importez le dans Postman

Créez 2 variables :
* API PSS-SERVER : https://pss-api.prevyo.com/
* POA-TOKEN : votre token Prevyo

Glossaire
==
* Lemme : Forme neutre d'un mot. C'est-à-dire sans avoir subi de modification par le contexte (singulier pour un nom ou adjectif, infinitif pour un verbe)
* Forme : Forme d'un mot (ou ensemble de mots) tel qu'il a été utilisé dans le texte.
* Part-of-speech (Pos) : Catégories grammaticales. Par exemple : nom commun (NC), adjectif (ADJ), verbe (VB), nom propre (NPP)

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

L'analyse d’opinion (<i>opinion mining</i> ou <i>sentiment analysis</i>) consiste à analyser un texte pour identifier les sentiments ainsi que les émotions qui y sont exprimés.

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

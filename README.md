Prevyo Semantic Services
=

Briques logicielles pour comprendre le langage naturel.

Pour tester les Prevyo Semantic Services vous pouvez soit utiliser l'interface web [https://pss.prevyo.com/](https://pss.prevyo.com/) soit utiliser l'API REST. Pour utiliser l'API REST, vous devez créer un compte Prevyo sur [https://pss.prevyo.com/](https://pss.prevyo.com/) puis nous contacter à [dev@emvista.com](mailto:dev@emvista.com) pour obtenir votre Token d'authentifcation.

Version
==
- 2020.03 [changelog](CHANGELOG.md)
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

L'analyse de sentiments (<i>opinion mining</i> ou <i>sentiment analysis</i>) consiste à identifier les sentiments (positif/négatif/neutre) ainsi que les émotions (joie, tristesse, peur, colère, dégoût, surprise) qui sont exprimés dans le texte à analyser. Ce service propose une analyse au niveau des mots et des groupes de mots significatifs. Il est ainsi possible d'identifier des sentiments ou émotions contradictoires au sein d'une même phrase. Par exemple dans "Luc déteste ce produit alors que Marie l'adore." le produit est positif du point de vue de Luc mais négatif du point de vue de Marie.

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

Résumés
==

<img src="images/ic_pss_resume.png" alt="drawing" width="80"/>

Le générateur de résumés crée une synthèse du texte, dont le niveau d'abstraction est paramétrable.

[Rest API](pss/README_RESUME.md)

Meaning Representation
==

<img src="images/ic_pss_action.png" alt="drawing" width="80"/>

La reconnaissance d'actions vise à extraire les actions que doit faire une personne, pour quand, comment, pour qui, etc.

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

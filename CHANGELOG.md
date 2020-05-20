# Version 2020.05

## Nouveautés de l'API :
- Nouveau JSON de sortie ;
- Mise en place d'une gestion de versions dans les URLs des services : 
`/pss/api/v1/<service>` ;
- L'API devient asynchrone au-delà d'un certain nombre de caractères. Si vous envoyez un long texte, vous aurez alors un retour (code Http) qui vous informera de la prise en compte de votre demande. Une url est renvoyée pour interroger le serveur qui soit vous répondra que la demande est toujours en cours d'analyse, soit vous renverra le résultat de l'analyse ;
- Nouveau service Parser : analyse syntaxique ;
- Documentation complète.

## Nouveautés sur le système de compréhension du langage naturel (Recursive Linguistic Analyzer) :
- Exécution plus rapide

## Nouveautés sur la plateforme de démonstration :

# Version 2020.03

## Nouveautés sur le système de compréhension du langage naturel (Recursive Linguistic Analyzer) :
- Amélioration qualitative du système d'analyse sémantique avec l'intégration des modèles de langage récents (CamemBERT, FlauBERT) ;
- Gestion des modalités dans la représentation sémantique du texte (obligation, suggestion, ...) ;
- Résolution des coréférences dans la représentation sémantique.

## Nouveautés sur la plateforme de démonstration :
- Visualisation des résultats améliorée (notamment concernant la visualisation du JSON qui intègre dorénavant un moteur de recherche et une navigation facilitée ; affichage des étiquettes en français) ;
- Service "Concepts" : davantage de concepts affichés ;
- Service "Highlighter" : affichage des étiquettes en français ;
- Service "Actions" : les erreurs de visualisation du graphe des connaissances sont corrigées. 

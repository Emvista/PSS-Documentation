# Version 2022.12
Une nouvelle version (v2) de l'API est disponible. Avec cette version la langue n'est plus obligatoire. Si la langue n'est pas précisée, celle-ci sera automatiquement détectée. 

Requête : 

```JSON
{
	"text": "TEXT"
}
```

Réponse : la langue détectée sera retournée dans la réponse.

```JSON
{
	"message": null,
	"code": 0,
	"language": "fr",
    ...
```

# Version 2022.06
- la langue est obligatoire. La langue doit être passée en paramètre. Les langues disponibles sont : français (fr) et anglais (en).   

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


# Version 2021.06
- la langue par defaut devient l'anglais

# Version 2020.08
- Intéropérabilité des services : possibilité de croiser les résultats des services (par exemple Highlighter pour repérer des noms de produits et Sentiments pour obtenir les opinions détectés sur ces produits.
- Nouveaux services pour l'analyse de l'anglais :  Mots clés, Concepts, Highlighter, Anonymisation, Résumés, Parser.
- Intégration de la coréférence dans le service Parser
- Nouvelle visualisation pour le service Parser
- Documentation des API REST à jour
- Le service Sentiment Expérimental (version 2020.07) est maintenant le service par défaut.

## Notes pour l'anglais

La langue est passée en paramètre. Par défaut c'est le français. Les langues disponibles sont : français (fr) et anglais (en).   

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


# Version 2020.07
- Ajout de la possibilité de passer des paramètres à l'API.
- Ajout du service Sentiments Expérimental.

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

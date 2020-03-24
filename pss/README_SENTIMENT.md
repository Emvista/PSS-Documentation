Sentiment
==

<img src="../images/ic_pss_sentiment.png" alt="drawing" width="80"/>

L'analyse de sentiments (<i>opinion mining</i> ou <i>sentiment analysis</i>) consiste à identifier les sentiments (positif/négatif/neutre) ainsi que les émotions (joie, tristesse, peur, colère, dégoût, surprise) qui sont exprimés dans le texte à analyser. Ce service propose une analyse au niveau des mots et des groupes de mots significatifs. Il est ainsi possible d'identifier des sentiments ou émotions contradictoires au sein d'une même phrase. Par exemple dans "Luc déteste ce produit alors que Marie l'adore." le produit est positif du point de vue de Luc mais négatif du point de vue de Marie.

Query
--
* Method : POST
* Header : Content-Type: application/json
* Poa-Token : TOKEN
* Server : https://pss-api.prevyo.com/pss/api/sentiments
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Paul n'aime pas la très bonne pomme de Marie."
}
```

OUTPUT
--
HTTP Status : 200

La sortie de ce service fournit :

* value (String) : Valeur de l'élément auquel cet attribut est rattaché. La valeur est soit un mot tel qu'il apparaît dans le contexte, soit sa forme lemmatisée (entrée dictionnairique).

* emotions (List) : Liste d'émotions parmi : joie, tristesse, peur, colère, dégoût, surprise.
Dans "Luc déteste envoyer des e-mails", la colère et le dégoût sont des émotions déclenchées.

* sentiment (String) : Sentiment positif, négatif ou neutre exprimé dans le texte.
Dans "Luc envoie une facture", "envoyer" est un prédicat ayant pour arguments "Luc" et "facture".

* point-of-view (String) : Indication sur la personne qui émet une information, un jugement, un sentiment, une émotion, ...
Dans "Luc déteste envoyer des e-mails", la colère et le dégoût sont des émotions portées sur l'envoie d'e-mails, du point de vue de Luc.


Body :

```JSON
{
    "results": [
        {
            "value": {
                "lemma": "ne pas aimer(bonne pomme)"
            },
            "emotions": [
                "sadness"
            ],
            "sentiment": "negative",
            "point-of-view": [
                {
                    "value": "Paul"
                }
            ]
        }
    ]
}
```

TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/sentiments" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Paul n'aime pas la très bonne pomme de Marie."}` 


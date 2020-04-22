Sentiment
==

<img src="../images/ic_pss_sentiment.png" alt="drawing" width="80"/>

L'analyse de sentiments (<i>opinion mining</i> ou <i>sentiment analysis</i>) consiste à identifier les sentiments (positif/négatif/neutre) ainsi que les émotions (joie, tristesse, peur, colère, dégoût, surprise) qui sont exprimés dans le texte à analyser. Ce service propose une analyse au niveau des mots et des groupes de mots significatifs. Il est ainsi possible d'identifier des sentiments ou émotions contradictoires au sein d'une même phrase. Par exemple dans "Luc déteste ce produit alors que Marie l'adore." le produit est positif du point de vue de Luc mais négatif du point de vue de Marie.

Query
--
* Method : POST
* Header : Content-Type: application/json
* Poa-Token : TOKEN
* Server : https://pss-api.prevyo.com/pss/api/v1/sentiments
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Luc déteste envoyer des e-mails alors que Marie adore ça."
}
```

OUTPUT
--
HTTP Status : 200

La sortie de ce service fournit :

* value (String) : Valeur de l'élément auquel cet attribut est rattaché.

* emotions (List) : Liste d'émotions parmi : joie, tristesse, peur, colère, dégoût, surprise.
Dans "Luc déteste envoyer des e-mails", la colère et le dégoût sont des émotions déclenchées.

* polarity (Double) : Sentiment positif, négatif ou neutre exprimé dans le texte.
Dans "Luc envoie une facture", "envoyer" est un prédicat ayant pour arguments "Luc" et "facture".

* pointOfView (String) : Indication sur la personne qui émet une information, un jugement, un sentiment, une émotion, ...
Dans "Luc déteste envoyer des e-mails", la colère et le dégoût sont des émotions portées sur l'envoie d'e-mails, du point de vue de Luc.


Body :

```JSON
{
  "startTime" : 1585730203802,
  "endTime" : 1585730207494,
  "result" : {
    "sentiments" : [ {
      "value" : "détester(envoyer)",
      "emotions" : [ "anger", "disgust" ],
      "polarity" : -1.0,
      "pointOfView" : "Luc"
    }, {
      "value" : "adorer(ça)",
      "emotions" : [ "joy" ],
      "polarity" : 1.0,
      "pointOfView" : "Marie"
    } ]
  }
}
```

TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/v1/sentiments" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Paul n'aime pas la très bonne pomme de Marie."}` 


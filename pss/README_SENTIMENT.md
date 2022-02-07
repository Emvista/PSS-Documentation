Sentiment
==

<img src="../images/ic_pss_sentiment.png" alt="drawing" width="80"/>

L'analyse de sentiments (<i>opinion mining</i> ou <i>sentiment analysis</i>) consiste à identifier les sentiments (positif/négatif/neutre) ainsi que les émotions (joie, tristesse, peur, colère, dégoût, surprise) qui sont exprimés dans le texte à analyser. Ce service propose une analyse au niveau des mots et des groupes de mots significatifs. Il est ainsi possible d'identifier des sentiments ou émotions contradictoires au sein d'une même phrase. Par exemple dans "Luc déteste ce produit alors que Marie l'adore." le produit est positif du point de vue de Luc mais négatif du point de vue de Marie.

Query
--
* Method : POST
* Header : "Content-Type: application/json"
* Header : "Poa-Token : TOKEN"
* Server : https://pss-api.prevyo.com/pss/api/v1/sentiments
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Je déteste les e-mails."
    "parameters": [
        {
            "name": "lowercase",
            "value": "false"
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
  "startTime" : 1597234017539,
  "endTime" : 1597234019129,
  "result" : {
    "opinions" : [ {
      "target" : "e-mail",
      "refTarget" : "0-3",
      "context" : "détester",
      "value" : -1.0,
      "emitter" : "Author"
    } ],
    "emotions" : [ {
      "trigger" : "e-mail",
      "refTrigger" : "0-3",
      "emitter" : "Author",
      "value" : "anger"
    }, {
      "trigger" : "e-mail",
      "refTrigger" : "0-3",
      "emitter" : "Author",
      "value" : "disgust"
    } ]
  }
}
```

La sortie de ce service fournit :

* emitter (String) : Emetteur de l'élément auquel cet attribut est rattaché. 

* emotions (List) : Liste d'émotions parmi : joie, tristesse, peur, colère, dégoût, surprise.
Dans "Luc déteste envoyer des e-mails", la colère et le dégoût sont des émotions déclenchées.

* opinions (List) : Liste des opinions positives et négatives détectées dans le texte.

* polarity (Double) : Sentiment positif, négatif ou neutre exprimé dans le texte.
Dans "Luc envoie une facture", "envoyer" est un prédicat ayant pour arguments "Luc" et "facture".

* pointOfView (String) : Indication sur la personne qui émet une information, un jugement, un sentiment, une émotion, ...
Dans "Luc déteste envoyer des e-mails", la colère et le dégoût sont des émotions portées sur l'envoie d'e-mails, du point de vue de Luc.

* ref[target/trigger] (String) : Indique l'identifiant du terme. Cet identifiant existe dans plusieurs services ce qui permet de croiser des informations provenant de ces services.

* target (String) : Cible sur laquelle porte l'élément auquel il est rattaché (l'opinion par exemple).
 
* trigger (String) : Déclencheur de l'élément auquel il est rattaché (par exemple une émotion).

* value (String) : Valeur de l'élément auquel cet attribut est rattaché.



TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/v1/sentiments" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Je déteste les e-mails."}` 


Emotions
==

<img src="../images/ic_pss_sentiment.png" alt="drawing" width="80"/>

Emotion analysis aims at identifying emotions (joy, sadness, fear, anger, disgust, surprise) 
which are embedded in the text to analyse.
For instance, in "Luc hates this product.", the "product" triggers angry for Luc.
This service provides a very fine-grained way to identify several emotions within a given sentence. 


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
    "text": "Luc déteste les e-mails."
    "parameters": [
        {
			    "name": "lang",
			    "value": "fr"
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
  "startTime" : 1665130587708,
  "endTime" : 1665130587708,
  "code" : 0,
  "message" : null,
  "result" : {
    "emotions" : [ {
      "trigger" : "e-mails",
      "refTrigger" : "0-3",
      "emitter" : "Luc",
      "value" : "anger"
    } ]
  }
}
```

The ouput provides:

* code (Integer): Error code

* emitter (String): Emitter of the emotion.

* endTime (Integer): Temporal indication that corresponds to the end of the analysis.

* message (String): Error message

* refTrigger (String): Indicates the identifier of the term based on the pattern x-y with x the identifier of the sentence and y the identifier of the token.

* startTime (Integer): Temporal indication that corresponds to the beginning of the analysis.

* trigger (String): Thing that triggers an emotion.

* value (String): Value of the emotion (joy, angry, fear, sadness, disgust, surprise).


TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/v1/sentiments" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Paul n'aime pas la très bonne pomme de Marie."}` 


Opinions
==

<img src="../images/ic_pss_sentiment.png" alt="drawing" width="80"/>

Opinion analysis aims at identifying opinions (positive, negative, and neutral) which are embedded in the text 
to analyse. 
This service provides a very fine-grained way to identify several opinions within a given sentence. 
For instance, in "Luc hates this product whereas Marie likes it.", the "product" is negative from Luc's point of view but not from Maries's one.

Query
--
* Method : POST
* Header : "Content-Type: application/json"
* Header : "Poa-Token : TOKEN"
* Server : https://pss-api.prevyo.com/pss/api/v1/opinions
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
  "startTime" : 1665129391467,
  "endTime" : 1665129391467,
  "code" : 0,
  "message" : null,
  "result" : {
    "opinions" : [ {
      "target" : "e-mails",
      "refTarget" : "0-3",
      "context" : null,
      "value" : -1.0,
      "emitter" : "Luc"
    } ],
    "globalScore" : -1.0
  }
}
```


The ouput provides:

* code (Integer): Error code

* context (String) : Indication of the context in which the opinion is detected.

* emitter (String): Emitter of the opinion.

* endTime (Integer): Temporal indication that corresponds to the end of the analysis.

* globalScore (Double): Value of the global opinion (for the whole text): between -1 and 1.

* message (String): Error message

* startTime (Integer): Temporal indication that corresponds to the beginning of the analysis.

* refTarget (String): Indicates the identifier of the term based on the pattern x-y with x the identifier of the sentence and y the identifier of the token.

* target (String): Target of the opinion.

* value (String): Value of the opinion: negative (-1) or positive (1).


TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/v1/opinions" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Paul n'aime pas la très bonne pomme de Marie."}` 


Query
==

<img src="../images/ic_pss_query.png" alt="drawing" width="80"/>

Le service Query prend une question écrite en langage naturel et la transforme en une requête SPARQL pour interroger une base de connaissances.

Query
--
* Method : POST
* Header : "Content-Type: application/json"
* Header : "Poa-Token : TOKEN"
* Server : https://pss-api.prevyo.com/pss/api/query
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Qui a peint La Joconde ?"
}
```

OUTPUT
--
HTTP Status : 200
Body :

```JSON
{
   "startTime":1587481169785,
   "endTime":1587481172935,
   "result":{
      "values":[{
         "value":"PREFIX dc:<http://purl.org/dc/elements/1.1/> PREFIX rdf:<http://www.w3.org/1999/02/22-rdf-syntax-ns#> PREFIX rdfs:<http://www.w3.org/2000/01/rdf-schema#> PREFIX xsd:<http://www.w3.org/2001/XMLSchema#> PREFIX owl:<http://www.w3.org/2002/07/owl#> PREFIX em:<http://emvista.com/>  SELECT  ?qui WHERE { graph<toSparql> { ?event1 rdf:type em:image_impression . ?event1 em:hasTheme em:La_Joconde . ?event1 em:hasAgent ?qui .  } } LIMIT 10",
         "valueToDisplay":"PREFIX dc:<http://purl.org/dc/elements/1.1/> \nPREFIX rdf:<http://www.w3.org/1999/02/22-rdf-syntax-ns#> \nPREFIX rdfs:<http://www.w3.org/2000/01/rdf-schema#> \nPREFIX xsd:<http://www.w3.org/2001/XMLSchema#> \nPREFIX owl:<http://www.w3.org/2002/07/owl#> \nPREFIX em:<http://emvista.com/> \n\n SELECT  ?qui\n WHERE {\n graph<toSparql> { \n\t?event1 rdf:type em:image_impression . \n\t?event1 em:hasTheme em:La_Joconde . \n\t?event1 em:hasAgent ?qui . \n }\n } \n LIMIT 10\n",
         "score":0.75
      }]
   }
}
```

* endTime (Time Stamp Unix) : Indication temporelle de la fin de l'analyse. Time Stamp Unix en millisecondes.

* score (Integer) : Score entre 0 et 1 de l'élément auquel cet attribut est rattaché.

* startTime (Time Stamp Unix) : Indication temporelle du début de l'analyse. Time Stamp Unix en millisecondes.

* value (String) : Valeur de l'élément auquel cet attribut est rattaché.

* values (List) : Liste des requêtes SPARQL générées à partir du texte donné en entrée.

* valuesToDisplay (List) : Liste des requêtes SPARQL générées à partir du texte donné en entrée, contenant les informations de mise en forme du texte (sauts de ligne : \n, tabulations : \t, ...).


TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/query" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Qui a peint La Joconde ?"}` 

Parser
==

<img src="../images/ic_pss_parser.png" alt="drawing" width="80"/>

Le parser retourne une analyse en dépendances syntaxiques.

Query
--
* Method : POST
* Header : Content-Type: application/json
* Poa-Token : TOKEN
* Server : https://pss-api.prevyo.com/pss/api/v1/parser
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Luc aime les pommes. Elles sont bonnes.",
    "parameters": [
        {
            "name": "coreference",
            "value": "true"
        }
    ]
}
```

OUTPUT
--
HTTP Status : 200

* coref (List) : Liste des identifiants de tokens qui coréfèrent avec le token auquel cet attribut est rattaché.

* definite (Boolean) : Indication sur le caractère défini ou indéfini de l'élément auquel cet attribut est rattaché (un token par exemple).

* depRel (String) : Type de la relation de dépendance syntaxique entre deux tokens : sujet, objet, complément, etc. Voir la liste des dépendances gérées.

* end (Integer) : Index de fin (en nombre de caractères).
Dans "Luc envoie une facture proforma", la valeur de end pour le mot "une" est 14.

* endTime (Time Stamp Unix) : Indication temporelle de la fin de l'analyse. Time Stamp Unix en millisecondes.

* form (String) : mot ou locution tel qu'il apparaît dans le contexte (accordé en genre et en nombre par exemple). Par exemple la forme "envoyées" a pour lemme "envoyer". Voir "lemma" dans le glossaire.

* head (String) : Tête syntaxique d'un token.

* id (Integer) : Identifiant de l'élément auquel cet attribut est rattaché.

* lemma (String) : Forme canonique, considérée par convention comme non fléchie, d’un nom, d’un adjectif, d’un verbe, d’un pronom, présentée comme entrée principale, dans un dictionnaire. Par exemple la forme "envoyées" a pour lemme "envoyer". Voir "form" dans le glossaire.

* negation (Boolean : true/false) : Indique si le token, la valeur ou le prédicat considéré est négatif ou affirmatif.
Dans "Luc envoie une facture proforma", l'attribut negation vaut false car la phrase est affirmative.

* person (String) : Indique la première personne ("1"), la deuxième personne ("2") ou la troisième personne ("3"). Par exemple, "vous" est la deuxième personne du pluriel (voir "plural").

* plural (String) : Indication sur le caractère singulier ("false") ou pluriel ("true") de l'élément auquel il est rattaché. 

* pos (String) : Catégorie grammaticale. Liste des catégories grammaticales gérées (pos) :
ADJ : Adjectif, 
ADJPOS : Adjectif possessif, 
ADJDEM : Adjectif démonstratif, 
ADJNUM : Adjectif numéral, 
ADJVPP : Adjectif ou Verbe au participe passé, 
ADJWH : Adjectif interrogatif, 
ADV : Adverbe, 
ADVHW : Adverbe interrogatif, 
AUX : Auxiliaire, 
CC : Conjonction de coordination, 
CS : Conjonction de subordination, 
CL : Clitique , 
CLS : Clitique sujet, 
CLO : Clitique object, 
CLR : Clitique réflexif, 
DET : Déterminant, 
DETI : Déterminant indéfini, 
DETD : Déterminant défini, 
DETWH : Déterminant interrogatif, 
I : Interjection, 
NC : Nom commmun, 
NPP : Nom propre, 
P : Préposition, 
PD : Contraction d'une préposition et d'un déterminant, 
PONCT : Ponctuation, 
PRO : Pronom, 
PROREL : Pronom relatif, 
PROWH : Pronom interrogatif, 
SEMAUX : Semi-Auxiliaire, 
V : Verbe, 
VIMP : Verbe conjugué à l'impératif, 
VINF : Verbe à l'infinitif, 
VPP : Verbe conjugué au participe passé, 
VPR : Verbe conjugué au participe présent, 
VS : Verbe au subjonctif

* pronominal (Boolean) : Indique si le verbe est pronominal.

* result (List) : Liste des résultats retournés par le service.

* sentences (List) : Phrases analysées.

* start (Integer) : Index de début (en nombre de caractères).
Dans "Luc envoie une facture proforma", la valeur de end pour le mot "une" est 11.

* startTime (Time Stamp Unix) : Indication temporelle du début de l'analyse. Time Stamp Unix en millisecondes.

* tense (String) : Indique le temps utilisé ("past", "present", ou "future").

* tokens (List) : Ensemble de tokens, c'est-à-dire de mots ou locutions.

* type : Type de la phrase analysée : declarative, exclamative, interrogative ou imperative. 

* verbalForm (String) : Forme verbale : active ou passive.

Body :

```JSON
{
  "startTime" : 1597236091960,
  "endTime" : 1597236091961,
  "result" : {
    "sentences" : [ {
      "id" : 0,
      "type" : "declarative",
      "tokens" : [ {
        "id" : 0,
        "form" : "Luc",
        "lemma" : "Luc",
        "depRel" : "suj",
        "head" : 1,
        "pos" : "NPP",
        "verbalform" : "",
        "start" : 0,
        "end" : 2,
        "negation" : false,
        "definite" : true,
        "pronominal" : false,
        "person" : "",
        "plural" : false,
        "tense" : null,
        "coref" : [ ]
      }, {
        "id" : 1,
        "form" : "aime",
        "lemma" : "aimer",
        "depRel" : "root",
        "head" : -1,
        "pos" : "V",
        "verbalform" : "active",
        "start" : 4,
        "end" : 7,
        "negation" : false,
        "definite" : false,
        "pronominal" : false,
        "person" : "1",
        "plural" : false,
        "tense" : "present",
        "coref" : [ ]
      }, {
        "id" : 2,
        "form" : "les",
        "lemma" : "le",
        "depRel" : "det",
        "head" : 3,
        "pos" : "DETD",
        "verbalform" : "",
        "start" : 9,
        "end" : 11,
        "negation" : false,
        "definite" : true,
        "pronominal" : false,
        "person" : "",
        "plural" : true,
        "tense" : null,
        "coref" : [ ]
      }, {
        "id" : 3,
        "form" : "pommes",
        "lemma" : "pomme",
        "depRel" : "obj",
        "head" : 1,
        "pos" : "NC",
        "verbalform" : "",
        "start" : 13,
        "end" : 18,
        "negation" : false,
        "definite" : true,
        "pronominal" : false,
        "person" : "",
        "plural" : true,
        "tense" : null,
        "coref" : [ ]
      }, {
        "id" : 4,
        "form" : ".",
        "lemma" : ".",
        "depRel" : "ponct",
        "head" : 1,
        "pos" : "PONCT",
        "verbalform" : "",
        "start" : 19,
        "end" : 19,
        "negation" : false,
        "definite" : false,
        "pronominal" : false,
        "person" : "",
        "plural" : false,
        "tense" : null,
        "coref" : [ ]
      } ]
    }, {
      "id" : 1,
      "type" : "declarative",
      "tokens" : [ {
        "id" : 0,
        "form" : "Elles",
        "lemma" : "elles",
        "depRel" : "suj",
        "head" : 1,
        "pos" : "CLS",
        "verbalform" : "",
        "start" : 21,
        "end" : 25,
        "negation" : false,
        "definite" : false,
        "pronominal" : false,
        "person" : "3",
        "plural" : true,
        "tense" : null,
        "coref" : [ "0-3" ]
      }, {
        "id" : 1,
        "form" : "sont",
        "lemma" : "être",
        "depRel" : "root",
        "head" : -1,
        "pos" : "V",
        "verbalform" : "active",
        "start" : 27,
        "end" : 30,
        "negation" : false,
        "definite" : false,
        "pronominal" : false,
        "person" : "3",
        "plural" : true,
        "tense" : "present",
        "coref" : [ ]
      }, {
        "id" : 2,
        "form" : "bonnes",
        "lemma" : "bon",
        "depRel" : "ats",
        "head" : 1,
        "pos" : "ADJ",
        "verbalform" : "",
        "start" : 32,
        "end" : 37,
        "negation" : false,
        "definite" : false,
        "pronominal" : false,
        "person" : "",
        "plural" : true,
        "tense" : null,
        "coref" : [ ]
      }, {
        "id" : 3,
        "form" : ".",
        "lemma" : ".",
        "depRel" : "ponct",
        "head" : 1,
        "pos" : "PONCT",
        "verbalform" : "",
        "start" : 38,
        "end" : 38,
        "negation" : false,
        "definite" : false,
        "pronominal" : false,
        "person" : "",
        "plural" : false,
        "tense" : null,
        "coref" : [ ]
      } ]
    } ]
  }
}
```

TEST
--

`curl -X POST "https://pss-api.prevyo.com/pss/api/v1/parser" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Marie enverra la facture demain à Pierre de chez Emvista."}` 

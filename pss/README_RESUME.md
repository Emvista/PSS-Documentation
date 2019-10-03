Résumés
==

<img src="../images/ic_pss_resume.png" alt="drawing" width="80"/>

Le générateur de résumés crée une synthèse du texte, dont le niveau d'abstraction est paramétrable.

Query
--
* Method : GET
* Header : Content-Type: application/json
* Poa-Token : TOKEN
* Server : https://api-pss.prevyo.com/pss/api/summarizer
* Body : {"text": "TEXT"}

INPUT
--

```JSON
{
    "text": "Emvista est une société créée à Montpellier en février 2018. Emvista développe des briques logicielles pour comprendre le langage naturel. Les technologies d’intelligence artificielle mises en œuvre sont fondées à la fois sur du machine learning (système d'apprentissage) et sur des ontologies. À partir de ces briques technologiques, Emvista propose Prevyo, un assistant virtuel intelligent de gestion d’e-mails."
}
```

OUTPUT
--
HTTP Status : 200

Body :

```JSON
{
  "0": {
    "1": "Emvista est une société créée à Montpellier en février 2018. ",
    "2": "Emvista est une société créée à Montpellier en février 2018. ",
    "3": "Emvista est une société créée à Montpellier en février 2018. ",
    "4": "Emvista est une société créée à Montpellier en février 2018. ",
    "5": "Emvista est une société créée à Montpellier en février 2018. ",
    "6": "Emvista est une société créée à Montpellier en février 2018. ",
    "7": "Emvista est une société créée à Montpellier en février 2018. ",
    "8": "Emvista est une société créée à Montpellier. ",
    "9": "Emvista est une société. ",
    "10": "Emvista est une société. "
  },
  "1": {
    "1": "Emvista développe des briques logicielles pour comprendre le langage naturel. ",
    "2": "Emvista développe des briques logicielles pour comprendre le langage naturel. ",
    "3": "Emvista développe des briques logicielles pour comprendre le langage naturel. ",
    "4": "Emvista développe des briques logicielles pour comprendre le langage naturel. ",
    "5": "Emvista développe des briques logicielles pour comprendre le langage naturel. ",
    "6": "Emvista développe des briques logicielles pour comprendre le langage naturel. ",
    "7": "Emvista développe des briques pour comprendre le langage. ",
    "8": "Emvista développe des briques pour comprendre le langage. ",
    "9": "Emvista développe des briques. ",
    "10": "Emvista développe des briques. "
  },
  "2": {
    "1": "Les technologies d'intelligence artificielle mises en œuvre sont fondées à la fois sur du machine learning et sur des ontologies. ",
    "2": "Les technologies d'intelligence artificielle mises en œuvre sont fondées sur du machine learning et sur des ontologies. ",
    "3": "Les technologies d'intelligence artificielle mises en œuvre sont fondées sur du machine learning et sur des ontologies. ",
    "4": "Les technologies d'intelligence artificielle mises en œuvre sont fondées sur du machine learning et sur des ontologies. ",
    "5": "Les technologies d'intelligence artificielle mises en œuvre sont fondées sur du machine learning et sur des ontologies. ",
    "6": "Les technologies d'intelligence artificielle mises en œuvre sont fondées sur du machine learning et sur des ontologies. ",
    "7": "Les technologies d'intelligence artificielle mises en œuvre sont fondées sur du machine learning et sur des ontologies. ",
    "8": "Les technologies d'intelligence artificielle mises en œuvre sont fondées sur du machine learning et. ",
    "9": "Les technologies d'intelligence artificielle mises en œuvre sont fondées sur du machine learning et. ",
    "10": "Les technologies d'intelligence artificielle mises en œuvre sont fondées sur du machine learning et. "
  },
  "3": {
    "1": "À partir de ces briques technologiques, Emvista propose Prevyo, un assistant virtuel intelligent de gestion d'e-mails. ",
    "2": "À partir de ces briques technologiques, Emvista propose Prevyo, un assistant virtuel intelligent de gestion d'e-mails. ",
    "3": "À partir de ces briques technologiques, Emvista propose Prevyo. ",
    "4": "À partir de ces briques technologiques, Emvista propose Prevyo. ",
    "5": "À partir de ces briques technologiques, Emvista propose Prevyo. ",
    "6": "À partir de ces briques technologiques, Emvista propose Prevyo. ",
    "7": "À partir de briques, Emvista propose Prevyo. ",
    "8": "À partir de briques, Emvista propose Prevyo. ",
    "9": "",
    "10": ""
  }
}```

TEST
--

`curl -X GET "https://api-pss.prevyo.com/pss/api/summarizer" -H "accept: application/json" -H "Content-Type: application/json" -H "Poa-Token: XXXXXXXX" -d {"text": "Emvista est une société créée à Montpellier en février 2018. Emvista développe des briques logicielles pour comprendre le langage naturel. Les technologies d’intelligence artificielle mises en œuvre sont fondées à la fois sur du machine learning (système d'apprentissage) et sur des ontologies. À partir de ces briques technologiques, Emvista propose Prevyo, un assistant virtuel intelligent de gestion d’e-mails."}` 


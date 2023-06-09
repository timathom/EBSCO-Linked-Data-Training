---
author: [EBSCO Information Services, Timothy A. Thompson ⍝ @timathom ⍝ @timathom@indieweb.social]
---

# RDF

-   How is RDF actually expressed?

-   We have many format options, which are called **serializations**.

-   One of the most common is called **[JSON-LD](https://www.w3.org/TR/json-ld11/)**.


**Previous topic:**[RDF](../../day_1/lesson_1/rdf_5.md)

**Next topic:**[Learning Turtle](../../day_1/lesson_2/learning_turtle.md)

## JSON-LD

Here is the JSON-LD that is embedded in the HTML page representing the dictionary entry for dato in the *Diccionario de la lengua española*:

```
[
  {"@context": "http://schema.org/"},
  {
    "@type": [
      "DefinedTermSet",
      "Book"
    ],
    "@id": "https://dle.rae.es/",
    "name": "Diccionario de la lengua española RAE - ASALE",
    "image": "https://dle.rae.es/app/doc/es/img/dle.jpg",
    "description": "Versión electrónica 23.6 del «Diccionario de la lengua española», obra lexicográfica académica pozr excelencia."
  },
  {
    "@type": "DefinedTerm",
    "@id": "https://dle.rae.es/dato",
    "name": "dato",
    "description": "1. m. Información sobre algo concreto que permite su conocimiento exacto o sirve para deducir las consecuencias derivadas de un hecho. A este problema le faltan datos numéricos.",
    "inDefinedTermSet": "https://dle.rae.es/"
  }
]
```

## JSON-LD Syntax

In the code, we can note the following:

-   The context is declared as `{"@context": "[http://schema.org/](http://schema.org/)"}`, which means that the terms are taken from the Schema.org vocabulary.

-   The resource [https://dle.rae.es/dato](https://dle.rae.es/dato) is declared to be of the type [http://schema.org/DefinedTerm](http://schema.org/DefinedTerm).

-   It is related to [https://dle.rae.es/](https://dle.rae.es/), which is a [http://schema.org/DefiniedTermSet](http://schema.org/DefiniedTermSet).



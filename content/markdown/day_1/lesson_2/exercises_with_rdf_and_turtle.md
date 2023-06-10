---
author: [EBSCO Information Services, Timothy A. Thompson ⍝ @timathom @timathom@indieweb.social]
---

# Exercises with RDF and Turtle

-   This set of 10 exercises will sharpen your skills in working with RDF and the Turtle format.
-   Some exercises ask you to review a vocabulary such as [Schema.org](https://schema.org/), but most of them are hands-on and require you to edit a set of triples.
-   To validate your work, use an RDF editor such as the [Sketch editor](https://sketch.zazuko.com/), by Zazuko.

**Previous topic:**[Learning Turtle](../../day_1/lesson_2/learning_turtle.md)

**Next topic:**[What Is an Ontology?](../../day_1/lesson_3/what_is_an_ontology.md)

## Exercise 1

```language-ttl


<https://metadatafram.es/data/person1> <http://xmlns.com/foaf/0.1/name> "Alicia" .
<https://metadatafram.es/data/person2> <http://xmlns.com/foaf/0.1/name> "Roberto" .

                
```

1.  Add a new triple with a person3 and give them a name.


**Related information**  


[RDF Sketch editor](https://sketch.zazuko.com/)

## Exercise 2

```language-ttl


<https://metadatafram.es/data/person1> <http://xmlns.com/foaf/0.1/name> "Alice" .
<https://metadatafram.es/data/person1> <http://xmlns.com/foaf/0.1/knows> <https://metadatafram.es/data/person2> .

                
```

1.  Rewrite these triples using the feature of Turtle that allows us to avoid repeating a subject.


**Related information**  


[RDF Sketch editor](https://sketch.zazuko.com/)

## Exercise 3

```language-ttl


<https://metadatafram.es/data/person1> <http://xmlns.com/foaf/0.1/name> "Alicia" ;
<http://xmlns.com/foaf/0.1/knows> <https://metadatafram.es/data/person2> .
                    
                
```

1.  Now shorten the URIs by declaring prefixes at the top and using the qualified form.


**Related information**  


[RDF Sketch editor](https://sketch.zazuko.com/)

## Exercise 4

|Subject \(Domain\)|Property|Object \(Range\)|
|------------------|--------|----------------|
| | | |
| | | |
| | | |
| | | |
| | | |

1.  Explore the [Schema.org](https://schema.org/) vocabulary and see what types of entities and properties are defined there.

2.  List five possible "triple templates" in the table above, using classes that can be related to each other as subject and object.


**Related information**  


[RDF Sketch editor](https://sketch.zazuko.com/)

## Exercise 5

```language-ttl


@prefix schema: <http://schema.org/> .

<> a schema: ;
schema:name "" ;
schema:author <> .

                
```

1.  Use the `rdf:type` predicate or the special `a` shortcut to say what kind of thing the subject of these statements is.

2.  Choose a term from [Schema.org](https://schema.org/).


**Related information**  


[RDF Sketch editor](https://sketch.zazuko.com/)

## Exercise 6

|Subject \(Domain\)|Property|Object \(Range\)|
|------------------|--------|----------------|
| | | |
| | | |
| | | |
| | | |
| | | |

1.  Explore the vocabulary specification for [FOAF](http://xmlns.com/foaf/0.1/) \(Friend of a Friend\) and see what types of entities and properties are defined there.

2.  List five possible "triple templates" in the table above, using classes that can be related to each other as subject and object.


## Exercise 7

```language-ttl


@prefix foaf: <http://xmlns.com/foaf/0.1/> .
                    
<> foaf:firstName "" ;
foaf:lastName "" ;
foaf:knows <> .
                   
                
```

1.  Using FOAF, choose some terms to use to begin creating a profile for yourself.

2.  How many statements can you add?


**Related information**  


[RDF Sketch editor](https://sketch.zazuko.com/)

## Exercise 8

```language-ttl


@prefix dcterms: <https://purl.org/dc/terms/> .

<https://metadatafram.es/data/document1> dcterms:title "An Introduction to RDF" ;
dcterms:creator <> ;
dcterms:date "" .

                
```

1.  Explore the [Dublin Core Terms](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/) vocabulary specification.

2.  Fill in the missing values and add further statements.


**Related information**  


[RDF Sketch editor](https://sketch.zazuko.com/)

## Exercise 9

```language-ttl


@base <urn:name/> .
                    
<alicia> a <Person> ; <age> 77 .
                    
                
```

1.  Are these statements valid Turtle? Why or why not?


**Related information**  


[RDF Sketch editor](https://sketch.zazuko.com/)

## Exercise 10

```language-ttl


@prefix bf: <http://id.loc.gov/ontologies/bibframe/> .
@prefix dcterms: <https://purl.org/dc/terms/> .
@prefix schema: <http://schema.org/> .

<> a schema:Book ;
bf:title [ 
  a bf:Title ; bf:mainTitle "" ;
  dcterms:creator [] 
] .

                
```

1.  Where are the blank nodes in these statements?

2.  Rewrite the blank nodes using alternative syntax and fill in the statements.


**Related information**  


[RDF Sketch editor](https://sketch.zazuko.com/)


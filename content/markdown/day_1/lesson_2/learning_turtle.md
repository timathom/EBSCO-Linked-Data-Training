---
author: [EBSCO Information Services, Timothy A. Thompson ⍝ @timathom @timathom@indieweb.social]
---

# Learning Turtle

-   Although JSON-LD is a common format for exchanging linked data on the web, one of the best ways to learn, write, and read RDF is through the Turtle serialization \([Terse RDF Triple Language](https://www.w3.org/TR/rdf12-turtle/), or TTL\).

-   A subset of Turtle, called [N-Triples](https://www.w3.org/TR/rdf12-n-triples/), is simply lines of triples \(which can be hard to read\).


**Previous topic:**[RDF](../../day_1/lesson_1/rdf_6.md)

**Next topic:**[Exercises with RDF and Turtle](../../day_1/lesson_2/exercises_with_rdf_and_turtle.md)

## Prefixes

When we're writing RDF in Turtle, one of the first things we might want to do is declare some prefixes and namespaces so that we don't have to type as much.

```
@prefix bf: <http://id.loc.gov/ontologies/bibframe/> .
@prefix dcterms: <http://purl.org/dc/terms/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .

<https://metadatafram.es/alicia> foaf:name "Alicia" .
```

### Base

-   In addition to declaring prefixes, we can also use the `@base` keyword to declare the base URI for a Turtle file. Any relative URIs in our data will then be resolved against the base.
-   Instead of writing `<https://metadatafram.es/alicia>`, we can declare a base URI and then use relative URIs.

```
@base <https://metadatafram.es/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
                
<alicia> foaf:name "Alicia" .
```

## Semicolons

We can repeat statements about the same subject using semicolons.

```
@base <https://metadatafram.es/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .

<alicia> foaf:name "Alicia" ; foaf:nick "Al" .
```

**Note:** Notice the spacing around punctuation. \(Spacing is not required, but it makes the syntax easier to read.\)

## Commas

We can repeat objects for the same predicate using commas.

```
@base <https://metadatafram.es/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .

<alicia> foaf:name "Alicia" , "Al" .
```

## Typed Literals

-   When the object of a statement is a **literal** \(not a resource we can may statements about\), it can take a data type.
-   RDF uses the data types defined for XML, typically declared with the prefix `xsd`.
-   Data types are indicated with double carets, followed by the type name.

```
@base <https://metadatafram.es/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#date> .

<alicia> foaf:name "Alicia" ; <birthDate> "1946"^^xsd:date .
```

## Blank Nodes

In RDF, we sometimes need to say something about a resource whose identity we don't know \(or care\) about. These are called **blank nodes**.

```
@base <https://metadatafram.es/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#date> .

<alicia> foaf:name "Alicia" ; 
foaf:knows [ a foaf:Person ] ;
foaf:knows _:b1 .

_:b1 a foaf:Person .
```

**Note:** The example shows two different ways to encode a blank node: one with an identifier \(`_:b1`\) and one with square brackets. Blank node identifiers are not guaranteed to be unique across different Turtle files.

## Lists

We can also define lists, which can be [tricky in RDF](https://s.zazuko.com/zj3Rhn), but are easy to write in Turtle.

```
@base <https://metadatafram.es/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#date> .

<alicia> foaf:name "Alicia" ; 
foaf:knows (_:b1 _:b2 _:b3) .
```

## Type

-   Finally, Turtle defines a shortcut expression for the built-in RDF predicate `rdf:type`.
-   In Turtle, we can use the word `a` instead of `rdf:type`.
-   That way, it reads almost like an English sentence: `<alicia> a foaf:Person`.

**Note:** `rdf:type` is an important predicate because it allows us to say what kind of thing an entity is \(what **class** of things it belongs to\).


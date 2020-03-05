# SPARQL

* SELECT
* CONSTRUCT
* ASK
* DESCRIBE

Je pod ním HTTP.

```SPARQL
SELECT ?title
WHERE
{
	<http://example.org/book/book1>
	<http://purl.org/dc/elements/1.1/title>
	?title
}
```

Testy:

* *isURI*
* *isBlank*
* *isLiteral*
* *bound*

```SPARQL
PREFIX info: <http://somewhere/peopleInfo#>

SELECT ?resource
WHERE {
	?resource info:age ? age .
	FILTER (?age >= 24)
}
```

```SPARQL
PREFIX vcard: <http://www.w3.org/2001/vcard-rdf/3.0#>

SELECT ?g
WHERE {
	?y vcard:Given ?g .
	FILTER regex(?g,"r","i") # "i" je flag case Insensitive
} ORDER BY DESC(?g)
```

```SPARQL
PREFIX info: <http://somewhere/peopleInfo#>
PREFIX vcard: <http://www.w3.org/2001/vcard-rdf/3.0#>

SELECT ?name ?age
WHERE {
	?person vcard:FN ?name .
	OPTIONAL {?person info:age ?age} # volitelné hodnoty
}
```

```SPARQL
PREFIX foaf: <http://xmlns.com/foaf/0.1>
PREFIX vcard: <http://www.w3.org/2001/vcard-rdf/3.0#>

SELECT DISTINCT ?name
WHERE {
    {[] foaf:name ?name} UNION {[] vcard:FN ?name} # [] je blank node
} 
ORDER BY ?name
LIMIT 5
OFFSET 10
```

```SPARQL
PREFIX foaf: <http://xmlns.com/foaf/0.1>
PREFIX vcard: <http://www.w3.org/2001/vcard-rdf/3.0#>

CONSTRUCT {
    <http://example.com/person#Alice> vcard:name ?name
} WHERE {
    <http://example.com/person#Alice> foaf:name ?name
}
```




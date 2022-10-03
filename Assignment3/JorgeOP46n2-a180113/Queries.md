# SPARQL queries

## 1-. Get all the properties that can be applied to instances of the Politician class
    SELECT DISTINCT ?p WHERE {                              #select only the properties
    ?s rdf:type <http://dbpedia.org/ontology/Politician>.   #get all instances of politicias
    ?s ?p ?o                                                #get all statements in which a politician is a subject
    }

## 2-. Get all the properties, except rdf:type, that can be applied to instances of the Politician class
    SELECT DISTINCT ?p WHERE {                              #select only the properties
    ?s rdf:type <http://dbpedia.org/ontology/Politician>.   #get all instances of politicias
    ?s ?p ?o.                                               #get all statements in which a politician is a subject
    FILTER(?p!=rdf:type)                                    #filtering out the rdf:type property
    }

## 3-. Which different values exist for the properties, except for rdf:type, applicable to the instances of Politician?
    SELECT DISTINCT ?o WHERE {                              #select only the values
    ?s rdf:type <http://dbpedia.org/ontology/Politician>.   #get all instances of politicias
    ?s ?p ?o.                                               #get all statements in which a politician is a subject
    FILTER(?p!=rdf:type)
    }

## 4-. For each of these applicable properties, except for rdf:type, which different values do they take globally for all those instances?
    SELECT DISTINCT ?p ?o WHERE {                           #select the properties and the values
    ?s rdf:type <http://dbpedia.org/ontology/Politician>.   #get all instances of politicias
    ?s ?p ?o.                                               # get all statements in which a politician is a subject
    FILTER(?p!=rdf:type)                                    #filtering out the rdf:type property
    }

## 5-. For each of these applicable properties, except for rdf:type, how many distinct values do they take globally for all those instances?
    SELECT DISTINCT ?p COUNT(?o) WHERE {                    #select the properties and the counts of their objects
    ?s rdf:type <http://dbpedia.org/ontology/Politician>.    #get all instances of politicias
    ?s ?p ?o.                                                #get all statements in which a politician is a subject
    FILTER(?p!=rdf:type)                                    #filtering out the rdf:type property
    }


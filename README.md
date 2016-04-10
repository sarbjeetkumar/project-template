# Irish Constituencies Neo4j Database
###### Sarabjeet Kumar , G00305450

## Introduction
<br>
	<img height = 500 src ="https://github.com/sarbjeetkumar/project-template/blob/master/neo4j.JPG"/>
<br>
This project is about all consituencies of IRELAND and their members in the database . How they are stored and retrived from database .

## Database
Explain how you created your database, and how information is represented in it.
To create this Database all the information is retrieved from the Wikipedia , The nature of datbase is each and every node is created sepretly and each and every single node represent either a county or a members , so there is 40 consituencies is in Ireland so there is all together 40 nodes in the database which represents all the consituencies of ireland.
 
##Querie Shows how to create the node in database which represents a consituency Carlow–Kilkenny.

``` cypher 
CREATE ( CarlowKilkenny : constituencies {Name : "Carlow–Kilkenny" })

```
Above querie shows how each and every single node is created in database to create a nodes for consituensy , The very first word says "CREATE" Means tells in cypher to neo4j to create something and and next word is "CarlowKilkenny" I added this word "CarlowKilkenny" for my own purpose but we can create a node without this word as well and third word which is ": constituencies " : means = in cypher and constituencies is label which will represnets all the nodes who represents the constituencies and Naeme is actual name which show on the node and its a property of that node as well.

## Queries
Summarise your three queries here.
Then explain them one by one in the following sections.

#### Query one title
This query retreives the Bacon number of an actor...
```cypher
MATCH
	(Bacon)
RETURN
	Bacon;
```

#### Query two title
This query retreives the Bacon number of an actor...
```cypher
MATCH
	(Bacon)
RETURN
	Bacon;
```

#### Query three title
This query retreives the Bacon number of an actor...
```cypher
MATCH
	(Bacon)
RETURN
	Bacon;
```

## References
1. [Neo4J website](http://neo4j.com/), the website of the Neo4j database.
2. http://neo4j.com/developer/cypher/
3. https://github.com/graph-theory
4. https://github.com/graph-theory/problems-4/blob/master/problems.pdf


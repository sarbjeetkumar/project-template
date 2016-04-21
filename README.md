# Irish Constituencies Neo4j Database
###### Sarabjeet Kumar , G00305450

## Introduction
<br>
	<img height = 500 src ="https://github.com/sarbjeetkumar/project-template/blob/master/neo4j.JPG"/>
<br>
This project is about all consituencies of IRELAND and their members in the database . How they are stored and retrived from database .

## Database

To create this Database all the information is retrieved from the Wikipedia , The nature of datbase is each and every node is created sepretly and each and every single node represents either a county or a members , so there is 40 consituencies is in Ireland so there is all together 40 nodes in the database which represents all the consituencies of ireland.
 
##Querie Shows how to create the node in database which represents a consituency Carlow–Kilkenny.

``` cypher 
CREATE ( CarlowKilkenny : constituencies {Name : "Carlow–Kilkenny" })

```
Above querie shows how each and every single node is created in database to create a nodes for consituensy , The very first word says "CREATE" Means tells in cypher to neo4j to create something and and next word is "CarlowKilkenny" I added this word "CarlowKilkenny" for my own purpose but we can create a node without this word as well and third word which is ": constituencies " : means = in cypher and constituencies is label which will represnets all the nodes who represents the constituencies and Name is actual name which show on the node and its a property of that node as well.

##Querie Shows how to create the node in database which represents a each member of Carlow–Kilkenny.

``` 
CREATE 	(CarlowKillkenny1 : candidate_CK { Name : "John McGuiness", Gender : "Male" , Age : 40 , 

PartyName : "FiannaFail",	TotalVotes : 11903	,County : "Carlow–Kilkenny"	,Win : "Yes"	})


```
Above querie shows how to create a node in database which represents the member of county "Carlow–Kilkenny" and it has some property's as well. It starts "CRATE" words tell neo4j in cypher to create a node and give it a label called candidate_CK and inside a node name called John McGuiness which was the member in that county as so on with all the members of all county's.


##Querie Shows how to create a relationship between the given candidate with the given county .

```
MATCH (u:constituencies {Name:"Carlow–Kilkenny"}), (r:candidate_CK) 

CREATE (u)-[:Ran_IN_Election]->(r)


```

Above query shows how to create a relationship between constituency name Carlow–Kilkenny with the all the candidate of that constituency, Very first we have to match the nodes together in datbase , For eg in the constituencies match a node name called Carlow–Kilkenny and match a another node in that candidate_CK and make a relationship between them and give a relationship name called a Ran_IN_Election.


## Queries


#### Show database

 
```cypher
MATCH
	(n)
RETURN
	n;
```
This query Will Shows whats actually exixts in database and how is the structure of database. In terms of relationship with all of the members of the given county .




###This query will shows a user that how many nodes are in the databse It will count a total number of nodes .

```
	start n=node(*)
	
	match (n)
	
	return count(n)
```
#### Get the number of female members were there in county kerry 

```cypher
	MATCH(a:constituencies{Name : "Kerry"})-[:Ran_IN_Election]-> 
	
	(b:candidateKerry)
	
	WHERE b.Gender = "Female"
	
	RETURN b.Name , b.Age;
```

Query that displays all the female members of the county kerry who run in election With there names and age .



#### Get the Age 
This query retreives  a oldest man name and age who run in election in county clare 
```cypher
	MATCH(a:constituencies{Name : "Clare"})-[:Ran_IN_Election]-> 
	
	(b:candidate_Clare)
	
	WHERE b.Age >= 70
	
	RETURN b.Name , b.Age;
```


#### Get the Age 
This query retreives  a oldest man name and age who run in election in county clare 
```cypher
	MATCH(a:constituencies{Name : "Clare"})-[:Ran_IN_Election]-> 
	
	(b:candidate_Clare)
	
	WHERE b.Age >= 70
	
	RETURN b.Name , b.Age;
```


###This query willFind the list of people who won the election for more than 12000 votes , Their Names , Total Number of votes they get And Was male or female and count Them how many are they.

```
	MATCH(a:constituencies{Name : "Clare"})-[:Ran_IN_Election]-> 
	
	(b:candidate_Clare)
	
	WHERE b.TotalVotes >=12000
	
	RETURN b.Name , b.TotalVotes, b.Gender ,b.Age, Count(*);

```


## References
1. [Neo4J website](http://neo4j.com/), the website of the Neo4j database.
2. http://neo4j.com/developer/cypher/
3. https://github.com/graph-theory
4. https://github.com/graph-theory/problems-4/blob/master/problems.pdf
5. https://en.wikipedia.org/wiki/Parliamentary_constituencies_in_the_Republic_of_Ireland


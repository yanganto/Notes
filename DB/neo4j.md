Neo4J slide may upload to SlideShare

eric@eric.lv


---

# SQL

- ER-Model
- MySQL, MS-SQL, Oracle, Allegro, Titan

---

# NoSQL

> Not Only SQL 

- File base: Accumulo, HBase
- Key-Value: Cassandra, Couchbase, MongoDB
- row-main: Dynamo, Redis
- graphic-db: Neo4J, Allegro, Titan

---

# Why NoSQL

- highly adjusting structure
- highly scalability
- suitable for big data
- high availability
- HA

---

# Graphic database

- no schema
- data type
	- node 
	- relationship
- using in Social network and big protal

---

# Neo4J

- JAVA base 
- Data type: Node, Label, Property, Relationship
- Cypher query language (CQL)
- already use in bussiness and science environment 
- use enterprise version 
	- HA
	- query debug
	- 18k US dollar per node


- String need to be "", will be UTF-8
- thus, can use query with chinese

---

# Design database

- use Xmind is OK
- ralation has property

- application
	- cheat detation

---

# neo4j server
```
# systemctl start neo4j
```
- allow remote (modify the config file)
# dbms.connector.http.address=0.0.0.0:7474


---

# neo4j Console

[Console](http://console.neo4j.org) 
[Sendbox](https://neo4j.con/sendbox/) 

---

# Cypher

- Basic query
	- Match, Create, Where, Return 

```
MATCH (user)-[:BIRTH_PLACE]->(country)
RETURN user, country;
```
just like ASCII Art 

(user)-[:BIRTH_PLACE]->(country)

---

# Create

```
CREATE (n:Employee {Name: "Eric", Surname: "Lee", Gender: "M"});
```
> add employee with 3 props 
> n is variable

** props are case sensitive **
---

# Query

```
MATCH (n:Employee) RETURN n; 
MATCH (n:Employee) RETURN n LIMIT 100;
MATCH (n:Employee) RETURN n.Gender;
```

### Parameters

- ORDER BY
	- DESC
- DISTINCT
- COUNT

```
MATCH (s:Employee) RETURN DISTINCT (s.name); 
MATCH (s:Employee) RETURN COUNT(s); 
```

---

# WHERE

```
MATCH (n:Employee) WHERE n.Age > 20 RETURN n;
```

---

# CREATE relationship
```
CREATE (e:Employee {Name: "Eric"}}
```

### With Existing Nodes
```
match (n:Employee {Name:"Eric"}), (s:Skill {Name: "Neo4j") CREATE UNIQUE (n)-[:KNOWS]->(s);
```

---

# Query relationship

---

# Frequently Questions

- Multi-Label? Yes
- Define porp in relationship? Yes
- can node contain node? No
- ralarion can be bi-way? No, but can reverse query
- multi-platform? Already open source.

---

# Indexing

CREATE INDEX ON

---

# Avoid repeadting Nodes

CREATE CONSTRAINT ON (s:S)

---

# DELETE

 Only node with no raltaion can be deleted 

### Delete relation

### Delete all

### Delete node

---

# Useage of API

- python
	- neo4j-driver (PYPI)

- nodeJS
	- neo4j-driver (npm)

- .Net, JAVA

### 3 party API
- Perl, Ruby, PHP(composer), R(CRAN)

---

# Import from CSV file

** Set constrain to avoid problem **
** avoid bad data **

- csv file set to the import folder
- or set up with absolute path
- or remote cross site 

---

# Enterprise Tool

### SHELL
neo4j-shell -file xxx.cql

### DUMP
neofj-backup



---

# Exam

- 60 min, 80 test, multi/single chiose
- score 80 
- can reexame
- free
- enterprise needed, HA is important

- Meaning, Neo4J basic
- Cypher, create and query is important 
- Data construction
- Development role
- HA, enterprise avaiable and scalbility

---

# Conclusion

- Neo4j has data visualization 3 party (not free), can use D3, google visulization

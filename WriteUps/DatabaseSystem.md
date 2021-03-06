## Database System

- Managing Information
  - Physical Data Dependency:  the structure of the data is embedded inside the computer program itself.
  - Meta data: information about data, includes name type size of data field. 
    - To achieve "physical data independency", the program must first read meta data to find out the format/structure then access actual data accordingly 	
  - Logical Data Independence: the ability to present the stored information in different ways to different users. 
- ER model: Entity-Relation Model
  - model: a representation of portion/part of the real world
    - High level: this type of model omits a lot of information, low level: stores lots of detail, medium level: moderate amount of information
    - Entity-Relation Model is a high-level model
  - Entity: an object in the real world
  - Attribute: 
    - Types: simple, compound, multivalue
    - Special attribute: derived, key attributes
    - NULL: the attribute is not available or applicable, comparing two NULL values the result is false.
- Relational Model: 
  - a medium level model with moderate amount of details on how the data will be stored.
  - Keys:
    - super key: a set of attributes in a relation R such that no 2 different tuples will have the same values for the set of attributes
    - key: a minimal set of attributes in a relation R such that no 2 tuples will have the same value for that set of attributes; key is a minimal set of super key
    - candidate key: any key
    - primary key: the key that is chosen to be used to identify tuples in a relation
    - foreign key: a set of attributes inside some relation R1 that is the primary key of another relation R2
  - Integrity Constraint 
    - Key constraint: every relation schema must have a primary key
    - Entity integrity: the attribute value of the primary key can not have NULL values
- Relation Algebra:
  - Selection and Projection:
    - selection $\sigma_{\text{condition}}(R)$ : select tuples from a relation $R$ that satisfies the condition. 
    - projection $\pi_{\text{attribute_list}}(R)$: select out only the attribute values given in the attribute list from all tuples in relation $R$ , the result is a set without duplicated element
  - Join: the only operation that can combine the information from multiple tables;
    - Cartesian product ($\times$ ) every tuple in $R1$ is combined with every tuple in $R2$ 
    - Inner Join: $R_1 \bowtie_{\text{Cond}} R2 = \sigma_{\text{Cond}}(R_1 \times R_2)$ 
    - Outer join: 
      - Left-outer : always contains all record from the left table, matched tuples processed normally, and unmatched is combined with a NULL value
      - Right-outer: always contains all record from right table
      - Full-outer: always contains all record from both table
    - Set Division: result of set division is that the combined tuples are in  origin dataset 
    - Set Function: 
      - Forming groups: Group are formed based on common values in one or more attributes, tuple with same attribute value will be put  in the same group 
      - set functions will be applied to each group
      - can be grouped by multiple values to get finer results, can apply multiple set functions
- SQL:
  - Define a database: 
    - create database, create user identified by password, grant permission on database.table to user
    - create table, constraint constraint-name PRIMARY KEY,  FOREIGN KEY  REFERENCES 
    - NOT NULL, DEFAULT, CHECK constraints
    - DROP TABLE, ALTER TABLE, can not rename attribute, have to drop and create new. 
  - Stored Procedure:
    - a generalization of SQL by adding programming language-like structure to the SQL language; like a method; can only be used within the database where the precedure is defined. 
- Database Design:
  - anomalies: bad properties in relations, but sometimes more efficient
    - insert anomaly: introduce NULL values
    - delete anomaly: causing additional information loss
    - update anomaly: updating multiple tuples from some relation
  - NF: normal form defines a set of properties that relations must satisfy.
  - Functional Dependencies: 
    - the cause of anomalies in relation is duplication of information due to dependencies between different attributes in the relation 
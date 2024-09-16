## Advantages of NoSQL Databases
- Can move very fast
- Can change schema very easily 
## Problems with NoSQL Databases
- Can lead to inconsistent database
- Can cause runtime errors
- Is too flexible for an app that needs strictness

> Note : One might feel that `mongoose` does add strictness to the codebase because we define a schema there. That strictness is only present at the NodeJS level, not at the DB level. One can still put in erroneous data in the database that doesn't follow our schema.

SQL databases have a strict schema. They require you to :
- Define your schema
- Put in data that follows your schema
- Update the schema as your app changes and perform `migrations`

SQL database :
- Running the database
- Using a library to connect to the database and put data in it
- Creating a table and defining it's schema
- Run queries on the database to interact with the data (Insert/Update/Delete)

- ![[Pasted image 20240911225929.png]] This is how a postgreSQL connection string looks like.

CRUD operations :
![[Pasted image 20240911230324.png]]

 



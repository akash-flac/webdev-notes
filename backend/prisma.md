# ORMs
- Object-Relational Mapping
- A programming technique used in software development to convert data between incompatible type systems in object-oriented programming languages. This technique creates a "virtual object database" that can be used from within the programming languages.
- Used to abstract the complexities of the underlying database into simpler, more easily managed objects within the code. 
- Basically, ORMs let one interact easily with the database without worrying too much about the underlying syntax(eg. SQL).
- ![[Pasted image 20240912003020.png]]
- It is an abstraction that lets you flip the database you are using. Unifies API irrespective of the DB. ![[Pasted image 20240912003348.png]] 
- Automatic Migrations : In a simple Postgres app, it's very hard to keep track of all the components that were ran that led to the current schema of the table. ORMs help in this.

# Prisma
- Data model : In a single file, define your schema. What it looks like, what tables you have, what field each table has, how are rows related to each other.
- Automated Operations : Prisma generates and runs database migrations based on changes to the Prisma schema.
- Type Safety : Prisma generates a type-safe database client based on the Prisma schema.
- ![[Pasted image 20240912004434.png]]
- 
# Section 4: Building and Deploying

- A model is the data representation of some group of data. In object-oriented programming terms, a model is an object and is represented by a new class. It should usually represent a noun such as a user, a feed item, an order, etc.

- The model contains instance parameters. These can be other models or primitive fields.

- ***ORMs*** allow us to easily switch to a different dialect of SQL (e.g. *PostgreSQL*, *MySQL*), without having to modify the code that interacts with the database. If we were to write SQL queries directly, instead of using an ORM, we would have to modify our SQL statements to be compatible with the dialect of the database that we are using.

- ***Migration*** refers to modifying the database (by adding or removing tables or columns, for instance, or switching to a different dialect of SQL) to a newer version (usually based on new business requirements).
  
  - Up migration is the process of modifying the database to a newer state.
  - Down migration is the process of reversing an up migration, to a prior state.

- ***Seeds*** are default rows of data that will be inserted upon database formation. This may be helpful when provisioning databases frequently for specific applications and having welcome data populated, or when running tests on staging systems to simulate real-world conditions.

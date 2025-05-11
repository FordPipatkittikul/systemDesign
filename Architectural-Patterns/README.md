# Web Sessions

A web session is a way for a website to remember information about a user as they interact with the site over a period of time.

# Serialization

Serialization is the process of converting an object into a format that can be easily stored or transmitted, and later reconstructed (deserialized) back into the original object.

# CQRS

CQRS stands for Command and Query Responsibility Segregation. Basically this pattern separates read and update operations for a database.

For example of reading database, if your application required some query that needs to join more than 10 table, this will lock the database due to latency of query computation.

CQRS offers to use “separation of concerns” principles and separate reading database and the writing database with 2 database. By this way we can even use different database for reading and writing database types like using no-sql for reading and using relational database for crud operations.

**How to Sync Databases with CQRS ?**

But when we separate read and write databases in 2 different database, the main consideration is sync these two database in a proper way.

So we should sync these 2 databases and keep sync always.

This can be solve by using Event-Driven Architecture. According to Event Driven Architecture, when something update in write database, it will publish an update event with using message broker systems and this will consume by the read database and sync data according to latest changes.

But this solution creates a consistency issue, because since we have implemented async communication with message brokers, the data would not be reflected immediately.

![alt text](<Screenshot (71).png>)
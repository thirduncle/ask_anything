# This is a place to put down any technical questions and (hopefully) get some answers.

1. What is an ORM (Object-Relational Mapping)

Object-Relational Mapping (ORM) is a technique that lets you query and manipulate data from a database using an object-oriented paradigm. When talking about ORM, most people are referring to a library that implements the Object-Relational Mapping technique, hence the phrase "an ORM".

An ORM library is a completely ordinary library written in your language of choice that encapsulates the code needed to manipulate the data, so you don't use SQL anymore; you interact directly with an object in the same language you're using.

2. Difference between PostgreSQL, SQLAlchemy, psycopg2

PostgreSQL is an open-source relational database management system (RDBMS).

SQLAlchemy is an ORM, psycopg2 is a database driver. These are completely different things: SQLAlchemy generates SQL statements and psycopg2 sends SQL statements to the database. SQLAlchemy depends on psycopg2 or other database drivers to communicate with the database!

As a rather complex software layer SQLAlchemy does add some overhead but it also is a huge boost to development speed, at least once you learned the library. SQLAlchemy is a excellent library and will teach you the whole ORM concept, but if you don't want to generate SQL statements to begin with then you don't want SQLAlchemy.


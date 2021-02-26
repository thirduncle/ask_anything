# This is a place to put down any technical questions and (hopefully) get some answers.

1. What is an ORM (Object-Relational Mapping)?

Object-Relational Mapping (ORM) is a technique that lets you query and manipulate data from a database using an object-oriented paradigm. When talking about ORM, most people are referring to a library that implements the Object-Relational Mapping technique, hence the phrase "an ORM".

An ORM library is a completely ordinary library written in your language of choice that encapsulates the code needed to manipulate the data, so you don't use SQL anymore; you interact directly with an object in the same language you're using.

2. Difference between PostgreSQL, SQLAlchemy, psycopg2

PostgreSQL is an open-source relational database management system (RDBMS).

SQLAlchemy is an ORM, psycopg2 is a database driver. These are completely different things: SQLAlchemy generates SQL statements and psycopg2 sends SQL statements to the database. SQLAlchemy depends on psycopg2 or other database drivers to communicate with the database!

As a rather complex software layer SQLAlchemy does add some overhead but it also is a huge boost to development speed, at least once you learned the library. SQLAlchemy is a excellent library and will teach you the whole ORM concept, but if you don't want to generate SQL statements to begin with then you don't want SQLAlchemy.

3. When exactly do you need to prepend self._ to variable declarations within class methods?

def thing_counter(self, thing):
    length_of_thing = len(thing)
    return length_of_thing
    
def thing_counter(self, thing):
    self._length_of_thing = len(thing)
    return self._length_of_thing

In the first version, length_of_thing will be created inside the function, and the return will return a copy to the caller. length_of_thing itself will not exist anymore after the return.

In the second one, self._length_of_thing will be created, not inside the function, but inside the instance of the class. The result is that it will be visible to all other methods. And the return still returns a copy. So possibly this version uses a little more memory, as the variable self._length_of_thing remains alive till the instance of the class is destroyed.

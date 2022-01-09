## ORM(Object Relational mapping) 
<img width="1093" alt="image" src="https://user-images.githubusercontent.com/35554521/148148761-e0759775-45be-4ee7-acb1-c58d2ea694d1.png">

ORM: hibernate, MyBatis, Sequelize, SQLAlchemy

## JPA(Java persistence API)
JPA is a collection of classes and methods to persistently store the vast amount of data into database, it is one of the specification in JEE(Java enterprise edition). 

Hibernate implement the JPA specification.

## Hibernate  
<img width="696" alt="image" src="https://user-images.githubusercontent.com/35554521/148150397-6f9e326f-0c7b-496f-b86b-a0efb298c407.png">

### Hibernate config
The dialect specifies the type of database used in hibernate so that hibernate generate appropriate type of SQL statements.

### Session factory

### Entity


## Fetch type
Lazy loading
Eager Loading

## ExceptionInInitializerError
The ExceptionInInitializerError indicates that an unexpected exception has occurred in a static initializer(Static Variable, Static Initializer Block)

## Blanks spaces are restricted in the naming convention of the database object's name and column name of the table

## @GeneratedValue
 Generated Identifiers

If we want to automatically generate the primary key value, we can add the @GeneratedValue annotation.

This can use four generation types: AUTO, IDENTITY, SEQUENCE and TABLE.

If we don't explicitly specify a value, the generation type defaults to AUTO.

## hibernate.cfg.xml
If you are using Maven to build your project, place the 'hibernate.cfg.xml' file under 'src/main/resources'

### Error:
```
Caused by: javax.xml.bind.UnmarshalException
 - with linked exception:
[javax.xml.stream.XMLStreamException: ParseError at [row,col]:[15,44]
Message: The value of attribute "class" associated with an element type "mapping" must not contain the '<' character.]
```
Could be caused by syntax problems in your hibernate.cfg.xml file.

'''
WARN: HHH90000012: Recognized obsolete hibernate namespace http://hibernate.sourceforge.net/hibernate-configuration. Use namespace http://www.hibernate.org/dtd/hibernate-configuration instead.  Support for obsolete DTD/XSD namespaces may be removed at any time.
```
In Hibernate.cfg.xml the <!DOCTYPE hibernate-configuration PUBLIC replace the former link with the later link

```
could not find the table
```
The "hibernate.dialect" org.hibernate.dialect.MySQL8Dialect must match the verison of database. For example, the database is MySQL 8.0.27, use MySQL8Dialect
 
 
 
## Cache
First level cache (also session level cache)
Second level cache (Also session level cache)

EhCache
OSCache

## JDBC vs ORM
JDBC
Pros:
1. Small scale project it is recommended to go with JDBC
2. JDBC provides better performance with large amounts of data
3. Small application

Cons:
1. JDBC is not easy for large projects beacause it requires a lot setup.
2. query language is dependent on database
3. Have to take care of transaction manually
4. manually close th connection

ORM
Pros:
1. no need to deal with sql queries
2. Switching database is easier
3. support cache

Cons:
1. slower than JDBC




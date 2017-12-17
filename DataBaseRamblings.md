# **RDBMS inshort**
<!-- MarkdownTOC -->

1.  Keys
- Joins
- Normalization
<!-- /MarkdownTOC -->

## Keys
- Primary key
- Unique key
- Foreign Key

## Joins
- Inner Join : Inner join return rows when there is at least one match of rows between the tables.
- Left Join : Left join return rows which are common between the tables and all rows of Left hand side table
- Right Join : Right join return rows which are common between the tables and all rows of Right hand side table
- Full Join : It returns all the rows from the left hand side table and all the rows from the right hand side table.

## Normalization
Normalization is the process of minimizing redundancy and dependency by organizing fields and table of a database. The main aim of Normalization is to add, delete or modify field that can be made in a single table.

- **First Normal Form (1NF):**
This should remove all the duplicate columns from the table. Creation of tables for the related data and identification of unique columns.
- **Second Normal Form (2NF):**
Meeting all requirements of the first normal form. Placing the subsets of data in separate tables and Creation of relationships between the tables using primary keys.
- **Third Normal Form (3NF):**
This should meet all requirements of 2NF. Removing the columns which are not dependent on primary key constraints.
- **Fourth Normal Form (3NF):**
Meeting all the requirements of third normal form and it should not have multi- valued dependencies.

## View
A view is a virtual table which consists of a subset of data contained in a table. Views are not virtually present, and it takes less space to store. View can have data of one or more tables combined, and it is depending on the relationship.
## Index
An index is performance tuning method of allowing faster retrieval of records from the table. An index creates an entry for each value and it will be faster to retrieve data.
- Unique Index.
This indexing does not allow the field to have duplicate values if the column is unique indexed. Unique index can be applied automatically when primary key is defined.
- Clustered Index.
This type of index reorders the physical order of the table and search based on the key values. Each table can have only one clustered index.
- NonClustered Index.
NonClustered Index does not alter the physical order of the table and maintains logical order of data. Each table can have 999 nonclustered indexes.



### Design question :
Usual design question has to be answered around these items :
1. Abstraction. It’s a very important topic for system design interview. You should be clear about how to abstract a system, what is visible and invisible from other components, and what is the logic behind it. Object oriented programming is also important to know.
- Database. You should be clear about those basic concepts like relational database. Knowing about No-SQL might be a plus depends on your level (new grads or experienced engineers).
- Network. You should be able to explain clearly what happened when you type “gainlo.co” in your browser, things like DNS lookup, HTTP request should be clear.
- Concurrency. It will be great if you can recognize concurrency issue in a system and tell the interviewer how to solve it. Sometimes this topic can be very hard, but knowing about basic concepts like race condition, dead lock is the bottom line.
- Operating system. Sometimes your discussion with the interviewer can go very deeply and at this point it’s better to know how OS works in the low level.
- Machine learning (optional). You don’t need to be an expert, but again some basic concepts like feature selection, how ML algorithm works in general are better to be familiar with.


### what happens when a url is typed:
In an extremely rough and simplified sketch, assuming the simplest possible HTTP request, no proxies, IPv4 and no problems in any step:
1. browser checks cache; if requested object is in cache and is fresh, skip to #9
browser asks OS for server's IP address
- OS makes a DNS lookup and replies the IP address to the browser
- browser opens a TCP connection to server (this step is much more complex with HTTPS)
- browser sends the HTTP request through TCP connection
- browser receives HTTP response and may close the TCP connection, or reuse it for another request
- browser checks if the response is a redirect or a conditional response (3xx result status codes), authorization request (401), error (4xx and 5xx), etc.; these are handled differently from normal responses (2xx)
- if cacheable, response is stored in cache
- browser decodes response (e.g. if it's gzipped)
- browser determines what to do with response (e.g. is it a HTML page, is it an image, is it a sound clip?)
- browser renders response, or offers a download dialog for unrecognized types


The company is structured around two areas: its global distribution system and its IT Solutions business area. Acting as an international network, Amadeus provides search, pricing, booking, ticketing and other processing services in real-time to travel providers and travel agencies through its Amadeus CRS distribution business area. Through its IT Solutions business area, it also offers travel companies software systems which automate processes such as reservations, inventory management and departure control.

The group, which processed 850 million billable travel transactions in 2010,[2] services customers including airlines, hotels, tour operators, insurers, car rental and railway companies, ferry and cruise lines, travel agencies and individual travellers directly.

**ACID (Atomicity, Consistency, Isolation, Durability)** is a set of properties of database transactions intended to guarantee validity even in the event of errors, power failures, etc. In the context of databases, a sequence of database operations that satisfies the ACID properties, and thus can be perceived as a single logical operation on the data, is called a transaction. For example, a transfer of funds from one bank account to another, even involving multiple changes such as debiting one account and crediting another, is a single transaction.

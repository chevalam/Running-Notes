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


### Thread Specific Data
The general steps that a library function performs in order to use thread-specific
data are as follows:
660
1. The function creates a key, which is the means of differentiating the thread-specific
data item used by this function from the thread-specific data items used by
other functions. The key is created by calling the pthread_key_create() function.
Creating a key needs to be done only once, when the first thread calls the function.
For this purpose, pthread_once() is employed. Creating a key doesn’t allocate
any blocks of thread-specific data.
- The call to pthread_key_create() serves a second purpose: it allows the caller to
specify the address of the programmer-defined destructor function that is used
to deallocate each of the storage blocks allocated for this key (see the next
step). When a thread that has thread-specific data terminates, the Pthreads API
automatically invokes the destructor, passing it a pointer to the data block for
this thread.
- The function allocates a thread-specific data block for each thread from which
it is called. This is done using malloc() (or a similar function). This allocation is
done once for each thread, the first time the thread calls the function.
- In order to save a pointer to the storage allocated in the previous step, the func-
tion employs two Pthreads functions: pthread_setspecific() and pthread_getspecific().
A call to pthread_setspecific() is a request to the Pthreads implementation to say
“save this pointer, recording the fact that it is associated with a particular key (the
one for this function) and a particular thread (the calling thread).” Calling
pthread_getspecific() performs the complementary task, returning the pointer pre-
viously associated with a given key for the calling thread. If no pointer was
previously associated with a particular key and thread, then pthread_getspecific()
returns NULL . This is how a function can determine that it is being called for the
first time by this thread, and thus must allocate the storage block for the thread.
~~~~
#include <pthread.h>
int pthread_key_create(pthread_key_t * key , void (* destructor )(void *));
Returns 0 on success, or a positive error number on error
~~~~
Upon termination of a thread that has a non- NULL value associated with key, the
destructor function is automatically invoked by the Pthreads API and given that
value as its argument. The passed value is normally a pointer to this thread’s
thread-specific data block for this key. If a destructor is not required, then destructor
can be specified as NULL

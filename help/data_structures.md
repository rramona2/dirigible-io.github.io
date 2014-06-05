---
layout: help
---

Data Structures
===

Overview
---

Data Structures term in the context of the cloud toolkit is used for refering the Domain Model of the application. For pragmatic reasons it is chosen that the actual entities in the domain model to correspond 1:1 to the underlying database entities - tables and views. There is no additional abstract layer between your application code and the actual model in target storage.

Tables
---

*Table Model* is a JSON formatted *.table descriptor which represents the layout of the database table which will be created during activation process.

Example descriptor:

> {
>   "tableName":"TEST001",
>   "columns":
>     [
>       {
>         "name":"ID",
>         "type":"INTEGER",
>         "length":"0",
>         "notNull":"true",
>         "primaryKey":"true",
>         "defaultValue":""
>       }
>       ,
>       {
>         "name":"NAME",
>         "type":"VARCHAR",
>         "length":"20",
>         "notNull":"false",
>         "primaryKey":"false",
>         "defaultValue":""
>       }
>       ,
>       {
>         "name":"DATEOFBIRTH",
>         "type":"DATE",
>         "length":"0",
>         "notNull":"false",
>         "primaryKey":"false",
>         "defaultValue":""
>       }
>       ,
>       {
>         "name":"SALARY",
>         "type":"DOUBLE",
>         "length":"0",
>         "notNull":"false",
>         "primaryKey":"false",
>         "defaultValue":""
>       }
>     ]
> }


The supported database types are:

> * *VARCHAR*     - for text based fields up to 2K characters
> * *CHAR*        - for text based fields with fixed lenght up to 255 characters
> * *INTEGER*     - 32 bit
> * *BIGINT*      - 64 bit
> * *SMALLINT*    - 16 bit
> * *REAL*        - 7 digits of mantissa
> * *DOUBLE*      - 15 digits of mantissa
> * *DATE*        - represents a date consisting of day, month, and year
> * *TIME*        - represents a time consisting of hours, minutes, and seconds
> * *TIMESTAMP*   - represents DATE plus TIME plus a nanosecond field and time zone
> * *BLOB*        - binary object - images, audio, etc.

Activation of table descriptor is a process of creation of the database table in the target database.
The activator constructs a "CREATE TBALE" SQL statement considering the dialect of the target database system.
If the table with the given name already exists, the activator checks whether there is a compatible change (adding of new columns) and construct "ALTER TABLE" SQL statement.
If the there is an incompatible change, then the activator returns an error which have to be solved manually via the SQL Console.

Views
---

*View Model* is also JSON formatted *.view descriptor of a database view. Usually it is a join between multiple tables used for reporting purposes.
The script should follow the SQL92 standard, or have to be aligned with the dialect of the target database.

Data Files
---

Delimiter Separated Values *data files* *.dsv are used for importing some test data during the development or for defining a static content for some nomenclatures for instance.
The convention is that the name of the data file should be the same as the name of the target table.
The delimiter is the char "|" and the order of the data fields should be the same as the natural order of the target table.
If you want to import some data only once, this can be done via the Import Data Wizard.

> Be careful when using the static data in tables. [Entity Services](entity_service.html) (generated by the templates) are using sequence algorithm for identity column starting from 1.

The automatic re-initialization of the static content from the data file can be achieved when you create a *.dsv file under the DataStructures folder of the given project.
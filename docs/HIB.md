# HIB - Health Informatics B

## Meteor

| **Meteor metadata item types**  | **Example**                                                | **Detailed explanation: how example fulfils metadata item type definition** |
| ------------------------------- | ---------------------------------------------------------- | ------------------------------------------------------------ |
| **Data set specification**      | *Address details cluster*                                  | Cluster identifies groups of data elements and conditions of how collected data is grouped. This fits into DSS as it defines what data elements should be included and the scope of collection characteristics. |
| **Data Element**                | *Person(name)-given name, text X (39)*                     | Provides detailed specifications about the person – combination for different data |
| **Data Element Concept**        | *Combination of episode of admitted patient care with LOS* | By combining an object class and a property it produces a data element concept |
| **Object Class**                | *Patient*                                                  | Patient by itself does not provide enough detail, so it further specification needs to be added, as patient only describes a category of people, not each individual patient |
| **Property**                    | *Episode start date*                                       | Episode start end is just a characteristic of an object class of interest, in this case a patient’s admissions |
| **Object Class specialization** | *Type of patient (e.g cardiovascular)*                     | The type of patient provides more information about the object class (patient). Additionally, cardiovascular groups the patient into a treatment type providing additional information |
| **Property group**              | *Accommodation/living characteristics*                     | Accommodation/living characteristics provides further detail about the types of properties by grouping them in categories |
| **Value domain**                | *External cause code (ICD-10 classifications)*             | External cause codes are specified values which allow for data elements to be implemented |
| **Classification scheme**       | *ICD 10 classifications*                                   | ICD 10 classifications is a system which groups data items into diagnosis and procedural. |

- Metadata allows the discover of relevant information. When you are creating information, you need to assign metadata 
- Metadata is data about data, it describes other data 
- Data dictionary, schema and database logical design are all examples of extracting of metadata 
- Name of database where metadata is typically stored is metadata registry 

| **Type**               | **Example**                                                  |
| ---------------------- | ------------------------------------------------------------ |
| **One to one (1:1)**   | e.g patient demographic details. A single patient only has one DOB or one gender |
| **Many to one (M:1)**  | e.g patient and test results. A single patient may have many different types of results |
| **Many to Many (M:M)** | e.g patient and doctor. A single patient can see by many doctors and a single doctor can see many patients |

*From reference table to all table (1:M) E.g. doctor details (1) to patient appointments (M)

##Database table components:

- Table (file or entity)

- - ‘list of things’ E.g. people, episodes
  - Data is all of the same type of thing
  - Data only occurs in one space- no redundancy

- Record (line or row)- individual entry in a table for one person, e.g episode or person

- Field (column or data item)- column in a table, data is of the same type e.g surname

- Cell (data element)- record field, holding value

- Value- the thing in a cell (e.g. M in sex field)

##Database design components (Things we need to decide)

- Data base structure: 

- - table fields
  - Relationships

- Field formatting

- Business rules

Database design summary

- Establish entities (tables)
- Define data items within entities
- Define rules/codes for those entities
- Establish lookup files
- Establish relationships

In consultation with data dictionaries (AIHW)

##Database layers:

- Structure

- - Tables, fields- data structure
  - Field rules- business rules
  - **Relationships** and associated keys- connections between tables
  - Indexes- to speedup lookup

- Actual data

- - Records- forms collected and filed by type of form

**Relationships**: an association between the instances of one or more entity types that is of interest to the organisation (and needs to be stored)

- An **association** means some event has occurred or that there exists some natural linkage between entity instances

- Within files (key elements and indices)

- Between files

- - Provides a look up facility between files to show how the files are linked to each other
  - May be 1:1, 1:M or M:M
  - E.g. one to many (a patient may have many names)

**Degree of a relationship**: number of entity types that participate in a relationship

Most common relationships are:

- Unary (degree 1)- relationship between instances of the one entity type

- - Can be 1:1, M:1, M:M

- Binary (degree 2): a relationship between instances of two entty types

- Ternary (degree 3): simultaneous relationship between instances of three entity types





A community organisation has approached you as an HIM for information regarding asthma in the area surrounding a industrial site.

##**Database Design rules / best practice**

- no redundancy/ duplication

- Tables are for lists of things

- One type of thing per table

- One type of thing per field

- Use relationships

- Every table needs a primary key- unique attribute for a row

- - Attributes: identifier (i.e ID)

##**Microsoft access**

- Is a database (tables to hold information), a query language, a report generator, a software development language
- All elements (table, queries etc) have two versions- a structure or design and the data stored in and retrieved by that design

How to get data from a database?

- Layers of software

- MS access

- - Directly from tables
  - Queries based on table or other queries
  - Reports based on tables or queries
  - Can do simple statistics and grouping/sorting
  - Pre-programmed templates

Query language: a language for the specific procedure of extracting data from a database using specific criteria and presentation instructions

- Selection criteria- selecting rows (records) and columns (fields)
- Sort sequences
- Calculations
- Outputs can then be queried or reported, layer by layer

Data extraction pipeline- what to do when someone hands you some data for extraction

- Understand data structure and content

- - Establish data structure (model)
  - Populate control/reference tables with codes
  - Establish relationships between tables

- Establish question

- - Which data to use?
  - Any limits (criteria)?
  - Build special data items?
  - Checking the data you retrieve

- Prepare report to present data

Data reporting

Query/ report commonalities

- Can get data from database, tables and/or queries

- To other programs and systems

- Can change format e.g. totalling/grouping/sorting

- Used to: 

- - select data

  - ‘Move data’ query type

  - - make a table to generate a new table containing the query data (to manipulate the data, unlike the original table (non-query))
    - append- add records to a table using a query. E.g add new patient’s to a file, or new episodes of care meeting specific critera

  - ‘reformat’ query type

  - - Crosstab- tabulates counts of row/column pairs

  - ‘Change data’ query type

  - - Update- updates existing table with entries from the query E.g update postcode for people with a specific address
    - Delete- deletes records that meet the criteria of the query

##Compare/ difference between reports and queries

Query: 

- designed for computers, are just raw data
- Each row of data has same number of columns (‘square’ format)
- Output data- same type of thing (homogenous)
- Outputs: only input data

Report: 

- designed for people, should stand along
- each row of data is possibly different (stepped or grouped)
   output data is possibly different types (heterogenous)
- Outputs: output data and page numbers, dates, descriptive text

Multiple queries/query on query

- First query selects a subset of rows and columns

- Next query/queries based on subset

- Use multiple queries when: 

- - Simplify a query
  - Large number of criteria
  - Single query will not suffice
  - Multiple complex calculation

**Definitions**

**Primary key**: A set of attributes that distinctly identifies a record in a relation.

**Foreign Key**: Key or attribute which links two tables.

- Is a field (collection) of fields in one table that refers to the primary key in another table.
- The foreign key needs to be present in the reference table (as primary key)

**Entity**: Tables transcribe entities to relation



Once table specifications are finished, we need to specify the fields

- Use business rules to specify fields
- Use standards to specify fields E.g. DD/MM/YYYY
- E.g what is the rule for gender/ birthdate/principal diagnosis?
- A constraint e.g. To make a valid item, make it only available on a particular dataset. E.g PD

Data rules

- Rules apply wherever field is used
- E.g data bust be a proper date
- Gender must be F or M or U or I
- In Microsoft Access, rules are established in the tables through validation or reference tables
- In Microsoft Access, data rules is controlled by data types. E.g numbers, dates/ times, yes/no, text. 
- E.g. date must be a real date

Validation rules

- Useful for small, constant validations
- E.g. gender- must be a defined value, from a small set of generally understood values

**Data item**: a single entity in a computer system to which codes or rules may be applied. Also known as field or data element

- To clarify meaning, help with communication and ensure good data use

**Data dictionary**: formal approach to data definitions

**Data model**: a pictorial representation of data relationships

**Entity relationship diagram:** graphical representation of an E-R model

**Entity**: a person, place, object, event or concept 

- E.g. doctor, region, machine, sale, course
- Symbol used: rectangle

**Attribute**: a named property or characteristic of an entity that is of interest to us (or to the owners of the data, the organisation concerned etc)

- E.g STUDENT: student ID, student name, course 
- Symbol used: oval

Difference between an attribute and an entity?

- No attribute should be repeated across entities

**Candidate key**: an attribute (or collection of attributes) which uniquely identifies each instance of an entity type

**Composite key:** candidate key that consists of two or more attributes (table columns) that uniquely identify an entity occurrence (table row). A compound key is a composite key for which each attribute that makes up the key is a simple (foreign) key in its own right.







Example of an entity. Circles are attributes






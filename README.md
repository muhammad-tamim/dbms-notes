<h1 align="center">Database Management Systems Notes</h1>

- [Introduction](#introduction)
    - [Problem with traditional file systems:](#problem-with-traditional-file-systems)
    - [Most Common Types of DBMS:](#most-common-types-of-dbms)
    - [DBMS Architecture:](#dbms-architecture)
    - [Software Development Life Cycle (SDLC):](#software-development-life-cycle-sdlc)
    - [Database Design:](#database-design)
    - [Relationship Cardinality:](#relationship-cardinality)
    - [Relationship Cardinality Signs:](#relationship-cardinality-signs)
    - [Entity-Relationship (ER) Diagram:](#entity-relationship-er-diagram)
      - [Example 1:](#example-1)
- [Relational Database Management System](#relational-database-management-system)
    - [Schemas, Instance and Entities:](#schemas-instance-and-entities)
    - [Table in RDBMS::](#table-in-rdbms)
    - [keys in RDBMS:](#keys-in-rdbms)
      - [Super Key:](#super-key)
      - [Candidate key:](#candidate-key)
      - [Primary key:](#primary-key)
      - [Alternate key:](#alternate-key)
      - [Composite key:](#composite-key)
      - [Foreign key:](#foreign-key)

# Introduction
A Database Management System (DBMS) is a software system that allows us to manage data through databases. It acts as a bridge between the database and users or applications.

Note: 
- Data: Raw, unprocessed facts: 85, 90, 88, 92, 87
- Information: Processed data: Calculate the average temperature: sum of data / 5 = 88.4 (Information)
- Database: Organized collection of data

### Problem with traditional file systems:
Before the introduction of modern DBMS, data was managed using basic file systems on hard drives. While this approach allowed us to manage files as needed, but it came with numerous challenges such as: 
- Data Redundancy and inconsistency
- Difficult in Accessing the data
- Poor Security
- No support for collaboration
- No Backup/Recovery
  
### Most Common Types of DBMS: 

1. Relational Database Management System (RDBMS):
   - Data is organized in tables (relations) with rows and columns.
   - Uses Structured Query Language (SQL).
   - Examples: Oracle, MySQL, Microsoft SQL Server, PostgreSQL etc.
2. Non-Relational Database Management System (NoSQL DBMS):
   - Data is stored in a non-tabular(unstructured, flexible) format (key-value pairs, JSON-like documents, graphs etc).
   - Examples: MongoDB, Redis, Amazon DynamoDB etc.

### DBMS Architecture: 
- 1-Tier Architecture: Client and database are part of the same local system.
  - client + database
  - Example: MS Excel, SQLite, MS Access 
  
- 2-Tier Architecture: Client and database are on separate systems.
  - client --> database
  - Example: Desktop app → MySQL / SQL Server

- 3-Tier Architecture: The client communicates with an server, which then communicates with the database.
  - client --> server --> database

### Software Development Life Cycle (SDLC):
Planning -> Analysis -> System Design (Frontend, Backend, Database etc) -> Implementation (Building) -> Testing -> Maintenance (Deployment)

### Database Design: 
- Determining Entities (Students, Courses, Grades etc)
- Determining Attributes for each entities (Student_ID, Email, Phone etc)
- Determining Relationships between entities (Relationship Cardinality)
- Resolving Many to Many relationships

### Relationship Cardinality:
Relationship cardinality defines how many instances of one entity can be associated with how many instances of another entity in a database relationship.

Types of Relationship Cardinality: 

- One-to-One (1:1)
  - One record in Entity A is related to only one record in Entity B.
  - One student has one student ID.
  
- One-to-Many (1:N)
  - One record in Entity A can be related to many records in Entity B, but Entity B relates to only one record in A.
  - One student can enroll in many courses, but each course belongs to one student.

- Many-to-One (N:1)
  - Many records in Entity A can be related to one record in Entity B, but Entity B relates to many records in A.
  - Many students can enroll in-one course, but each student belongs to one course

- Many-to-Many (M:N)
  - Many records in Entity A can be related to many records in Entity B.
  - A student can enroll in many courses, and a course can have many students.

### Relationship Cardinality Signs: 

![alt text](./images/relationship-cardinality-signs.png)

### Entity-Relationship (ER) Diagram:
Entity-Relationship Diagram is a visual representation of entities, their attributes, and the relationships between them in a database system.

#### Example 1:
Business idea: EduHub is a global website offering a variety of technology courses across different subjects, allowing students to enroll and learn

Database Design: 
- Determining Entities:
Students, Courses, Instructors

- Determining Attributes for each entities (Student_ID, Email, Phone etc)
  - for Students Entity: Student_ID, Name, Email
  - for Courses Entity: Course_ID, Course_Name, Instructor_ID
  - for Instructors Entity: Instructor_ID, Name, Email

![alt text](./images/ERD-1.png)


# Relational Database Management System

### Schemas, Instance and Entities:

**Schemas** is the logical structure or blueprint of the database that defines tables, attributes, relationships, constraints etc. It changes rarely. 

```sql
CREATE TABLE students (
    student_id SERIAL PRIMARY KEY,
    email      VARCHAR(255) UNIQUE NOT NULL,
    phone      VARCHAR(20)
);
```

**Instance** is the actual data (rows) stored in the database according to the schemas at a specific time. It changes frequently.

| Student_ID | Email           | Phone        |
| ---------- | --------------- | ------------ |
| 1          | test1@gmail.com | 123-456-789  |
| 2          | test2@gmail.com | 123-456-7890 |
| 3          | test3@gmail.com | 123-456-7891 |

**Entities** are the different types of tables in the database.

| Student_ID | Email           | Phone        |
| ---------- | --------------- | ------------ |
| 1          | test1@gmail.com | 123-456-789  |
| 2          | test2@gmail.com | 123-456-7890 |
| 3          | test3@gmail.com | 123-456-7891 |

here, full students table is an entity.

### Table in RDBMS:: 
![alt text](./images/table-or-relation.png)

### keys in RDBMS:
A key is an attribute (or a set of attributes) used to uniquely identify a row (tuple) in a table and to establish relationships between tables.

| Student_ID | Email           | Phone        |
| ---------- | --------------- | ------------ |
| 1          | test1@gmail.com | 123-456-789  |
| 2          | test2@gmail.com | 123-456-7890 |
| 3          | test3@gmail.com | 123-456-7891 |

#### Super Key: 
A Super Key is any attribute or set of attributes that can uniquely identify a record in a table.

In the above table, the possible super keys: 
- {Student_ID}
- {Email}
- {Student_ID, Email}
- {Student_ID, Phone}

#### Candidate key: 
A Candidate Key is a minimal super key.

In the above table, the candidate keys are: 
- {Student_ID}
- {Email}

Note: {Student_ID, Email} is a super key but not a candidate keys because Student_ID and Email both alone can uniquely identify a record.

#### Primary key: 
A Primary Key is a candidate key that are:
- Cannot be NULL
- Must be unique
- Only one per table.

In the above table, the primary keys are: 
- Student_ID

#### Alternate key: 
All candidate keys that are NOT chosen as the primary key are called Alternate Keys.

In the above table, the alternate keys are: 
- Email

Note: Since Student_ID is the primary key, so in the table then Email is the alternate key.

#### Composite key: 
A Composite Key is a candidate key that made of two or more attributes that together uniquely identify a record.

| Student_ID | Email           | Phone       |
| ---------- | --------------- | ----------- |
| 1          | test1@gmail.com | 123-456-789 |
| 2          | test2@gmail.com | 123-456-789 |
| 3          | test3@gmail.com | 123-456-789 |


| Grade_id | Student_ID | Course_ID | Grade |
| -------- | ---------- | --------- | ----- |
| 1        | 1          | CS101     | A     |
| 2        | 2          | CS101     | A     |
| 3        | 3          | CS101     | A     |
| 4        | 1          | CS102     | A     |
| 5        | 1          | CS103     | A     |
| 6        | 2          | CS103     | A     |

here, the candidate keys are: 
- {Student_ID, Course_ID}

#### Foreign key:  
A Foreign Key is an attribute in one table that refers to the primary key of another table. It establishes relationships between tables.

In the Grade Table table, the foreign keys are:
- {Student_ID} 


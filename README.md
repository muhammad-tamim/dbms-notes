<h1 align="center">Database Management Systems Notes</h1>

- [Introduction](#introduction)
    - [Problem with traditional file systems:](#problem-with-traditional-file-systems)
    - [Most Common Types of DBMS:](#most-common-types-of-dbms)
    - [DBMS Architecture:](#dbms-architecture)
    - [Schemas and Instance:](#schemas-and-instance)

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
  
### Schemas and Instance:

**Schemas** is the logical structure or blueprint of the database that defines tables, attributes, relationships, constraints etc. It changes rarely. 

Example: Table Student (id, name, dept)

**Instance** is the actual data stored in the database according to the schemas at a specific time. It changes frequently.

Example: (1, 'Alice', 'CS'), (2, 'Bob', 'EE')


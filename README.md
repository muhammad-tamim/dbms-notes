<h1 align="center">Database Management Systems Notes</h1>

- [Introduction](#introduction)
    - [Problem with traditional file systems:](#problem-with-traditional-file-systems)
    - [Most Common Types of DBMS:](#most-common-types-of-dbms)

# Introduction
A Database Management System (DBMS) is a software system that allows us to manage data through databases. It acts as an bridge between the database and users or applications.

### Problem with traditional file systems:
Before the introduction of modern DBMS, data was managed using basic file systems on hard drives. While this approach allowed us to manage files as needed, but it came with numerous challenges such as: 
- Data Redundancy: Same data stored in multiple places
- Inconsistency: Different versions of the same data
- Difficult Access: Manual file search required
- Poor Security: No control over data access
- Single-User Access: No support for collaboration
- No Backup/Recovery: Data loss was often permanent

### Most Common Types of DBMS: 

1. Relational Database Management System (RDBMS):
   - Data is organized in tables (relations) with rows and columns.
   - Uses Structured Query Language (SQL).
   - Examples: Oracle, MySQL, Microsoft SQL Server, PostgreSQL etc.
2. Non-Relational Database Management System (NoSQL DBMS):
   - Data is stored in a non-tabular(unstructured, flexible) format (key-value pairs, JSON-like documents, graphs etc).
   - Examples: MongoDB, Redis, Amazon DynamoDB etc.

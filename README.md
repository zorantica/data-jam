# Data JAM for Oracle (Journaling & Auditing Module)

<p style="text-align:center;"><img src="img/icon.png"/></p>

Data JAM is an Oracle Database product / utility designed to automate the auditing of DML data changes in desired database schemas and tables.

It's usage simplifies the tracing of data changes and provides answers on various questions like:

- Who changed the record in the table?
- When?
- What was changed?
- From which application or client tool?
- From which IP address?

It can also assist developers during the debugging of the program logic and application behavior OR during the data restauration.

How?

- By generating scripts for necessary database objects in order to capture a complete audit trace of all INSERT, UPDATE, and DELETE operations.
- By analysing actual data changes which occured in table records.

## Key Features

**Automated Data Auditing:** Generates audit tables and triggers with a few clicks, creating an auditing mechanism.

**Built-in Audit Viewer:** A user-friendly GUI developed in Oracle APEX to easily query, filter, and analyze the audited data changes.

**Flexible Standards:** Define your own naming standards for all audit objects.

**Highly Configurable:** Fine-tune auditing by excluding specific columns based on names or data types. Define custom audit information like app ID, page ID, module, IP address, computer name, APEX request...

**Customizable Core:** Modify the audit trigger template to implement custom auditing logic.

## How does the Data Auditing work

Every monitored table contains a set of audit database objects:

- Audit table which stores audit data. This table contains the same columns as the monitored table PLUS audit information columns (like audit user, audit timestamp...).
- Audit DML trigger which is created on the monitored table. It is actually writing audit data in the audit table.
- Audit index in the audit table for faster data access and analysis.
- Appropriate grants for data auditing and data analysis.

So, when a data is changed in the monitored table, the whole changed record is copied in the audit table. Additionally, audit information columns like audit user and audit timestamp are also populated.

Actual data changes are analysied and the list provided from the Data JAM application UI on the user request.

Audit table can be located in a separate database schema (recommended) or in the same schema as the monitored table.

## Installation instructions

- Download the APEX application [from the install folder](https://github.com/zorantica/data-jam/blob/main/install/jam.sql).
- Install the application in the desired workspace together with supporting objects. *Ignore he fact the application wants to execute the upgrade of supporting objects even if it goes for a clean new install.*
- Be sure the appropriate SELECT privileges are assigned to the database user where the JAM is installed (You may check the helper script for database user generation [located in the install folder](https://github.com/zorantica/data-jam/blob/main/install/user.sql)). Assigned SELECT privileges are checked during the application installation.
- Use APEX accounts to log into the application.

![alt text](img/login.png)

## How to use Data JAM

### Locate and rename the Project

When a Data JAM is freshly installed there is a default project created. Project holds all necesarry settings and naming conventions for audit objects.

You should rename the project for Your purposes and apply changes.

![alt text](img/Settings01.png)

### Select a monitored schema and assign a schema for audit objects

On Project details page add a new monitored schema and assign an audit schema which is going to hold audit tables, data and other necessarry database objects.

![alt text](img/Schema01.png)

### Do the Initial Setting

Before staring to produce scripts for audit objects You should do the initial settings which have the direct impact on naming conventions, audited columns in tables, audit trigger PL/SQL code and audit information columns.

#### Naming Conventions

#### Excluded Columns by Data Type

#### Excluded Columns by Name

#### Trigger Template

#### Audit Information Columns

## DBA Remarks

From DBA perspective it is recommended to create a separate schema and separate tablespace for audit data.

Also, in a dynamic systems with many DML changes the amount of audit data can be significant. Therefore it is recomended to monitor the audit data tablespace size.

## Changelog

- 1.0.0 - Initial Release

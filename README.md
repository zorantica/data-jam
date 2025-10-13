# Data JAM for Oracle (Journaling & Auditing Module)

Data JAM is an Oracle Database product / utility designed to automate the auditing of DML data changes in desired database schemas and tables.

It's usage simplifies the tracing of data changes and provides answers on various questions like:

- Who changed the record in the table?
- When?
- What was changed?
- From which application or client tool?
- From which IP address?

It can also assist developers during the debugging of the program logic and application behavior.

How?

- By generating scripts for necessary database objects in order to capture a complete audit trace of all INSERT, UPDATE, and DELETE operations.
- By analysing actual data changes which occured in table records.

## Key Features

**Automated Data Auditing:** Generates audit tables and triggers with a few clicks, creating an auditing mechanism.

**Built-in Audit Viewer:** A user-friendly GUI developed in Oracle APEX to easily query, filter, and analyze the audited data changes.

**Flexible Standards:** Define your own naming standards for all journaling and audit objects.

**Highly Configurable:** Fine-tune auditing by excluding specific columns baes on names or data types. Define custom audit information like app ID, page ID, module, IP address, computer name, APEX request...

**Customizable Core:** Modify the audit trigger template to implement custom auditing logic.

## Changelog

- 1.0.0 - Initial Release

## Installation instructions

- Download the APEX application [from the install folder](https://github.com/zorantica/data-jam/blob/main/install/jam.sql).
- Install the application in the desired workspace together with supporting objects. *Ignore he fact the application wants to execute the upgrade of supporting objects even if it goes for a clean new install.*
- Be sure the appropriate SELECT privileges are assigned to the database user where the JAM is installed (You may check the helper script for database user generation [located in the install folder](https://github.com/zorantica/data-jam/blob/main/install/user.sql)).

## How to use Data JAM

### Locate and rename the project

When a Data JAM is freshly installed there is a default project created. Project holds all necesarry settings and naming conventions.

You should rename it for Your purposes and apply changes.

![alt text](img/Settings01.png)

#### Select a monitored schema and assign a schema for auditing objects

On Project details page add a new schema for monitoring and assign a schema which is going to hold audit tables with audit data.


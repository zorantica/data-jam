# Data JAM for Oracle (Journaling & Auditing Module)
Data JAM is a powerful and highly configurable Oracle Database utility designed to automate the auditing of data changes. It simplifies data tracing and debugging by automatically generating scripts for the necessary database objects in order to capture a complete journal of all INSERT, UPDATE, and DELETE operations.

### Key Features:

**Automated Data Auditing:** Generates audit tables and triggers with a few clicks, creating a full-change journal.

**Built-in Audit Viewer:** A user-friendly GUI developed in Oracle APEX to easily query, filter, and analyze the journaled data changes.

**Flexible Standards:** Define your own naming standards for all journaling and audit objects.

**Highly Configurable:** Fine-tune auditing by excluding specific columns baes on names or data types. Define custom audit information like app ID, page ID, module, IP address, computer name, APEX request...

**Customizable Core:** Modify the audit trigger template to implement custom auditing logic.

## Changelog
- 1.0.0 - Initial Release

## Installation instructions
- download the APEX application from the install folder 
- install the application in the desired workspace together with the supporting objects
- be sure the appropriate privileges are assigned to the database user where the JAM is installed

## How to use Data JAM
*Procedure and Function descriptions with input and output parameters are located in package definition script.*



## Demo
A demo script together with demo package and APEX application is located under "demo" directory.

### Install the demo on Your environment
First execute the script tables_and_data.sql, which will create demo tables and populate them with data.

Then install demo database package ZT_SVG_DEMO (specification and body).

At the end import APEX demo aplication and run it.

*Demo script and package should be installed in a database schema assigned to a workspace, where is the application imported.* 

![demo/demo_01.png](demo/demo_01.png)

### Demo App on apex.oracle.com
[https://apex.oracle.com/pls/apex/f?p=ztsvg](https://apex.oracle.com/pls/apex/f?p=ztsvg)

uid: demo

pwd: demodemo
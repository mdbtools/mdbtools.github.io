---
layout: default
title: Frequently Asked Questions
---

Frequently Asked Questions
=================================


## What is an MDB ?

MDB databases are files produced by the Microsoft 'Jet' database engine. They are used in a variety of Microsoft products 
such as Money, Project, IIS, and Exchange as well as Accpac's Simply Accounting and Fog Creek's CityDesk, but most 
importantly, it is used as the format for Microsoft Access databases.


## What does MDB Tools do ?

MDB Tools is an open source suite of libraries and utilities to read (and soon write) MDB database files.


## What are the tools in MDB Tools ?

MDB Tools includes
- LibMDB, a library for accessing MDB files.
- MDB Utilities, a set of command line utilities to extract schema and data.
- MDBSQL, a SQL engine layered on top of LibMDB.
- MDB ODBC driver, a ODBC driver - requires unixODBC driver manager.
- gmdb2, a graphical interface including SQL query tool and file debugger.


## What license is MDB Tools under ?

The libraries in MDB Tools (libmdb, libmdbsql, and libmdbodbc) are licensed under the LGPL. The remainder 
of the software is license under the GPL.


## What Jet Databases does MDB Tools support ?

MDB Tools supports Jet version 3.0 and 4.0 databases. It does not, and probably never 
will support Jet 2.0. I'm looking into adding support for MSDE databases, and if anyone wants to send some 
sample databases in that format, we'd be very interested.


## Is there a roadmap ?

Roughly, the plan moving forward looks like this.

- Add index scan capability to libmdb and the SQL engine with a query plan generator.
- Add support for adding rows to existing tables and an mdb-import tool.
- Add full write support to libmdb and libmdbsql.
- Extract queries, table properties, VBA script, forms.
- mdb-check database consistancy checker and recovery tool.
- Add joins.
- Ability to add tables.

Of course these are my personal goals, and the direction of the project depends on contributors and feature requests from users.

## How do I install ?

Consult the [/install](installation) guide for details.


## I've found a bug

Post it to the sourceforge project page so it gets tracked and send a note to the list so we can 
work it out. I may request details about or a copy of your database. Any database sent will be kept confidential.


## How do I help ?
Join the mailing list, it's very low traffic at the time of this writing.

If you are a programmer, start with the debugger in gmdb2 to get a feel for the database layout. Read the 
HACKING file included in the distribution.

We are currently looking for corrupted Access databases to help with developing recovery tools. If you 
have them, I will even extract the usable data from them for you for free. ;-)


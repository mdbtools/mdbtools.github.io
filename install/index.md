---
layout: default
title: MDB Tools Installation Guide
---

# MDB Tools Installation Guide

## Overview

MDB Tools is composed of 

- three libraries
- a set of [command line utilities](/utils/) 
- and a graphical interface.


### LibMDB

libmdb is the lowest level library. It handles the details of reading from and writing 
to the MDB file format. Atop this library sits all the other functionality of MDB Tools.

A complete description of libmdb will be available in the forthcoming MDB Tools Programmer's Guide. For 
now you can look at the utility programs for a 
general idea of how to use the API, it's fairly straightforward.

### LibMDBSQL (the SQL Engine)

LibMDBSQL is an SQL engine which provides a subset of the SQL query language to access MDB databases. It is 
used with the ODBC driver, by the mdb-sql utility, and by the query window in gmdb2.

For a description of the supported SQL, see the mdb-sql man page.

### LibMDBODBC

LibMDBODBC is an ODBC driver that works with the unixODBC driver manager to allow MDB Tools to work 
with such programs as PHP and Perl (via DBD::ODBC). At the time of this writing, the breadth of 
coverage for the driver is rather limited. If you have specific problems with it, please contact the 
list and they can most likely be resolved.

The ODBC driver relies on LibMDB and LibMDBSQL.

### Gmdb2

Gmdb2 is a graphical interface to the functionality of MDB Tools. Its interface resembles that of 
access with a tabbed interface to each of the object types in the 
database (tables, queries, forms, etc...). Additonally, it sports an SQL Query window, and a file 
debugger useful for developers or anybody interested in examining the dark secrets of the MDB file format.

For information on how to use gmdb2, see the manual under the Help menu.

## Requirements

MDB Tools like any most packages has some requirements for libraries and such on your system. Most of 
them are optional and will turn off certain features if not present.

The following matrix lists all requirements and which features they affect. An X in the major 
feature categories (SQL, ODBC, gmdb2) means these features will be turned off if the prequisite is not found.


|Name       |SQL|ODBC|gmdb2|Source|Notes|
|-----------|:-:|:--:|:---:|------|-----|  
|glib 2.0   |X  |X   |X     |[gtk.org](https://gtk.org/)|Absolutely required, will not install without|
|readline   |   |    |      |http://cnswww.cns.cwru.edu/~chet/readline/rltop.html|Supports history in mdb-sql, will compile without history if not found.|
|bison      |X  |X   |      |[gnu.org](https://www.gnu.org/)|gmdb2 will not have a SQL window and mdb-sql will be stubbed out.|
|flex       |X  |X   |      |[gnu.org](https://www.gnu.org/)|gmdb2 will not have a SQL window and mdb-sql will be stubbed out.|
|unixODBC   |   |X   |      |[unixodbc.com](http://www.unixodbc.org/)| | 
|Gnome 2.0  |   |    |X     |[gnome.org](https://www.gnome.org/)| |
|libglade   |   |    |X     |[gnome.org](https://www.gnome.org/)|  | 
|wordexp    |   |    |      |               |Part of the OS, without it ~ expansion in SQL engine will be disabled|


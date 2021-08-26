# Hierarchical Database Model
*the first DBMS*
------
## General Information
+ maps the reality into a hierarchical tree structure
+ connections get realized by a parent-child-relation
+ every set has a predecessor except for the root
+ it is designed to show 1:N relationships - to split off repeating groups
+ it is extremely fast to read but the storage of data and its connections must be determined before
+ due to its weaknesses, this model is widely avoided nowadays
+ It is stil common in the economy and experiences a rennaissance due to ``XML`` (e``X``tensible ``M``arkup ``L``anguage)

  + it shows hierarchically structured data in a text-file

![alt text](https://github.com/CODERS-BAY/dbms-systems-LukeGrave/blob/main/HierarchicalDBMS/hierarchicalDBM.PNG "Hierarchical Database Model")
======
## How a XML-File looks like:
![alt text](https://github.com/CODERS-BAY/dbms-systems-LukeGrave/blob/main/HierarchicalDBMS/XMLstructure.PNG "XML Structure")
======
## Functionality
+ each entity set is part of one hierarchy
+ existing hierarchies are independent from each other, have no entity together and leads to redundancies
+ each root-type has a primary key
+ each entity needs to be accessable

   if you can access the parent, you can access the child but not the other way round - entry only via root

+ no child can exist without its parent --> **dataintegrity**

  + the connection node has to be set in before
   
  + deleting a parent will delete all children too

------
## IMS (Information Management System)
+ for data manipulation
+ IMS functions get called with a __*carrier language*__ (PL/1, Cobol, Assembler)
+ database access language: __*``DL/1``*__
+ Commands:

  + GU, GHU --- get unique (and hold)

  + GN, GHN --- get next (and hold)

  + GNP, GHNP --- get next within parent (and hold)

  + ISRT, DLET, REPL --- Insert / Delete / Replace

------
## examples of hierarchical data as relational tables

> ![alt text](https://github.com/CODERS-BAY/dbms-systems-LukeGrave/blob/main/HierarchicalDBMS/relation_employee_equipment.PNG "Employee uses Equipment") <br>
> An organization stores employee information. <br>
> Each employee is provided with computer hardware. <br>
> The equipment is only allowed to be used by its assigned employee.

<br>

The employee table represents the "parent" part while the computer table represents its "child" of the hierarchy. <br>
Children point to their parents - each employee may possess several pieces of equipment but there can only be one employee assigned to it.

<br>

> ![alt text](https://github.com/CODERS-BAY/dbms-systems-LukeGrave/blob/main/HierarchicalDBMS/employee_reportsTo.PNG "Employee reports to Employee") <br>
> Child is the same type as parent. <br>
> The foreign Key "``ReportsTo``" refers to the unique "``EmpNo``" Data.

------
## History of hieararchical databases
+ IBM introduced its format in the ``1960s`` for mainframe systems.
+ Mainframe Computers still use hierarchical databases.
+ IBM IMS is one of the most popular databases and was first designed for the __*Apollo Program*__.
+ IMS nowadays supports ``Java``, ``JDBC``, ``XML`` and ``web services``.

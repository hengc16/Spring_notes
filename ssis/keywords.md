# keywords

### SSIS Project:

* a versioned container for parameters and package 

### SSIS Package:

* A unit of task flow execution 
* A unit of deployment

###  Control Flow:

* it is the brain of package
* Decides the order of execution for all its components

### Tasks:

* individual units of work

### Precedence constraints:

* Directs tasks to execute in a given order
* Defines the workflow of SSIS package 

### Data Flow:

* it is the heart of package
* provides the capability to implements ETL

### Sources:

* A component which specify the location of the source data

### Transformation:

* Allow changes to the data within the data pipeline

### Destinations:

* A component which specify the destination of the transformed data.

### Variables:

* SSIS variables can be set to evaluate to a expression at runtime

### Parameters:

* Parameters behave much like variables but with a few main exceptions.
* it can make a package dynamic 
* it can be set outside the package easily
* it can be designated as values that must be passed in for the package to start
* Parameters are new to SSIS in SQL Server 2012 and replace the capabilities of configurations in the previous releases of SQL server.




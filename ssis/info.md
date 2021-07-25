# intro

### What is SSIS

* an ETL tool, ETL stands for Extract, Transform and Load.

### Why use SSIS

* don't need to write a line of code to import multi csv, flat file to database.



### Control flow:

one control flow can contain multiple data flow

![](../.gitbook/assets/image%20%28353%29.png)

### Data Flow :

design for data migration.

![](../.gitbook/assets/image%20%28340%29.png)

source -&gt; logic -&gt; destination

### Parameters:

For different database. Instead of change SSIS package. we can change the parameter. 

### Event handlers

most time to use as error handler.

OnError: handle errors. 

![](../.gitbook/assets/image%20%28343%29.png)

select task on excecutable section, and evenhandler on the right.

### Package Explorer:

![](../.gitbook/assets/image%20%28342%29.png)

### Variables

![](../.gitbook/assets/image%20%28347%29.png)

create variable to use at any tasks in this ssis package. 

### Connection Managers

![](../.gitbook/assets/image%20%28339%29.png)

### Solution Explorer

![](../.gitbook/assets/image%20%28348%29.png)

### what is SSIS 

 A **SQL Server Integration Services** \(SSIS\) package includes the necessary components, such as the connection manager, tasks, control flow, data flow, parameters, event handlers, and variables, to execute a specific ETL task.




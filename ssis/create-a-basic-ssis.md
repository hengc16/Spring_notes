# create a basic ssis

### data generator:

{% embed url="https://mockaroo.com" %}

### 

### Process

Load data from a CSV file to database.

### Create a flat file source

* create a data flow task 
  * create a flat file source
    * edit-&gt; create a flat file connection.

![](../.gitbook/assets/image%20%28346%29.png)

### create a OLE DB destination 

* create new connection
  * give the sql server name
  * select datebase name 
  * select data access mode 
    * fast load

### Done

![](../.gitbook/assets/image%20%28352%29.png)

click on package, and execute the package.


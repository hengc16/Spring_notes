# pipeline

### Pipeline:

* pipeline in Devops is a set of process\(automated or can be triggered manually\) which is used to make available your project code to users.

### Azure pipeline:

* Azure pipelines is a cloud service that you can use to automatically build and test your code project and make it available to other users.

### CI/CD:

* CI continues integration: CI is used to automate tests and build for the projects. It is used to find bugs or other build issue in early phase.
* CD \(continues Delivery\): CD is used to automatically deploy and test code in multipage stages\( environments like dev, qa, staging etc.\) to maintain the quality. 

keywords: 

### Agent:

![](../.gitbook/assets/image%20%28349%29.png)

### Approvals:

![](../.gitbook/assets/image%20%28344%29.png)

### Artifacts:

![](../.gitbook/assets/image%20%28352%29.png)



### environment:

where we deploy our application.

![](../.gitbook/assets/image%20%28345%29.png)

### Job:

![](../.gitbook/assets/image%20%28338%29.png)

### Run:

* one execution of pipeline\(build or release\) is known as run.

### stage:

* a stage is used to mark separation of concerns.
* example = creating build for QA, Staging, Production etc. 
* stage is very important in adding an extra validation before your code goes to production. 

### Trigger:

* A trigger is a setup that tells the pipeline when to run.
* we can configure a pipeline when-
  * new push in repo
  * at scheduled time
  * upon completion of another build.


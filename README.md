# Tableau Prep Conductor Example


This demo shows you how to use Tableau Prep Builder to work with a Tableau Prep Conductor enabled Tableau Server (Version 2019.1 or later).

## Requirements ##

* Tableau Prep Builder
* Tableau Server - enabled with Tableau Prep Conductor or the Data Management Add-on.
* Microsoft SQL Server 

## Data Source for Example ##

https://www.health.mil/Military-Health-Topics/Technology/Support-Areas/Geographic-Reference-Information/DMIS-ID-Tables


## Instructions ##

* Download the latest monthly DMIS table
* Insert into a new table on your available Microsoft SQL Server database.

### Open Tableau Prep Builder ###

* Start your Prep Flow by connecting to Microsoft SQL Server.   
* Once you've dragged your data source (in this instance ref_dmis) to the flow, create an output object.
  * Change the output destination from 'Save to file' to 'Publish' as a data source.'


![Connect to MS SQL Server](img/prepbuilder_step1_connect.png)

![Create your flow](img/prepbuilder_step2_createflow.png)

![Execute flow](img/prepbuilder_step3_execute_and_check.png)



![Publish flow menu](img/prepbuilder_step4_publishflow_menu.png)
![Check connections setup](img/prepbuilder_step5_publishflow_setup.png)
![Check out the flow on the server](img/prepbuilder_step6_doublecheck_on_server.png)
![Run your flow](img/prepbuilder_step7_runflow.png)
![Watch the pending status](img/prepbuilder_step7_pending.png)
![We have an error](img/prepbuilder_step8_error.png)
![Check your connection error](img/prepbuilder_step9_checkconnection.png)
![Edit the connection](img/prepbuilder_step10_editconnection.png)
![Change the port to 1433](img/prepbuilder_step12_editport.png)
![Eureka - success!](img/prepbuilder_step13_success.png)
![Create a task schedule for the flow](img/prepbuilder_step14_createschedule.png)
![Look over your tasks in the scheduler](img/prepbuilder_step15_checktasks.png)
![Click on the flows tab](img/prepbuilder_step16_checkflows.png)


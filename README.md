# Tableau Prep Conductor Example


This demo shows you how to use Tableau Prep Builder to work with a Tableau Prep Conductor enabled Tableau Server (Version 2019.1 or later).

# Requirements #

* Tableau Prep Builder
* Tableau Server - enabled with Tableau Prep Conductor or the Data Management Add-on.
* Microsoft SQL Server (or a CSV/Flat File) - In this example MSSQL is used.

# Data Source for Example #

https://www.health.mil/Military-Health-Topics/Technology/Support-Areas/Geographic-Reference-Information/DMIS-ID-Tables

# Instructions #

* Download the latest DMIS ID Monthly Downloads Zip File.
  * Unzip the file into your local project folder.
  * The file name should be something like this: 202006_dmisid_June2020.xlsx
* Insert into a new table on your available Microsoft SQL Server database.

# Open Tableau Prep Builder #

* Start your Prep Flow by connecting to Microsoft SQL Server. 
* Connect to your Tableau Server

# Connect to the SQL Server & Create a new Flow #

![Connect to MS SQL Server](img/prepbuilder_step1_connect.png)

# Build Your Flow #

* Once you've dragged your data source (in this instance ref_dmis) to the flow, create an output object.
  * Change the output destination from 'Save to file' to 'Publish' as a data source.'
  * Set the destination project folder on your Tableau Server.
  * Make sure you use good documentation on your flow for the object name & description since other analysts will see this.

![Create your flow](img/prepbuilder_step2_createflow.png)

# Execute the Flow #

* It's time to run the flow.   Run it from Tableau Prep Builder on the desktop and verify that the flow works correctly locally before moving onto publishing the flow on the Tableau Server.
* If successful, you will see the hyper output published on the remote server in the destination project. (default in this example)


![Execute flow](img/prepbuilder_step3_execute_and_check.png)

# Publish your flow to the Tableau Server #

* Publish your flow to the Tableau server.  __Note - This is the flow itself, not the data that the flow creates!__
* Prep Builder > Server Menu > Publish Flow (F10)

![Publish flow menu](img/prepbuilder_step4_publishflow_menu.png)

# Check over your flow setup #

* Double check your connection to the MSSQL db.   Use your security best practices.  In this situation the flow (tfl) uses an embedded password.
  * Click 'Edit' next to Connections and double check your 'Authentication' settings. 
  * **IMPORTANT** - IF you are using a Excel/Flat File (CSV) instead of MSSQL, use direct connections instead of uploading the file to the server.
* Once publishes your default browser will open up and you'll see the flow directly in the browser.

![Check connections setup](img/prepbuilder_step5_publishflow_setup.png)

## CSV/Flat File Set Up ##
![Flat file setup](img/prepbuilder_step5_directfile_connects.png)


# Check Out Your Flow on the Tableau Server #

Your browser should automatically load the flow on the Tableau server.

![Check out the flow on the server](img/prepbuilder_step6_doublecheck_on_server.png)

# Execute the Flow on the Tableau Server #

Run the flow directly from the browser.

![Run your flow](img/prepbuilder_step7_runflow.png)

# Watch for the Pending Status #

![Watch the pending status](img/prepbuilder_step7_pending.png)

# Flow Error Detected #

Uh oh, we have an error! The flow has failed and likely generated an email to you in your email inbox stating a failed flow run.
Examine your flow and see where the issue is.

![We have an error](img/prepbuilder_step8_error.png)

# Check Your Connection to the SQL Server #

* Correct the error by adding a port 1433 to the MSSQL db.   If your MSSQL uses a different port than the default, use that one instead.  Ask your MSSSQL DBA for that information.  But try 1433 first.

![Check your connection error](img/prepbuilder_step9_checkconnection.png)

![Edit the connection](img/prepbuilder_step10_editconnection.png)

![Change the port to 1433](img/prepbuilder_step12_editport.png)


# Test and Verify the Fix #

* Click the test connection button and verify that the Tableau server can successfully reach the MSSQL db.
* Run your flow again and check for a successful run.


![Eureka - success!](img/prepbuilder_step13_success.png)

# Set up a Tableau Server Task Scheduler #

* Now that you know that your connection is working, it's time to schedule it to automatically update. Depending on your needs, you may need to set up a separate process to upload the data onto MSSQL.   Tableau Prep Builder 2020 will have new feature capability to export data from an external source to MSSQL, not only hyper or CSV outputs.   

![Create a task schedule for the flow](img/prepbuilder_step14_createschedule.png)

# Optional - Check out your tasks in the Tableau Server Scheduler #

* (Optional) You can see your task that you schedule in the Tableau Tasks.

![Look over your tasks in the scheduler](img/prepbuilder_step15_checktasks.png)


![Click on the flows tab](img/prepbuilder_step16_checkflows.png)


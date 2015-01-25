Overview and the Env app
========================
The DISC Server is a collection of apps (as defined by Django).
There is one app to define data.  The other apps help to configure sources of data and create actions from the data.
The server also provides for users and groups.

The DISC Server uses the "Env" (Environment) app to define and store all the time series data.
It also defines the controllers.  All the other apps will use implicit (or soft) links to the env information.
This makes sure that various apps that consume the data have a standard interface even when there are different sources of data.
The env app also provides a few convenient features.  It provides a list of the latest data as well as statistics and methods to plot the data.

Logging HTML Table data from the National Weather Service
=========================================================
If the server is running on localhost, port 8000, open <http://localhost:8000/disc/admin>
Log in with an admin account
This link should put you in the DISC Server Administration

Define the Controller
-----------------------
In the "Env" section, click on "Controllers"
Click on the one controller listed "LocalController"
Note the configuration items for the controller.  This configuration allows the server to communicate with the controller.
It also allows us to link data streams to a controller.
When a controller is started, it will read its configuration from the DISC server.

Add URL of the HTML Table
--------------------------------
In the Htmltable section, click on Html tables
Click on ID 1 to view the configuration of the HTML Table

Add an HTML Table cell Sensor
-------------------------------
In the Htmltable section, click on Sensors
Click on ID 1 to view the configuration of the sensor
Note that the sensor data is linked to a DataID.
The DataID can be pre-entered before setting up the HTML Table Sensor or it can be added 'on the fly' by clicking the green '+'.

In order to get the row and column:

Copy the National Weather Service URL from the HTML Table ID 1
Look in http://localhost:8000/disc/admin/htmltable/htmltable/

Now open the following link in a new tab
http://localhost:8000/disc/htmltable/parse_and_index_htmltable
Paste the URL into the box and click submit
The tables in the webpage are extracted and enumerated with row and column indexes.
The index of a table is the upper left number on each table.
The row and column indexes for a table are across the top and left side of the table data.
Use these indexes to specify which cell data should be logged by the controller and disc server.

Add Data Types
---------------
In the section "Env", click "Data types".
If the DataType that you want to use is not listed, click 'Add data type' in the upper right corner.
Fill out the form for the new Data Type.

Add Data Definition
-------------------
In the section "Env", click "Data".
Click 'Add data' in the upper right.
Fill out the form for the new Data item.




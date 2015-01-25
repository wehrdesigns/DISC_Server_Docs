Introduction Notes
==================
DISC is an acronym for Distributed Intelligent Sense and Control.  There are centralized elements of the system with more computing power that handle complex functionality but also distributed elements that handle more simple functions.  A goal is to make sure most of the system can be remotely managed.  Another goal is to make sure that critical control and data logging functions operate when temporarily disconnected from the network.  Another goal is to keep the system very reliable and the cost low.

Time Series Data
----------------
The DISC Server is centered around timeseries data that is pre-filtered so that it can quickly and easily be analyzed and used to make decisions.  The server can handle many channels of data even with a low cost computer such as the raspberry pi or beaglebone.  The server must filter and store the data as well as retrieve it to drive actions and alerts.  Fifty data channels recorded at 1 point per minute will be 72000 points per day.  That many data points can be costly to store in the cloud.  Performing statistical operations every few minutes on that data is even more costly to perform in the cloud.  If you need high performance, just install the DISC Server on an old computer (faster than a raspberry pi) and use the raspberry pi as a remote data logger so that you don't loose any data when you reboot the server.

Metric Chimes
-------------
This is a fun use of the DISC system.  An hourly chime is nice, so why not keep track of your environment on the hour?  Use the action lab to create statistics about your environment and have them sent as an SMS.  This is very neat with a smartwatch.  Here are some suggestions:
*	At 9am be notified about how much hot water was used for the morning shower(s)
*	At 10am be notified about how well you rested
*	At 11am be notified about when you turned off the light in your room last night
*	At noon be notified when the sunrise light level was bright enough to easily read a book
*	At 5pm be notified about how much activity there was in the office during the last 9 hours
*	At 8pm be notified of the electricity cost for the last 24 hours
*	At 9pm be notified of the average temperature/humidity/windspeed for the day

Considerations
--------------
*	The present version of this documentation expects that the user has some advanced computer skills.
*	The user should be able to install python and python packages.
*	The user will have to use the command line and possibly modify commands in this documentation to suit the configuration of their computer.
*	Building a samewire network will require basic electronics skills.
*	If you find a bug or want a feature, dive in and add it yourself for the good of all.  If that doesn't work for you, then encourage the developers as they improve it for you.  Be thankful for the work in progress!

For developers
--------------
A goal for the DISC System is to provide a few core apps that can be used by plug-in apps.  Hard links are convenient during early development but create complex dependencies as the system grows.  Efforts have been made to identify core functionality and provide for soft links between other apps.

What can I do with the DISC system?
===================================
The author has only listed things that he has done with the system.  Your needs may find new purpose for these tools.  The author hopes that some may use their skills to develop completely new features for the system whether it be hardware or software.

Log data from an HTML Table
---------------------------
Data can be collected from any html table for which the table and cell indexes do not change in the page.

A good example is logging National Weather Service Forecast data.  The author records the 3,6 and 12hr forecast data.  He configures the system to send alerts such as:
*	when the windows should be open or closed for best efficiency in cooling
*	when there might be frost
*	when cold temperatures and high winds might freeze pipes

You might record data from other measurement systems that present their data in a webpage with an html table.  Maybe you don't have logging and graphing capability on the other system or you want to combine data from both systems in order to create more intelligent alerts.  You might want to control functions connected to the DISC System with input data collected from another measurement system.


Action Lab
----------
Write python scripts that analyze your data and decide when to perform actions or notify you when certain conditions occur.  There are examples as well as convenience functions written for getting data and sending emails, etc.  The server does not need to be restarted when changing an action lab script.  The server checks for a new time stamp and automatically reloads the script.  The script can even be edited remotely in a web browser.


Operate a Samewire network
--------------------------
This is a two wire network.  One wire is ground and the other carries power and communication.  The distribution is point to multi-point.  A network has one master and one or more serfs.  Each serf has an address so that it only responds to commands intended for it.  The master and serfs can be configured with a serial terminal or (using the DISC system) through a web browser.  Linear calibration values can be written to the serf so that calibration stays with the hardware.  The serf firmware has adjustable filters to help reduce sensor noise.  The serf firmware can be a completely local control system.  Sensor inputs can control digital outputs with configurable thresholds and hysteresis.

Measure
^^^^^^^
*   Analog (Temperature, Humidity, Battery Voltage, Pressure Sensor)
*   Digital (PIR Motion, Switch State)
*   Capacitance (Light Level, Humidity)
*   Timing (Wind Speed, Blood Pressure Pulse Sensor)
*   AC Power Monitor (AC Voltage, AC Current)

Control
^^^^^^^
*   LED Indicator
*   Digital Outputs

Filter Inputs
^^^^^^^^^^^^^
Filter input data with a moving average

Use thresholds (with hysteresis) for analog inputs to drive digital outputs
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
*   Link an output to be controlled by an input
*   Define how the output is controlled by the input
*   Set thresholds for the output to be changed by the input
*   Use hysteresis with the thresholds
*   Set the frequency that the output value is updated


Monitor and Control a Thermostat that has serial port programming access (such as RCS TR 40)
-------------------------------------------------------------------------------------------
This system was designed using the RCS TR 40 Thermostat but could be adapted to other thermostats that are programmable through a serial interface.


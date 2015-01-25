Running the demo
================
The DISC Server that you download from Github will be setup to easily run a demo.

Start the DISC Server
---------------------
Open a new terminal.
*Change to the folder disc and run:*::
	python runserver.py &

The server is configured to run on port 8000, which can be changed in the file:
disc/user/config.json
The parameter is: HTTP_PORT

Start the Controller
--------------------
Open a new terminal.
*Change to the folder disc/controller and run:*::
	python controller.py &

The controller also has a web server and is configured to run on port 11111
Settings for the controller are in the file disc/controller/settings.py

Login to the DISC Server
------------------------
Login with user 'admin' and password 'admin'
If the web browser is running on the same computer as the server use the link:
<http://localhost:8000/disc/admin>

The admin account has super user priviledges so be careful which links you click on.
If you prefer to explore with less power, log in with user 'guest' and password 'guest'.

Look at the tutorial for more info about how the demo was configured.

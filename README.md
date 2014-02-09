Raspberry Pi Garage Door REST server

Used to control an automatic garage door opener, features include:

* Activate door open/close/stop
* Email notification when door remains open for a set period
* Sensing door state changes

Technologies / Architecture / Design
====================================

Bottle to manage REST service http://bottlepy.org/
RPIO Raspberry Pi GPIO to control/sense door state https://pypi.python.org/pypi/RPIO
sqlite database to store state
Google Web Toolkit (GWT) browser interface [TODO link to project]
Google OAuth reverse proxy (written in GO) [TODO link to project]

user ----> router [port forward] ----> oauth proxy ----> py_garage_server ----> garage.db
                                                                        \-----> GPIO -----> Relay/Sensors

If not requiring external access or for testing can go directly from 
user to py_garage_server by disabling auth in config (see below)
																		
Electronics
===========

Build the electronics - see README and diagrams in the electronics folder

Browser app
===========

Download garagecontrol-client.zip from https://github.com/drweaver/gwt_garage_control/releases/latest

Put file in www folder and unzip: 
$ unzip garagecontrol-client.zip .

It should create following file structure:
www/GarageControl.html
www/ico/[several images]
www/garagecontrol/[gwt javascript files] 

Dependencies
============

TODO: RPio, sqlite, python3, google oauth, geopy, bottle etc

Configuration
=============

TODO: auth (setup/disabling/location), email, etc

Running
=======

TODO: command-line, system service/init.d

Authentication
==============

TODO: upload files and add details of google oauth

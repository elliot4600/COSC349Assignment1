# COSC349Assignment1
COSC349 Assignment 1 README

This VM application makes use of the following tools to run. They can be downloaded from the links below, and their approximate download size is also displayed (for the latest versions as of September 2020). 

Vagrant:
https://www.vagrantup.com/downloads 
Download size: 30-40MB for Mac OS X & Linux, ~240MB for Windows (64-Bit) 

Virtualbox:
https://www.virtualbox.org/wiki/Downloads 
Download size: 100-120MB 

To use this application, clone the repository using git with this command:
git clone https://github.com/elliot4600/COSC349Assignment1.git

Alternatively, this repository can be downloaded as a .zip folder from:
https://github.com/elliot4600/COSC349Assignment1/archive/master.zip


After cloning/downloading the repository, navigate to the directory of the repository.
Run the command below to initialise the VM's using vagrant:
vagrant up --provider virtualbox

The public can access the library contents page at the URL:
http://127.0.0.1:8081

The library administration can edit the database contents and add new books at the URL:

http://127.0.0.1:8080
For database purposes, the user and password are both "admin"

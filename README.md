![CarRental](logo.png)

Car Rental Minimal App
===========================

A car rental management minimal app in Bash.

Contents
-----
  1. [Planning](#planning)
  1. [Design](#design)
  1. [Development](#development)
  1. [Evalution](#evaluation)

Planning
----------
### Definition of the problem
A car rental office wants to buy a computer program that can record all their information about their cars. This Program will help the clients to record the car that they took and how long their trip was and the history of the car for all its trips. They require the program to be simple so that it wouldn’t confuse the users and the owners of the company. For the program to be simple, it needs to contain simple commands which can be used by anyone without needing any instructions from the program designer. This program needs to be delivered to the company in the simplest way possible. Every time that they use their program, all their data need to be saved so that they could recall it later for more information. This program will store all their data which makes them keep track of their financial system. 

Design
---------
### First Sketch of System
![CarRental](System.jpg)
**Fig. 1** This diagram shows the main components of the minimal 
rental app. It includes the input/output and main action.

### Second Sketch of system
![CarRental](prosys.jpg)
**Fig. 1** This diagram creates a frame on the important words
that the program will use. 

Development
--------
### 1. Script for installation
The script below creates the folder structure for the application
```.sh
#!/bin/bash

#this program creates the folder structure for the minimal rental app

echo "Starting Installation"
echo "Installing in the desktop (default). press enter"
read
cd ~/Desktop

#Create app folder
mkdir RentalCarApp

cd RentalCarApp

mkdir database
mkdir scripts
echo "Installation complete successfully"

```
### 2. Script for uninstallation
This script below will delete the created folders for the minimal rental app
```.sh
#!/bin/bash

#this program will delete the created folders for the minimal rental app

echo "Starting to uninstall"
echo "uninstalling in the desktop (default). press enter"
read
cd ~/Desktop

rm -r RentalCarApp


echo "uninstallation complete successfully"
```

This script meets the requirement of the client for a simple installation and uninstallation 
however, it could be simplified so that the user does not need to execute the program by typing ``bash install.sh``

###problem solving
1. How to detect a word's length is odd or even?
  A. you use the module sign which is %, and this sign will show if the length of the word is even or odd. We also use if statement with the module sign and it can be state it this way. len which is the length of the of the word % 2, if the outcome is 1 then the word is odd if its 0 then the word is even. 

### Developing the action create new car
This process involves the inputs _,_,_,_, and the outputs:
the following steps describe the algorithm
1. Get the input as argumanets `$1 $2 $3 $4`
2. check number of argumetns (4) `$#`
3. Store new car inside `Maincarfile.txt`
4. create file for recording trips as plate.txt
`echo "Lxq912 nissan 2000 8" >> Maincarfile.txt`
`echo " " > plate.txt`
### Developing the action of recording trip
1. get the arguments and check (2)
2. check that the car exist `test license.txt`
3. add a new line to the file `license,txt`
4. end

Evaluation
-----------




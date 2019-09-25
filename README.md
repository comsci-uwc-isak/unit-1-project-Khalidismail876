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
This script meets the requirement of the client for a simple installation 
however, it could be simplified so that the user does not need to execute the program by typing ``bash install.sh``

Evaluation
-----------




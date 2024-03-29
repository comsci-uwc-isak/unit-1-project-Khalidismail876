![CarRental](logo.png)
```.py
Marks= 18
Demo=-
Total=(Marks+Demo)= 18
```
**Graded on Nov 8**

Car Rental Minimal App
===========================

A car rental management minimal app in Bash.

Contents
-----
  1. [Planning](#planning)
  2. [Design](#design)
  3. [Development](#development)
  4. [Evalution](#evaluation)

Planning
----------
### Definition of the problem (update this part)
A car rental office wants to buy a computer program that can record all their information about their cars. This Program will help the clients to record the car that they took and how long their trip was and the history of the car for all its trips. They require the program to be simple so that it wouldn’t confuse the users and the owners of the company. For the program to be simple, it needs to contain simple commands which can be used by anyone without needing any instructions from the program designer. This program needs to be delivered to the company in the simplest way possible. Every time that they use their program, all their data need to be saved so that they could recall it later for more information. This program will store all their data which makes them keep track of their financial system. 

### Proposed solution
The car rental office proposed a simple program that would keep track on all their informations and sustain their financial system. So to make their program simple, I created an easy install and uninstall program that can make them use the program in their computers or remove it if they want. After they install, everything they need will be in the folder that would be provided and everything is simple and easy with just one step process. The language that I used is bash script, the reason why I chose the bash script is because it's in the computer and you don't need to install it from somewhere else. Overall, the program is simple as the car rental office proposed and it will help all their needs. 

### Success Criteria
These are outcomes that can be measured
1. A car can be created
2. A trip can be recorded for a given car
3. A summary (Total distance traveled, average) of trips can be requested
4. A car information can be edited
5. A basic working backup system is available
6. The user can easily (name notation, documantation) understand the commands
7. Installation is **simple**, it does not require additional software, one step process
8. A car information can be deleted
9. The application can be uninstall

**Criterion A**

|Level|Descriptor|
|----|-----|
|5|The client in the car rental office is identified and his situation described. The rationale for choosing the proposed product (Computer tools used) is justified and includes a range of appropriate criteria for evaluating the success of the product.|
```.sh
Rational
* Great job with this criterion. You could improve the definition of the problem by answering the questions: Who is the client? Why is the product being developed?
* You are missing marks because the justification for the solution is not specific and clear enough. You say it is a simple system, what do you mean by that, how does the solution solve the clients problems?
* One more justificaiton for using BASH is that we were learning it. 
```

Design
---------
### First Sketch of System
![CarRental](System.jpg)
**Fig. 1** This diagram shows the main components of the minimal 
rental app. It includes the input/output and main action.

### Second Sketch of system
![CarRental](prosys.jpg)
**Fig. 2** This diagram creates a frame on the important words
that the program will use. 

### Third Sketch of the system
![CarRental](Sketchhh.jpg)
**Fig. 3** This diagram backsup all the data that we need to restore.

### Test Plan
![CarRental](table.png)
**Fig. 4** This table shows the test of all scripts in the program.

## Criterion B
|**level**|**Description**|
|-----|------------|
|5|An outline test plan is included but partially complete. A system diagram and some flow diagrams for algorithms in the product are included. They provide a basic understanding of how the product was developed.|
```.sh
Rationale
* You can use the figure as a reference point and refeer to it with Fig. 1. For example: "As shown in Fig. 1, the computational system consists of ..." This is necessary to be concrete about the reason from including the picture.
* Here you did not get all the full marks because you are missing the description. Remember, an image without description is an unbiguous tool. Add a paragraph explaining what YOU see in the image and the reason why you included. This will help the reader follow your ideas. 
* The system diagram needs an uptaded version. It is difficult to follow.
* The flow diagrams have problems with the symbols. We use rectangles, diamonds, and the other two symbols because they are standard representations of computer operations. When you use different symbols is difficult to follow your ideas.
```

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
cp -r ~/desktop/Carapp/scripts/ ~/desktop/RentalCarApp/scripts/

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

### problem solving
1. How to detect a word's length is odd or even?
  A. you use the module sign which is %, and this sign will show if the length of the word is even or odd. We also use if statement with the module sign and it can be state it this way. len which is the length of the of the word % 2, if the outcome is 1 then the word is odd if its 0 then the word is even. 
  
### 3. Script for Frame
This code shown below will create a frame around the word that is given

```.sh
#!/bin/bash

word=$1
len=${#word}
padding=3


#lenght of the frame
width=80
(( spaces=$width/2-$len/2-1 )) 

# Print a whole line with symbol
for (( i=0; i<$width; i++ ))
do
	echo -n "#"
done
echo " " #this is for going down one line 

#prints the padding
for (( p=1; p<padding ; p++ ))
do
	echo -n "#"
	for (( s=0; s<$width-2; s++ ))
	do
		echo -n " "
	done
	echo "#"
done

#line for the word
echo -n "#"
for (( s=0;s<$spaces;s++ ))
do
	echo -n " "
done
echo -n $word

if [[ $(( $len%2 )) -ne 0 ]]; then
        (( spaces=$spaces-1 ))

fi
for (( s=0;s<$spaces;s++ ))
do
        echo -n " "
done
echo "#"

#prints the padding
for (( p=1; p<padding ; p++ ))
do
        echo -n "#"
        for (( s=0; s<$width-2; s++ ))
        do
                echo -n " "
        done
        echo "#"
done

#print bottom frame
for (( i=0; i<$width; i++ ))
do
        echo -n "#"
done
echo " " #this is for going down one line 
```

### Developing the action create new car
This process involves the inputs _,_,_,_, and the outputs:
the following steps describe the algorithm
1. Get the input as argumanets `$1 $2 $3 $4`
2. check number of argumetns (4) `$#`
3. Store new car inside `Maincarfile.txt`
4. create file for recording trips as plate.txt
`echo "Lxq912 nissan 2000 8" >> Maincarfile.txt`
`echo " " > plate.txt`
 
 Coding 
```.sh
#!/bin/bash

if [$# -ne 4 ]; then
	echo "Error with the number of arguments"
	echo "Enter LIcense Maker Model Passengers"
	exit
fi
lIcense=$1 
maker=$2
model=$3
pp=$4

echo "$license $maker $model $pp" >> db/maincarfile.txt
echo "" > $license.txt
```

bash frame "Installation Complete"
### Developing the action of recording trip
This code will record all travelled Km in the car file that is created.

1. get the arguments and check (2)
2. check that the car exist `test license.txt`
3. add a new line to the file `license,txt`
4. end

coding
```.sh
#!/bin/bash

if [ $# -ne 2 ]; then
	echo "Error with the number of arguments"
	echo "Enter License distance"
	exit
fi

km=#2
license=#1
#check if the file exist
if [ ! -f "$license.txt" ]; then
	echo "Car does not exist"
	exit
fi
echo "$km" >> ../database/$license.txt
bash frame "Trip recorded successfully"
```

### Developing the action of Summarizing the traveled trip
This code will sum all the km that is stored in car file and give 
the used one number.

1. Get the argument (bash Summary.sh license)
2. Check if the car exists 
3. show the all the travelled KM
4. Add all the travelled KM and show the sum

The coding for this program is shown below.
```.sh
#!/bin/bash

#This is an example script that solves the smaller
#problems for the action summary
#1. Read a txt file line by line
#2. split a line by spaces
#3.add the first word in the line

if [ $# -ne 1 ]; then
  echo "Car doesn't exist"
  exit
fi
license=$1
FILE="../database/$license.txt"
totalkm=0
while read line
do
  echo $line
  #Bash splits a line by spaces
  for word in $line
  do
    echo $word
    ((totalkm=$word+$totalkm))
    #add all the km
    break
  done
done < $FILE
#4. show very nicely the total km traveled
bash frame "Total Km Traveled $totalkm"
```

### Developing the action of backingup the data
This code will restore all the data they prevous had in RentalCarApp to a created folder
called backup.

1. Go to Desktop (cd ~)
2. check if there is a file named Backup 
3. if the file exist then delete
4. create folder called Backup and within that folder create sub-folders called database and scripts
5. copy everything from RentalCarApp to Backup

The Code shown below described everything. 
```.sh
#!/bin/bash

# This program creates a backup of the database folder in the app folder

# Starting
echo "Backup starting"

# Navigate to the desktop to create a new folder (backup/)
cd ~/desktop/
# If theres already a folder called "backup", it is removed
rm -r ~/desktop/backup
mkdir backup
# Creats subfolder (backup/dataBase/)
cd backup
mkdir database
mkdir scripts

# Copies all (*) the files from the dataBase folder to the new folder (backup/) and subfolder (backup/dataBase/)
cp -r ~/desktop/RentalCarApp/database/ ~/desktop/backup/database/

cp -r ~/desktop/RentalCarApp/scripts/ ~/desktop/backup/scripts/

cp -r ~/desktop/RentalCarApp/ ~/desktop/backup/
```

### Developing the action of editing files
This code will allow the user to edit and change the data they stored in the car file.

1. Get the input as argumanets `$1 $2 $3 $4`
2. check number of argumetns (4) `$#`
3. Go inside database
4. find the car with given license
5. Change anything from that file

The code shown below shows the process
```.sh
#!/bin/bash
#This program edit the information of an exiting car in the
#maincarfile
#user enters [license place] [model] [red] [pp]

if [ $# -ne 4 ]; then
  echo "Error with the number of arguments"
  echo "Enter License Maker Model Passengers"
  exit
fi

license=$1
maker=$2
model=$3
pp=$4

cd ../database

if [ ! -f "$license.txt" ]; then
  echo "File not found!"
fi

#find the line with the given car plate and delete it
sed -i '' "/^$license/d" maincarfile.txt
#add the new information
echo "$license $maker $model $pp" >> maincarfile.txt
cd ../scripts
bash frame "Car edited successfully"
```


### Developing the action of deleting file
This code will delete a car file from database and inside maincarfile. 

1. Get the input as argumanets `$1 
2. check number of argumetns (1) `$#`
3. Go inside database
4. find the car with given license
5. remove the car file from database and inside the maincarfile.txt

The code below shows how the it works
```.sh
#!/bin/bash

#this program delete a car given one argument
#licences

license=$1
if [ $# -ne 1 ]; then rm -rf
        echo "error with the number of arguments"
        echo " enter license"
        exit
fi

cd ../database
#check if the .txt  file exist
if [ ! -f "$license.txt" ]; then
        echo "file doesn't exist"
        exit
else
        rm $license.txt
        sed -i '' "/^$license/d" maincarfile.txt
fi

cd ../scripts
bash frame "car deleted successufully"
```

### Developing Help files
We will be using man pages to create a help file, almost all UNIX like oses comes preinstalled with man pages. Its a document processing system developed by AT&T for the Unix operating system. 
This program below shows how the Help files is structured using create.sh program. 

```.6
.TH man 6 "29 oct 2019" "1.0" "create man page"
.SH NAME
Create \- Create a new car
.SH SYNOPSIS
bash create [license] [model] [color] [passengers]
.SH DESCRIPTION
Create is bash program that allows to create a new in bash
.SH AUTHOR
Created by Ismail Khalid
```

### Tools used in Unit 1
1. Bash Commands (Used)
2. For loops (Used)
3. If statement (Used)
4. Man pages/help files (Used)
5. GitHUb (Used)

## Criterion C
|**level**|**Description**|
|-----|------------|
|5|The proposed solution is characterized by the appropriate use of existing tools. The techniques are adequate for the task and their use is explained. All sources are identified.|
```.sh
Rationale
* You also need description here about the important parts of the code, such as things you learned for the first time, issues and solutions.
* Try to use the references in body of the document in the place where you use the information, for example, when researching solutions to the problems you faced," As presented in [1], bash can be frustrating..."
* The tools used in Unit 1 need description. Listing is not sufficient. Why those tools and no other tools?
```

Evaluation
-----------
Test 1: A car can be created and stored in the database
For this purpose we will create the file testcreate.sh. This is called software testing 

The first step is to check for the file

```.sh
#!/bin/bash

#This file checks if the action create successfully addsa new car.

#step 1: navigate to the folder containing the create.sh file
cd ../scripts/
if [ -f "create" ]; then
        echo "File exists, test will start now"
else
        echo "File create.sh doesn't exist. Test Failed"
fi

#step 2: Use the create script to record a new car TXM901 nissan red 9
bash create TXM901 nissan red 9

#step 3: check that a txt file was created inside the database folder with
#the license number
cd ../Database
if [ -f "TXM901.txt" ]; then
        echo "Test One: File with the license place created successfully. passe$
else
        echo "Tes one: file with license number not found: failing"
fi
```

This file check all the criteria.

This test corresponds to dynamic, alpha, and white box test. The reason why it corresponds to those three tests is
because all of them require a person who knows how the program is designed or the person who actually designed it. 
For the dynamic test, you need to excute the programming code and test it with a set of given cases. For the alpha testing
you need the developers to use the program and see if it actually works or not. White box test is the last test that have been used which is examing the code that is used to create the program. All these types of testing is used for this program. 

### future updates
When this program is launched, it will contain a lot of things that the users will request to be impoved and we will improve it depending on their requests. One way we could improve this code is to make as one application and make the user press buttons instead of running codes. Also creating a program that scans QR of the cars would help the company be easier to keep track their data. providing a carriable device that would help the drivers put all the data of the car they drove would smooth the process of the company. More updates will come depending on the need that the users want to get. 

## Criterion D
|**level**|**Description**|
|-----|------------|
|3|The product is fully evaluated against the success criteria identified in criterion A. Recommendations for further improvement of the product are realistic.|
```.sh
Rationale
* The Improvement is realistic. 
*The evidence for the achievement of the criteria is limited so you lost some marks here. Next time, try to expand of the reasons/evidence that allows you to say that you have met the success criteria. Writing "This file check all the criteria" is not sufficient
```

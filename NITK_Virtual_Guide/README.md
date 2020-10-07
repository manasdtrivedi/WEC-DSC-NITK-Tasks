# NITK_Virtual_Guide
## Description
The project 'NITK_Virtual_Guide' is a Java application that accesses a MySQL database, which shall act as a guide for individuals who are interested in knowing more about NITK.

There are the following four modules in the application:
* News
* Events
* Mess Menu
* Map

In the News module, the news items are listed in the form of news titles, in decreasing order of date of upload. Upon clicking one of the items, the user is led to a page which has the details of the news item i.e. the title, date of upload, and the news content.

In the Events module, the current and upcoming events are listed in the form of event titles, and are presented in ascending order of event end dates. Upon clicking one of the event titles, the iser is led to a page which has the details of the event i.e. the title, the event start date, the event end date, and the event details.

In the Mess Menu module, the user can view the present day's breakfast, lunch, and dinner items for a particular mess.

In the Map module, the user can view a scrollable 2D map of NITK.

## Technical specifications
* Java 7 or above
* MySQL version 5.1 or above

## Screenshots

## Task list
- [x] Values loaded dynamically from MySQL database
- [x] User can view news, sorted by most recent
- [x] User can view current and upcoming events, and their details
- [x] User can view the menu for a particular mess for the current day
- [x] User can view 2D map of NITK

## Installation guide

#### Java
To check if Java is already installed on your system, execute the following command in the Terminal:
```
$ java -version
```

If Java is not present, execute the following command to install the default Java Runtime Environment (JRE), which will install the JRE from OpenJDK 11:
```
$ sudo apt install default-jre
```

#### MySQL
To install MySQL, follow all three steps given in [this](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-18-04) tutorial, and set `1234` as the `root` password when prompted for the same.

## Usage

#### 1. MySQL database creation

Issue the following commands in the MySQL Command Line Client for building the database used by the application:
```
CREATE DATABASE NITK_Virtual_Guide;
USE NITK_Virtual_Guide;

CREATE TABLE News
(
Title varchar(100),
Date date,
Content varchar(10000)
);

ADD PRIMARY KEY(Title, Date);

CREATE TABLE Events
(
Title varchar(100),
StartDate date,
EndDate date,
Content varchar(10000)
);

ADD PRIMARY KEY(Title, StartDate, EndDate);

CREATE TABLE Menu
(
Hostel varchar(100),
Day varchar(20),
Meal varchar(20),
Item varchar(100),
);
```

#### 2. Clean and build project

Click the `Run` tab, and click `Clean and Build Project`. Alternatively, press Shift+F11. This produces NITK_Virtual_Guide.jar, which is the executable file to be run. This file is present at NITK_Virtual_Guide/dist.

#### 3. Execute the application

To execute the application from within the IDE, click the `Run` tab, and click `Run File`. Alternatively, press Shift+F6.
To execute the application from outside the IDE, double-click NITK_Virtual_Guide.jar. If it doesn't run, right click it, go to Properties, and under the Permissions tab tick the 'Allow executing file as program' checkbox.

#### 5. Distribution

To distribute the application, create a zip file of the dist folder, and send it to the users of the application, along with the installation and usage instructions.
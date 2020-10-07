# Email_Notification
## Description
The project 'Email_Notification' is a Java application that accesses a MySQL database, where the user role `admin` is permitted to draft and send emails to the other users registered on the application.

To use the application, users are required to sign up by providing email ID, user ID, country, and password. These details are stored in a MySQL table called 'User'. The admin can send emails to the users by using the email IDs provided by the latter. The admin may enter a subject and a body for the email. The admin can send emails in the following two ways:
* Send emails to all users at once.
* Send emails to users belonging to one or more countries selected by the admin.

## Technical specifications
* Java 7 or above
* MySQL version 5.1 or above

## Screenshots

![Admin dashboard](Screenshots/5%20Admin%20Dashboard.png)  
<p align="center">Admin dashboard</p>

&nbsp;

![Email](Screenshots/6%20Email%20by%20Admin.png)  
<p align="center">Email sent by admin</p>

&nbsp;

![Database state](Screenshots/7%20MySQL%20Database%20State.png)  
<p align="center">Database state at the time of sending email</p>

&nbsp;

## Task list
- [x] Send emails to all registered users
- [x] Send emails to users of one or more selected countries
- [x] Provide subject and body to the email
- [x] User registration and authentication
- [x] Admin authentication

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

To check if the Java compiler is already installed on your system, execute the following command:
```
$ javac -version
```

If the Java compiler is not present, execute the following command to install the default Java Development Kit (JDK):
```
$ sudo apt install default-jdk
```

#### MySQL
To install MySQL, follow all three steps given in [this](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-18-04) tutorial, and set `1234` as the `root` password when prompted for the same.

#### NetBeans IDE 8.2
Install NetBeans IDE 8.2 from [here](https://netbeans.org/downloads/old/8.2/), by selecting the Java SE or Java EE bundle.

## Usage

#### 1. MySQL database creation

Issue the following commands in the MySQL Command Line Client for building the database used by the application:
```
CREATE DATABASE Email_Notification;
USE Email_Notification;

CREATE TABLE User
(
UserID varchar(100) PRIMARY KEY,
Email varchar(100) UNIQUE,
Password varchar(100),
Country varchar(100)
);

INSERT INTO User VALUES('admin', 'yourEmailID@gmail.com', 'admin', 'India');
```

In the very last command, enter your own email ID in the designated place.

#### 2. Edit source code to include email and password of the admin

Open the NetBeans IDE, click on File -> Open Project, and open the Java application. Once opened, in the Projects section, expand the 'Email_Notification' project node, expand the `Source Packages` subnode, expand the `<default package>` subnode, and double click `Email_Notification.java`. Click the `Source` tab. In the `sendEmailsButtonActionPerformed() function`, set the `adminEmail` and `password` variables as your own email and password.

#### 3. Clean and build project

Click the `Run` tab, and click `Clean and Build Project`. Alternatively, press Shift+F11. This produces Email_Notification.jar, which is the executable file to be run. This file is present at Email_Notification/dist.

#### 4. Execute the application

To execute the application from within the IDE, click the `Run` tab, and click `Run File`. Alternatively, press Shift+F6.
To execute the application from outside the IDE, double-click Email_Notification.jar. If it doesn't run, right click it, go to Properties, and under the Permissions tab tick the 'Allow executing file as program' checkbox.

#### 5. Distribution

To distribute the application, create a zip file of the dist folder, and send it to the users of the application, along with the installation and usage instructions.

# Email_Notification
The project 'Email_Notification' is a Java-MySQL application where the user role 'admin' is permitted to send emails to the other users registered on the application, based on the selection of filters.

Email_Notification.jar is the executable file to be run, which is present at Email_Notification/dist.

To run this file, first check if Java is installed on your system by issuing the following command in the Terminal:
```
java -version
```

If Java is not present, issue this command:
```
sudo apt install default-jre
```

This downloads the Java Runtime Environment. Now, in MySQL, issue the following commands:
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

Next, ensure that your MySQL 'Root' password is set to "1234".

Now, double-click Email_Notification.jar to run it. If it doesn't run, right click it, go to Properties, and under the Permissions tab tick the 'Allow executing file as program' checkbox.
# BlackEagle – Server-side and Client-side Parental Control Spyware
<img src="https://i.ibb.co/rwB4fLv/be-logo.png" width="400" hspace="10" vspace="10">

## About
BlackEagle is a parental control system that helps parents monitor their children's computers and reduce their exposure to content that is not appropriate for their age, while putting great emphasis on increased security and privacy of the information stored on our system.

The system consists of three parts:
* Remote server developed using Spring-Boot in conjunction with Apache-Tomcat server software.
* C / C ++ spyware that is responsible for collecting data from the monitored computer and keeping it on a remote server securely.
* A WEB interface developed using React-Native that allows remote access to data collected from a remote computer, in order to detect inappropriate content.

<img src="https://i.ibb.co/HPGZ7qt/block-diagram.png" width="500" hspace="10" vspace="10"><img src="https://i.ibb.co/Yt9ryKD/Client-server-architecture.jpg" width="400" hspace="10" vspace="10">


## Server (Spring-Boot + Apache-Tomcat)
The server side is developed in the Java language using Spring-Boot in combination with the Apache-Tomcat server software. The development is done with the support of many external libraries, which are imported through Maven technology.

As part of the development of the server, several entities were created that help to manage the database in the best possible way. The entities include: User, Data, Password, Event where User can be defined as Player, Admin and Device. For each entity and in particular for all types of Users in the system there is a service that contains the relevant functions for it.

The entities are saved in the PostgreSQL database using the CrudRepository interface that provides functions that themselves perform the desired queries on the database (saving, deleting, retrieving, etc.).

As part of the system's security process, there is a system for managing permissions according to user types (for each User type entity that has the ability to connect to the system, there are unique permissions for it).

The server is also responsible for sending updates to the personal email accounts of the system users.

## Spying Application
The spy software developed in C/C++ languages is responsible for collecting the data from the monitored computer and sending it to the remote server. In addition, the software is responsible for filtering and blocking inappropriate content and is able to perform the following actions:
* Capturing screenshots
* Keystroke logging
* Taking pictures through the mobile camera
* Audio recording
* Viewing the network traffic of the monitored computer
* Blocking inappropriate content
* Locating the location of the monitored computer
* Remote computer locking
* Sending CMD commands

The software connects to the remote server as a Device type user with reduced privileges, using login information that will be created by the parent when the Device is created in the database.

## User Interface (React-Native)
The user interface is developed using React-Native. The interface provides visual access to all the actions defined on the server within the permissions of the connected user (registration, logging in, creating devices, managing user settings, viewing collected data, and more).
The interface contains the following pages:
* Home page
* Login and Registration pages
* Forgot password pages
    * Enter your email
    * Enter a one-time password from the email
    * Creating a new password
* Main system page - presentation of the parent's children
* Select actions to perform page
* A certain action page
* Change and definition page of the child's settings
* Alerts page
* User account upgrade page
* Help page
* About page

## System Security
The existing protections in the system:
*#### Access to information ###


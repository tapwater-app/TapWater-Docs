- Jonathan: Other Nonfunctional Requirements, Other Requirements, Appendices
- Cody: System Features
- David: Overall Description
- Kon-Kon: Introduction, External Interface Requirements


# System Requirements Specification

## Introduction

### Purpose 

Identify the product whose software requirements are specified in this document, including the revision or release number. Describe the scope of the product that is covered by this SRS, particularly if this SRS describes only part of the system or a single subsystem.

### Document Conventions

Describe any standards or typographical conventions that were followed when writing this SRS, such as fonts or highlighting that have special significance. For example, state whether priorities  for higher-level requirements are assumed to be inherited by detailed requirements, or whether every requirement statement is to have its own priority.

### Intended Audience and Reading Suggestions

Describe the different types of reader that the document is intended for, such as developers, project managers, marketing staff, users, testers, and documentation writers. Describe what the rest of this SRS contains and how it is organized. Suggest a sequence for reading the document, beginning with the overview sections and proceeding through the sections that are most pertinent to each reader type.

### Product Scope

Provide a short description of the software being specified and its purpose, including relevant benefits, objectives, and goals. Relate the software to corporate goals or business strategies. If a separate vision and scope document is available, refer to it rather than duplicating its contents here.

### References

List any other documents or Web addresses to which this SRS refers. These may include user interface style guides, contracts, standards, system requirements specifications, use case documents, or a vision and scope document. Provide enough information so that the reader could access a copy of each reference, including title, author, version number, date, and source or location.

## Overall Description

### Product Perspective

  The TapWater development project works towards creating a new, self-contained software product, namely in the form of a joint-OS (Android and iOS) mobile app. Thus, the primary focus is development of these two co-existing applications. There will also exist a server-side component of development to facilitate synchronization across multiple platforms and devices. In this way, the project requires and will make use of server- and client-side technologies.

### Product Functions

  The following is a (non-exhaustive) list of core features, along with a brief description without diving into great detail of the technology supporting them. All features listed are categorized as “core” or “main” features, meaning they are either essential to the applications operation or promised functionality which created the demand for such a product.

#### Features:
  1. Unique User Registration and Setup
    - Encompasses a “first-time only” account setup to register the user as a unique Client.
    - Subsequent logins (including those on additional devices) require only a typical username/password submission.
    - Setup provides the User the opportunity to customize a few additional settings, including toggling notifications for the device (critical).
  2. Adding Drinks
    - From a simple menu, the User is able to add drinks from a list of pre-configured amounts (typical amounts, such as 4, 8, and 16fl oz.)
  3. Tracking Drinks
    - A simple view of “drink history” throughout the day, including the times they were logged into the application.
    - It is also possible to view previous days to compare progress.
  4. Drink Notifications
    - From a tracking algorithm, we can push notifications to the User’s device(s) to remind them to drink.

### User Classes and Characteristics

As a fairly simple, straight-forward application, the User Classes are somewhat trivial to lay out in detail. The TapWater application is intended to offer ease-of-use in an intuitive and unobtrusive interface. Part of this intention is fulfilled by refraining from adding “embellishment” features and menus that are rather unnecessary to fulfil the intended use. Moreover, as a cross-platform application, these interfaces should mirror each other as much as possible. For the purposes of User Classes, we will define the following:
  
__Simple User__ – A User who utilizes TapWater on only a singular device
__Complex User__ – A User who utilizes TapWater across multiple devices and, possibly, multiple platforms.

#### Simple User

##### Critical Functions:

- Log water intake
- Track progress towards daily goals

##### Requirements:
    
- Methods for logging water intake, including fixed and customized amounts
- Simplistic history-view of intake for each day
- A visible daily progress bar for added clarity
    
#### Complex User
  
##### Critical Functions:
    
- All functions identified in the first User Class
- Synchronization functions to update progress and drink-history on all client devices
 
##### Requirements:
    
- Synchronization method for pushing new data to server
- Synchronization method for pulling updated data from server

The TapWater development team recognizes that both User Classes are critical to the success of the project. Therefore, all identified requirements are classified as “critical”, in that they must function, and function reliably, to minimize frustration and promote user-base growth.

### Operating Environment

As the core functionality of the TapWater development project is focused within the mobile applications, the intended operating environments are the Android and iOS mobile operating systems. Due to the intentional simplicity of the interface and functionality, the system is highly unlikely to overload the hardware of any popular mobile device.
Server-side functionality will be implemented through Heroku, eliminating the need for development and maintenance of complex server technologies.

### Design and Implementation Constraints

From a design standpoint, it will be important to remember the functional limitations of mobile devices. By keeping the interface minimalistic, screen size and resolution are less of a concern. However, menu hierarchy will need to be carefully managed to avoid a frustrating user-experience in navigating the application. The action of “logging” a water intake should not be a hardware intensive action, either. The primary concern, then, lies with synchronization of data to the server, which can (potentially) be somewhat more processor-intensive as well as more overall complex.

### User Documentation

Again, we are at an advantage here due to the simplistic nature of the application’s function and design. Because we fully intend there to be very little learning curve to use this application (which is, for the most part, a critical requirement of all mobile apps) there is also little need for complex documentation. 
A very brief tutorial will be provided in the app-store descriptions to clarify any ambiguous features or menu options. An in-app help menu will also identify the function of all screen elements on each page.

### Assumptions and Dependencies

##### Hardware Dependencies
  
Again, all server functionality will be implemented through Heroku, reducing complexity of the implementation. However, this also increases external dependency for the project, because the application will only be able to sync when the server functions properly.
Client-side, the application will be dependent upon the mobile device's mobile/wifi antennas to accomplish synchronization tasks. The mobile applications will also be dependent on other integral technologies, such as the touch-screen hardware.

##### Software Dependencies
  
With the Android operating system evolving so rapidly over the past several years, we must be sure to develop only using functions available several iterations previous to the current OS version. Many mobile phone users do not update their devices in a timely manner.
With Android, we will also be implementing functions from the native Android push notification library.
With the iOS operating system, this is less of a problem, but we must still be sure to develop several versions back to support older devices which cannot update to the latest iOS platform.

## External Interface Requirements

### User Interfaces

Describe the logical characteristics of each interface between the software product and the users. This may include sample screen images, any GUI standards or product family style guides that are to be followed, screen layout constraints, standard buttons and functions (e.g., help) that will appear on every screen, keyboard shortcuts, error message display standards, and so on. Define the software components for which a user interface is needed. Details of the user interface design should be documented in a separate user interface specification.

### Hardware Interfaces

Describe the logical and physical characteristics of each interface between the software product and the hardware components of the system. This may include the supported device types, the nature of the data and control interactions between the software and the hardware, and communication protocols to be used.

### Software Interfaces

Describe the connections between this product and other specific software components (name and version), including databases, operating systems, tools, libraries, and integrated commercial components. Identify the data items or messages coming into the system and going out and describe the purpose of each. Describe the services needed and the nature of communications. Refer to documents that describe detailed application programming interface protocols. Identify data that will be shared across software components. If the data sharing mechanism must be implemented in a specific way (for example, use of a global data area in a multitasking operating system), specify this as an implementation constraint.

### Communications Interfaces

Describe the requirements associated with any communications functions required by this product, including e-mail, web browser, network server communications protocols, electronic forms, and so on. Define any pertinent message formatting. Identify any communication standards that will be used, such as FTP or HTTP. Specify any communication security or encryption issues, data transfer rates, and synchronization mechanisms.


## System Features

This template illustrates organizing the functional requirements for the product by system features, the major services provided by the product. You may prefer to organize this section by use case, mode of operation, user class, object class, functional hierarchy, or combinations of these, whatever makes the most logical sense for your product.

### Log Drinks

Users will record the drinks they consume throughout the day.

#### 4.1.1	Description and Priority

Users will record their consumption of water throughout the day manually by choosing from three different categories: a "drink", a "glass", or a "bottle". A drink constitutes 4 oz of water, a glass constitutes 
8 oz of water, and a bottle constitutes 16 oz of water. This features is critical to the overal usability of the system, so it is of high priority.

#### 4.1.2	Stimulus/Response Sequences

1. From the main screen, the three TapWater water consumption sizes are presented and selectable.
2. The user will select one of the option when they have drank a matching amount of water.
3. The total amount of water consumed in that day will increment on the screen
4. A new drink with be added to the device's database

#### 4.1.3	Functional Requirements

- REQ 1.1: The system should provide 3 different options for recording drinks.
- REQ 1.2: The system should create a drink object with an unique UUID for the created drink, the category of the drink selected, and the current date as the drink_date.
- REQ 1.3: The system should save the created drink into the device's database and be ready to accept another drink before the selection's button animation completes.

### View Drink History

Users will view the drinks they have recorded.

#### 4.2.1	Description and Priority

Users will have a list of all their previously recorded drinks. This list will contain the size of the drink logged as well as the time it was logged. This feature is a high priority.

#### 4.2.2	Stimulus/Response Sequences

1. The user will select an icon on the main screen which will lead them to their drink history.
2. Users will see a list of all the previous drinks they have recorded as well as information regarding the size of the drink and time it was recorded.

#### 4.2.3	Functional Requirements

- REQ 2.1: The system should provide a button which will open a screen to view the user's logged drinks.
- REQ 2.2: The system should list each drink the user has logged, with each entry displaying the category of the drink and the date the drink was logged.

### Schedule Drink Notifications

Users will be able to schedule the frequency in which they are reminded by the system to drink water.

#### 4.3.1	Description and Priority

The system will allow for both manual, unassisted drink entry as well as remind the users that it is time for them to consume another drink of a certain size in order to meet their self-defined goal. 
This goal is user defined and the user will specify how often (or how many times per 24 hour period) they would like to be reminded to drink. The priority of this feature is medium.

#### 4.3.2	Stimulus/Response Sequences

1. The user will tap a button to take them to a notification settings screen.
2. The user will enter a goal for the amount of water they wish to drink in a day.
3. The user will use a date picker to pick a start and end time to specify the period in which they would like to be reminded to drink.
4. The user will toggle notifications on/off.
5. The application will notify the user to drink an 8 ounce cup of water at even intervals throughout the day until they've met their goal.

#### 4.3.3	Functional Requirements

- REQ 3.1: The system should provide a "settings" icon which provides access to the notification scheduler.
- REQ 3.2: The notification scheduler should provide fields to edit the number of ounces the user wishes to drink daily, as well as how often the system will notify them.
- REQ 3.3: The system will push notifications to the user's device when the specified time periods are met including the number of remaining ounces to drink as calculated by the system.

### User Registration/Login/Log Out

Users will register a unique account using their user-defined username and password, and log in and out of this account as they wish.

#### 4.4.1	Description and Priority

Users will have a list of all their previously recorded drinks. This list will contain the size of the drink logged as well as the time it was logged. This feature is a medium priority.

#### 4.4.2	Stimulus/Response Sequences

##### Registration

1. From the main screen, the unathenticated user will tap a button to navigate to the user settings screen.
2. The user will enter a username, password, and password confirmation
3. If the password and the password confirmation match, the application will try to register the user with the rails server. If there is an error the registration form will reset and an error message will be displayed.
4. If the account creation is successful the server will send the device a device token which it will use to identify itself and the user in future requests.
5. The registered user will be logged in as the current user for the mobile application.

###### 4.4.3.1	Functional Requirements

- REQ 4.1: The system should provide a registration button if there is no user is logged in.
- REQ 4.2: The system provides fields for the user to enter a username, password, and confirm their password.
- REQ 4.3: The system will provide a submit button to create a user and log them in.

##### Log In

1. From the main screen, the unathenticated user will tap a button to navigate to the user settings screen.
2. The user will enter a username and password.
3. The application will send the username and password to the server.
4. If the authentication information is valid, the server will respond with a device token. Otherwise, it will respond with an error and the mobile application will reset the log in form and display an error message.
5. The device token will be saved to be used in future requests.
6. The registered user will be logged in as the current user for the mobile application.

###### 4.4.3.2	Functional Requirements

- REQ 4.4: The system should provide a log in button to authenticate a previously created user.
- REQ 4.5: The system should return a 300 code if the log in isn't valid, and return a device token if the log in is valid.

##### Log Out

1. From the main screen, the athenticated user will tap a button to navigate to the user settings screen.
2. The user will press a log out button and the device token will be deleted and the user will be logged out of the mobile application.

###### 4.4.3.3	Functional Requirements

- REQ 4.6: The system should provide a log out button if the user is already logged in.
- REQ 4.7: On press, the system should delete the saved device token.
- REQ 4.8: The system should redirect the user to the login screen.

### Synchronization

Users will sync their data with the system's server in order to be up-to-date between devices.

#### 4.5.1	Description and Priority

Users will be able to pull down on the history screen, which will synchronize their drink history with the history recorded for the user on the server. This feature is of low importance.

#### 4.5.2	Stimulus/Response Sequences

1. User will view their drink history.
2. User will pull down on the screen in order to trigger the synchronization feature.
3. The system will post the drinks in the history to the server, and the server will respond with the current history between devices for that user.

#### 4.5.3	Functional Requirements

- REQ 5.1: The system should provide the functionality to pull down on the screen from the drink history screen and trigger synchronization.
- REQ 5.2: The system should send a POST request to the server containing all the drinks in the device's local database and receive from the server a list of the current drinks between devices for the user.

## Other Nonfunctional Requirements

### Performance Requirements

Performance issues are not expected form TapWater.
Simplicity is a fundamental element of the design.

Performance will vary depending upon device and system version.

Changing between screens and processing button presses will be handled by the built in features of the SDK for the given mobile device and should perform at device expectations.

Sycnhronization time may vary depending on network connectivity.
The data exchanged should be optimized to assure the fastest synchronization possible.
A local cache of drinks will be kept by the system so that it does not have to load data from the server repeatedly.

### Safety Requirements

Use of the system should not present any harm to the user's device.

TapWater should not be used while operating a motor vehicle or any other kind of dangerous machinery.

Users should not use TapWater to consume more than a healthy amount of water.
What is considered a "healthy" amount of water varies from person to person. 
If a user is uncertain they should seek the advice of a doctor.

Users should not use TapWater if they have a condition in which water consumption may damage their health.

### Security Requirements

The drink data is not sensetive information.
It is still private user information and should be secured using standard database security protocols.

The system communicates usernames, passwords, and device information over the network.
This communication should be encrytpted with an HTTPS connection.
Additionally, the database should not store plain text user passwords.

Specify any requirements regarding security or privacy issues surrounding use of the product or protection of the data used or created by the product. Define any user identity authentication requirements. Refer to any external policies or regulations containing security issues that affect the product. Define any security or privacy certifications that must be satisfied.

### Software Quality Attributes

The user interfaces should be appealing to the eye.
The system should follow a consistent design style with a consistent color scheme.

The mobile applications should be available on their respective software marketplaces.
The iOS app should be available on the Apple App store.
The Android app should be available on the Google Play store.

The data synchronized to each of a user's devices should be consistent with the data on the other devices.

## Other Requirements

The database on the iOS and Android apps will be a SQLite databse.
The schema will look like the following:

#### Drinks

| Field Name | Description                                                           |
|------------|-----------------------------------------------------------------------|
| uuid       | A unique identifier for the drink.                                    |
| category   | The type of drink. Possible values are "drink", "glass", and "bottle" |
| drink_date | The date/time the drink was logged                                    |

The database on the Server will have the following schema:

#### Users

| Field Name      | Description                                        |
|-----------------|----------------------------------------------------|
| username        | The user's username                                |
| password_digest | The password hash and salt for the user's password |

#### Devices

| Field Name   | Description                                              |
|--------------|----------------------------------------------------------|
| device_token | The token this device will use to authenticate API calls |
| device_type  | The type and system version of the device                |
| user_id      | Foreign key for the user associated with the device      |

#### Drinks

| Field Name | Description                                                           |
|------------|-----------------------------------------------------------------------|
| uuid       | A unique identifier for the drink.                                    |
| category   | The type of drink. Possible values are "drink", "glass", and "bottle" |
| drink_date | The date/time the drink was logged                                    |
| user_id    | Foreign key for the user associated with the drink                    |

## Appendix A: Glossary

Define all the terms necessary to properly interpret the SRS, including acronyms and abbreviations. You may wish to build a separate glossary that spans multiple projects or the entire organization, and just include terms specific to a single project in each SRS.

## Appendix B: Analysis Models

Optionally, include any pertinent analysis models, such as data flow diagrams, class diagrams, state-transition diagrams, or entity-relationship diagrams.

## Appendix C: To Be Determined List

Collect a numbered list of the TBD (to be determined) references that remain in the SRS so they can be tracked to closure.
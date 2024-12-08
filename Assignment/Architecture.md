# System Context  Diagram Code

![System Context Diagram ](https://github.com/user-attachments/assets/0a83311c-0243-4c0e-92e1-ff3db25aad6e)


```plantuml
@startuml

' External Actors
actor "Rider (User)" as Rider
actor "Driver (User)" as Driver
actor "Admin" as Admin
actor "Payment Gateway" as PaymentGateway
actor "Map Service" as MapService
actor "Notification Service" as NotificationService
actor "Customer Support" as CustomerSupport

' System Boundary: InDrive Clone App
package "InDrive Clone App" {

    ' Subsystems
    rectangle "User Registration \nand Authentication" as Registration
    rectangle "Ride Booking \nand Management" as RideBooking
    rectangle "Driver Functionality" as DriverFunctionality
    rectangle "Payment Integration" as Payment
    rectangle "Ratings and Reviews" as Ratings
    rectangle "Admin Panel" as AdminPanel
    rectangle "Push Notifications" as PushNotifications
    rectangle "In-App Chat \nand Support" as ChatSupport
    rectangle "Real-Time Location Tracking" as Tracking
    rectangle "Customer Support" as Support
}

' Relationships between actors and system components
Rider --> Registration : Sign Up/Login
Rider --> RideBooking : Request Ride
Rider --> Payment : Process Payment
Rider --> Ratings : Rate Driver
Rider --> PushNotifications : Receive Notifications
Rider --> ChatSupport : In-App Chat with Driver

Driver --> Registration : Register/Login
Driver --> RideBooking : Accept Ride Request
Driver --> DriverFunctionality : Manage Availability
Driver --> Payment : Receive Payment
Driver --> Ratings : Rate Rider
Driver --> PushNotifications : Receive Ride Notifications
Driver --> ChatSupport : In-App Chat with Rider

Admin --> AdminPanel : Manage Users/Drivers/Rides
Admin --> RideBooking : Monitor Rides
Admin --> Payment : Monitor Payments
Admin --> PushNotifications : Send Notifications
Admin --> Ratings : Manage Reviews

' External Interactions
Payment --> PaymentGateway : Process Payment Transactions
Tracking --> MapService : Use Maps for Navigation
PushNotifications --> NotificationService : Send Notifications
Support --> CustomerSupport : Handle User Issues

@enduml
```

# Container Diagram

![image](https://github.com/user-attachments/assets/afc0a960-1dd0-47db-8530-f12d08b7ada4)

Here’s the **PlantUML code** for a container diagram considering **Admin**, **Driver**, and **Rider** roles, emphasizing their interactions with the system.  

```plantuml
@startuml
!define RECTANGLE rectangle
!define BOLD **<color:Black>**

title Container Diagram - InDrive Clone (Admin, Driver, Rider)

skinparam backgroundColor #FFFFFF

' User-facing applications
RECTANGLE "Admin Web Panel" as adminPanel <<Web Application>> #lightblue
RECTANGLE "Driver Mobile App" as driverApp <<Mobile Application>> #lightblue
RECTANGLE "Rider Mobile App" as riderApp <<Mobile Application>> #lightblue

' API Gateway
RECTANGLE "API Gateway" as apiGateway <<API Gateway>> #lightblue

' Backend microservices
RECTANGLE "Ride Service" as rideService <<Microservice>> #lightgreen
RECTANGLE "User Service" as userService <<Microservice>> #lightgreen
RECTANGLE "Payment Service" as paymentService <<Microservice>> #lightgreen
RECTANGLE "Notification Service" as notificationService <<Microservice>> #lightgreen
RECTANGLE "Admin Management Service" as adminService <<Microservice>> #lightgreen

' Databases
RECTANGLE "Ride Database" as rideDB <<Database>> #lightyellow
RECTANGLE "User Database" as userDB <<Database>> #lightyellow
RECTANGLE "Payment Database" as paymentDB <<Database>> #lightyellow

' External Systems
RECTANGLE "Payment Gateway" as paymentGateway <<External System>> #orange
RECTANGLE "SMS Provider" as smsProvider <<External System>> #orange
RECTANGLE "Email Provider" as emailProvider <<External System>> #orange
RECTANGLE "Maps Service" as mapsService <<External System>> #orange

' Relationships for Admin
adminPanel --> apiGateway : Admin Actions
apiGateway --> adminService : Manage Data/Reports
adminService --> rideDB : View/Edit Ride Records
adminService --> userDB : Manage Users

' Relationships for Rider
riderApp --> apiGateway : REST API Calls
apiGateway --> userService : Manage Rider Profile
apiGateway --> rideService : Request Ride
rideService --> rideDB : Ride Records
rideService --> mapsService : Fetch Routes
apiGateway --> paymentService : Handle Rider Payments
paymentService --> paymentDB : Read/Write
paymentService --> paymentGateway : Process Payments

' Relationships for Driver
driverApp --> apiGateway : REST API Calls
apiGateway --> userService : Manage Driver Profile
apiGateway --> rideService : Driver Matches/Updates
rideService --> rideDB : Ride Records
rideService --> mapsService : Fetch Routes

' Notifications
notificationService --> smsProvider : Send SMS
notificationService --> emailProvider : Send Emails
notificationService --> riderApp : Push Notifications
notificationService --> driverApp : Push Notifications

@enduml
```
Here are separate **PlantUML container diagrams** for **Driver**, **Rider**, and **Admin** workflows. Each role has its dedicated architecture, focusing on their specific interactions.  

---

### **Driver Workflow Diagram**
![image](https://github.com/user-attachments/assets/cf4b8bf9-9183-475a-a4fd-f38920db44ef)

```plantuml
@startuml
!define RECTANGLE rectangle
!define BOLD **<color:Black>**

title Container Diagram - Driver Workflow

skinparam backgroundColor #FFFFFF

' Applications
RECTANGLE "Driver Mobile App" as driverApp <<Mobile Application>> #lightblue

' API Gateway
RECTANGLE "API Gateway" as apiGateway <<API Gateway>> #lightblue

' Backend microservices
RECTANGLE "Ride Service" as rideService <<Microservice>> #lightgreen
RECTANGLE "User Service" as userService <<Microservice>> #lightgreen
RECTANGLE "Notification Service" as notificationService <<Microservice>> #lightgreen

' Databases
RECTANGLE "Ride Database" as rideDB <<Database>> #lightyellow
RECTANGLE "User Database" as userDB <<Database>> #lightyellow

' External Systems
RECTANGLE "Maps Service" as mapsService <<External System>> #orange
RECTANGLE "SMS Provider" as smsProvider <<External System>> #orange

' Relationships
driverApp --> apiGateway : REST API Calls
apiGateway --> userService : Manage Driver Profile
apiGateway --> rideService : Update Ride Status/Accept Rides
rideService --> rideDB : Ride Records
rideService --> mapsService : Fetch Routes
notificationService --> smsProvider : Send Notifications
notificationService --> driverApp : Push Notifications

@enduml
```

---

### **Rider Workflow Diagram**
![image](https://github.com/user-attachments/assets/2b67c735-a779-451b-8536-cfcb97228879)

```plantuml
@startuml
!define RECTANGLE rectangle
!define BOLD **<color:Black>**

title Container Diagram - Rider Workflow

skinparam backgroundColor #FFFFFF

' Applications
RECTANGLE "Rider Mobile App" as riderApp <<Mobile Application>> #lightblue

' API Gateway
RECTANGLE "API Gateway" as apiGateway <<API Gateway>> #lightblue

' Backend microservices
RECTANGLE "Ride Service" as rideService <<Microservice>> #lightgreen
RECTANGLE "User Service" as userService <<Microservice>> #lightgreen
RECTANGLE "Payment Service" as paymentService <<Microservice>> #lightgreen
RECTANGLE "Notification Service" as notificationService <<Microservice>> #lightgreen

' Databases
RECTANGLE "Ride Database" as rideDB <<Database>> #lightyellow
RECTANGLE "User Database" as userDB <<Database>> #lightyellow
RECTANGLE "Payment Database" as paymentDB <<Database>> #lightyellow

' External Systems
RECTANGLE "Maps Service" as mapsService <<External System>> #orange
RECTANGLE "Payment Gateway" as paymentGateway <<External System>> #orange
RECTANGLE "SMS Provider" as smsProvider <<External System>> #orange

' Relationships
riderApp --> apiGateway : REST API Calls
apiGateway --> userService : Manage Rider Profile
apiGateway --> rideService : Request Rides
rideService --> rideDB : Ride Records
rideService --> mapsService : Fetch Routes
apiGateway --> paymentService : Handle Rider Payments
paymentService --> paymentDB : Payment Records
paymentService --> paymentGateway : Process Transactions
notificationService --> smsProvider : Send Notifications
notificationService --> riderApp : Push Notifications

@enduml
```

---

### **Admin Workflow Diagram**
![image](https://github.com/user-attachments/assets/32dc05d9-2997-4db6-ba7e-1dae1aeeb876)

```plantuml
@startuml
!define RECTANGLE rectangle
!define BOLD **<color:Black>**

title Container Diagram - Admin Workflow

skinparam backgroundColor #FFFFFF

' Applications
RECTANGLE "Admin Web Panel" as adminPanel <<Web Application>> #lightblue

' API Gateway
RECTANGLE "API Gateway" as apiGateway <<API Gateway>> #lightblue

' Backend microservices
RECTANGLE "Admin Management Service" as adminService <<Microservice>> #lightgreen
RECTANGLE "Ride Service" as rideService <<Microservice>> #lightgreen
RECTANGLE "User Service" as userService <<Microservice>> #lightgreen

' Databases
RECTANGLE "Ride Database" as rideDB <<Database>> #lightyellow
RECTANGLE "User Database" as userDB <<Database>> #lightyellow

' Relationships
adminPanel --> apiGateway : Manage Data/Reports
apiGateway --> adminService : Admin Operations
adminService --> rideService : Fetch/Edit Ride Records
adminService --> rideDB : Direct Ride Data Queries
adminService --> userService : Manage User Profiles
adminService --> userDB : Direct User Data Queries

@enduml
```
---
# Component Diagram
![image](https://github.com/user-attachments/assets/cb28493e-36ba-44c7-847e-389394a85585)

Here is the **PlantUML code** for a **combined component diagram** that includes **Admin**, **Rider**, and **Driver** components.

```plantuml
@startuml
title Combined Component Diagram - Admin, Rider, Driver

' External Actors
actor "Rider (User)" as Rider
actor "Driver (User)" as Driver
actor "Admin" as Admin
actor "Payment Gateway" as PaymentGateway
actor "Map Service" as MapService
actor "Notification Service" as NotificationService
actor "Customer Support" as CustomerSupport

' System Boundary: InDrive Clone App
package "InDrive Clone App" {

    ' Rider Components
    component "User Registration \nand Authentication" as Registration
    component "Ride Booking \nand Management" as RideBooking
    component "Payment Processing" as RiderPayment
    component "Driver Rating \nand Review" as RiderRatings
    component "Push Notifications" as RiderNotifications
    component "In-App Chat \nand Support" as RiderChatSupport
    component "Real-Time Location Tracking" as RiderTracking

    ' Driver Components
    component "Driver Registration \nand Authentication" as DriverRegistration
    component "Driver Profile Management" as DriverProfile
    component "Ride Acceptance \nand Management" as RideManagement
    component "Driver Payment Processing" as DriverPayment
    component "Driver Ratings \nand Feedback" as DriverRatings
    component "Driver Notifications" as DriverNotifications
    component "Driver Real-Time \nLocation Tracking" as DriverTracking
    component "Driver In-App Chat \nand Support" as DriverChatSupport

    ' Admin Components
    component "Admin Dashboard" as AdminDashboard
    component "User Management" as UserManagement
    component "Driver Management" as DriverManagement
    component "Ride Monitoring" as RideMonitoring
    component "Payment Management" as PaymentManagement
    component "Reports and Analytics" as ReportsAnalytics
    component "Notification Management" as NotificationManagement
}

' Relationships for Rider
Rider --> Registration : Sign Up/Login
Rider --> RideBooking : Request Ride
Rider --> RiderPayment : Process Payment
Rider --> RiderRatings : Rate Driver
Rider --> RiderNotifications : Receive Notifications
Rider --> RiderChatSupport : Chat with Driver
Rider --> RiderTracking : Track Driver Location

' Relationships for Driver
Driver --> DriverRegistration : Sign Up/Login
Driver --> DriverProfile : Manage Profile
Driver --> RideManagement : Accept/Decline Rides
Driver --> DriverPayment : Track Earnings/Receive Payment
Driver --> DriverRatings : Rate Rider
Driver --> DriverNotifications : Receive Notifications
Driver --> DriverTracking : Share Location
Driver --> DriverChatSupport : Chat with Rider

' Relationships for Admin
Admin --> AdminDashboard : Access Dashboard
Admin --> UserManagement : Manage Users
Admin --> DriverManagement : Manage Drivers
Admin --> RideMonitoring : Monitor Rides
Admin --> PaymentManagement : Monitor Payments
Admin --> ReportsAnalytics : Generate Reports
Admin --> NotificationManagement : Manage Notifications

' External Interactions
RiderTracking --> MapService : Access Maps for Navigation
DriverTracking --> MapService : Access Maps for Navigation
RiderPayment --> PaymentGateway : Process Rider Payments
DriverPayment --> PaymentGateway : Process Driver Payments
RiderNotifications --> NotificationService : Push Notifications
DriverNotifications --> NotificationService : Push Notifications
RiderChatSupport --> CustomerSupport : Escalate Issues
DriverChatSupport --> CustomerSupport : Escalate Issues

@enduml
```


---
Below are the **PlantUML** codes for the diagrams related to the **InDrive Clone System**, focusing on the **Driver**, **Rider**, and **Admin**.

---

### **1. Driver Component Diagram**
![image](https://github.com/user-attachments/assets/d678da3c-69de-497c-aa9d-602aa459dbde)

```plantuml
@startuml
' External Actors
actor "Driver (User)" as Driver
actor "Map Service" as MapService
actor "Notification Service" as NotificationService
actor "Payment Gateway" as PaymentGateway
actor "Rider (User)" as Rider
actor "Customer Support" as CustomerSupport

' System Boundary: InDrive Clone App
package "InDrive Clone App" {

    ' Subsystems specifically related to Driver
    rectangle "Driver Registration \nand Authentication" as DriverRegistration
    rectangle "Driver Profile Management" as DriverProfile
    rectangle "Ride Acceptance \nand Management" as RideManagement
    rectangle "Payment Processing" as DriverPayment
    rectangle "Driver Ratings \nand Feedback" as DriverRatings
    rectangle "Real-Time Location Tracking" as DriverTracking
    rectangle "Driver Notifications" as DriverNotifications
    rectangle "In-App Chat \nand Support" as DriverChatSupport
}

' Relationships between Driver and system components
Driver --> DriverRegistration : Register/Login
Driver --> DriverProfile : Manage Profile
Driver --> RideManagement : Accept/Decline Ride Requests
Driver --> DriverPayment : Track Earnings/Receive Payment
Driver --> DriverRatings : Rate Rider
Driver --> DriverNotifications : Receive Ride Notifications
Driver --> DriverChatSupport : Chat with Rider/Customer Support
Driver --> DriverTracking : Real-Time Location Sharing

' External Interactions
DriverTracking --> MapService : Access Navigation Maps
DriverPayment --> PaymentGateway : Process Driver Payments
DriverNotifications --> NotificationService : Send Notifications to Driver
DriverChatSupport --> CustomerSupport : Escalate Issues with Support
@enduml
```

---

### **2. Rider Component Diagram**
![image](https://github.com/user-attachments/assets/98b627f0-5a6f-4c8e-b597-2c80bab41f3f)

```plantuml
@startuml

' External Actors
actor "Rider (User)" as Rider
actor "Driver (User)" as Driver
actor "Admin" as Admin
actor "Payment Gateway" as PaymentGateway
actor "Map Service" as MapService
actor "Notification Service" as NotificationService
actor "Customer Support" as CustomerSupport

' System Boundary: InDrive Clone App
package "InDrive Clone App" {

    ' Subsystems
    rectangle "User Registration \nand Authentication" as Registration
    rectangle "Ride Booking \nand Management" as RideBooking
    rectangle "Payment Processing" as Payment
    rectangle "Driver Rating \nand Review" as Ratings
    rectangle "Push Notifications" as PushNotifications
    rectangle "In-App Chat \nand Support" as ChatSupport
    rectangle "Real-Time Location Tracking" as Tracking
    rectangle "Customer Support" as Support
}

' Relationships between actors and system components
Rider --> Registration : Sign Up/Login
Rider --> RideBooking : Request Ride
Rider --> Payment : Process Payment
Rider --> Ratings : Rate Driver
Rider --> PushNotifications : Receive Notifications
Rider --> ChatSupport : In-App Chat with Driver

Driver --> Registration : Register/Login
Driver --> RideBooking : Accept Ride Request
Driver --> Payment : Receive Payment
Driver --> Ratings : Rate Rider
Driver --> PushNotifications : Receive Ride Notifications
Driver --> ChatSupport : In-App Chat with Rider

Admin --> RideBooking : Monitor Rides
Admin --> Payment : Monitor Payments
Admin --> Ratings : Manage Reviews

' External Interactions
Payment --> PaymentGateway : Process Payment Transactions
Tracking --> MapService : Use Maps for Navigation
PushNotifications --> NotificationService : Send Notifications
Support --> CustomerSupport : Handle User Issues

@enduml
```

---

### **3. Admin Component Diagram**
![image](https://github.com/user-attachments/assets/3529e829-5c4a-45d9-987b-e9284a3edcab)

```plantuml
@startuml

' Define the system components for the Admin Panel
package "Admin Panel" {
    component "Dashboard" as Dashboard
    component "User Management" as UserManagement
    component "Driver Management" as DriverManagement
    component "Ride Monitoring" as RideMonitoring
    component "Payment Management" as PaymentManagement
    component "Reports and Analytics" as ReportsAnalytics
    component "Notification Management" as NotificationManagement
}

' External services used by the Admin Panel
database "User Database" as UserDB
database "Driver Database" as DriverDB
database "Ride Database" as RideDB
database "Payment Database" as PaymentDB
component "Notification Service" as NotificationService
component "Payment Gateway" as PaymentGateway

' Relationships between Admin Panel components
Dashboard --> UserManagement : Access User Data
Dashboard --> DriverManagement : Manage Drivers
Dashboard --> RideMonitoring : Monitor Active Rides
Dashboard --> PaymentManagement : View Payment Info
Dashboard --> ReportsAnalytics : Generate Reports
Dashboard --> NotificationManagement : Send Notifications

' Internal component interactions
UserManagement --> UserDB : Read/Write User Data
DriverManagement --> DriverDB : Read/Write Driver Data
RideMonitoring --> RideDB : Access Ride Data
PaymentManagement --> PaymentDB : Access Payment Data
ReportsAnalytics --> UserDB : Generate User Reports
ReportsAnalytics --> DriverDB : Generate Driver Reports
ReportsAnalytics --> RideDB : Generate Ride Reports
ReportsAnalytics --> PaymentDB : Generate Payment Reports

' External interactions
PaymentManagement --> PaymentGateway : Process Payment Refunds
NotificationManagement --> NotificationService : Send Notifications to Users

@enduml
```

---

# Deployment Diagram
![image](https://github.com/user-attachments/assets/8301b46d-7f67-4292-a9af-1e7b943fd704)


```plantuml
@startuml
title Deployment Diagram - InDrive Clone System

node "Rider's Mobile Device" {
    [Rider Mobile App] <<Mobile App>>
}

node "Driver's Mobile Device" {
    [Driver Mobile App] <<Mobile App>>
}

node "Admin's PC" {
    [Admin Web Dashboard] <<Web App>>
}

node "Web Server" {
    [Ride Management Service] <<Microservice>>
    [Payment Service] <<Microservice>>
    [User Management Service] <<Microservice>>
    [Real-Time Tracking Service] <<Microservice>>
}

node "Database Server" {
    database "User Database" as UserDB
    database "Ride Database" as RideDB
    database "Payment Database" as PaymentDB
}

cloud "Third-Party Services" {
    [Payment Gateway] <<External Service>>
    [Map/GPS Service] <<External Service>>
}

' Connections
[Rider Mobile App] --> [Ride Management Service] : "Request rides"
[Rider Mobile App] --> [Payment Service] : "Process payment"
[Rider Mobile App] --> [Real-Time Tracking Service] : "Track driver"
[Rider Mobile App] --> [User Management Service] : "Manage profile"

[Driver Mobile App] --> [Ride Management Service] : "Accept/Decline ride"
[Driver Mobile App] --> [Real-Time Tracking Service] : "Navigate to rider"
[Driver Mobile App] --> [User Management Service] : "Manage profile"
[Driver Mobile App] --> [Payment Service] : "View earnings"

[Admin Web Dashboard] --> [Ride Management Service] : "Monitor rides"
[Admin Web Dashboard] --> [User Management Service] : "Manage users"
[Admin Web Dashboard] --> [Payment Service] : "Monitor payments"

[Ride Management Service] --> UserDB : "Read/Write user and ride data"
[Payment Service] --> PaymentDB : "Read/Write payment data"
[User Management Service] --> UserDB : "Manage user profiles"
[Real-Time Tracking Service] --> RideDB : "Read/Write location data"

[Payment Service] --> [Payment Gateway] : "Process payment"
[Real-Time Tracking Service] --> [Map/GPS Service] : "Access map and GPS data"

@enduml
```







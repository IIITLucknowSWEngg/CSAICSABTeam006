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
## Driver
## Rider
![comtainet Diagram](https://github.com/user-attachments/assets/ea20c4a7-aa56-469c-98b6-50573e66390b)


```plantuml
@startuml
!define RECTANGLE rectangle
!define BOLD **<color:Black>**

title Container Diagram - InDrive Clone

' Add primary containers
' User section
RECTANGLE "Mobile App" as mobileApp <<Mobile Application>> #lightblue
RECTANGLE "Web App" as webApp <<Web Application>> #lightblue
RECTANGLE "User API Gateway" as userGateway <<API Gateway>> #lightblue

' Backend services
RECTANGLE "Ride Service" as rideService <<Microservice>> #lightgreen
RECTANGLE "User Service" as userService <<Microservice>> #lightgreen
RECTANGLE "Payment Service" as paymentService <<Microservice>> #lightgreen
RECTANGLE "Notification Service" as notificationService <<Microservice>> #lightgreen

' Database containers
RECTANGLE "Ride Database" as rideDB <<Database>> #lightyellow
RECTANGLE "User Database" as userDB <<Database>> #lightyellow
RECTANGLE "Payment Database" as paymentDB <<Database>> #lightyellow

' External systems
RECTANGLE "External Payment System" as paymentSystem <<External System>> #pink
RECTANGLE "Third-Party Map API" as mapAPI <<External System>> #pink
RECTANGLE "Push Notification Service" as pushNotification <<External System>> #pink

' Relationships between containers
mobileApp --> userGateway : "API Calls"
webApp --> userGateway : "API Calls"
userGateway --> rideService : "Manage Rides"
userGateway --> userService : "Manage User Data"
userGateway --> paymentService : "Process Payments"
userGateway --> notificationService : "Send Notifications"

rideService --> rideDB : "Read/Write Data"
userService --> userDB : "Read/Write Data"
paymentService --> paymentDB : "Read/Write Data"

paymentService --> paymentSystem : "Process Payments"
rideService --> mapAPI : "Fetch Routes"
notificationService --> pushNotification : "Send Push Notifications"

@enduml
```

## Admin

# Component Diagram
## Driver
![Component Driver Diagram](https://github.com/user-attachments/assets/86f479eb-194e-45d3-8e5b-4459e0c95da4)

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

## Rider
![Component  Rider Diagram]![Screenshot 2024-12-01 001704 1](https://github.com/user-attachments/assets/a66de12a-40f1-4510-8316-2c110947e90c)



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


## Admin

![Admin](https://github.com/user-attachments/assets/d77cee63-02b5-4840-b837-d8c5035c85f3)


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

# Deployment Diagram Code

![Deployment Diagram](https://github.com/user-attachments/assets/88d20dd1-52e8-4425-912f-a0f0c984c436)


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

### Software Requirements Specification (SRS) Document ###

---

## 1. Introduction

### 1.1 Purpose  
This Software Requirements Specification (SRS) document outlines the requirements for an InDrive competitor application. It serves as a comprehensive reference for developers, testers, and stakeholders throughout the development lifecycle, covering functional, non-functional, and interface requirements.

### 1.2 Scope  
The InDrive competitor application is a ride-hailing platform that enables users to negotiate ride fares with drivers. It provides functionalities for booking rides, tracking trips, and ensuring secure and reliable payment processing. The application also integrates features such as user feedback and route optimization. This document details all aspects of the application, including design constraints, external interfaces, and system features.

### 1.3 Definitions, Acronyms, and Abbreviations  
- **SRS**: Software Requirements Specification  
- **NFR**: Non-Functional Requirement  
- **UI**: User Interface  
- **API**: Application Programming Interface  
- **OTP**: One-Time Password  
- **ETA**: Estimated Time of Arrival

### 1.4 References  
- IEEE Std 830-1998, IEEE Recommended Practice for Software Requirements Specifications  
- SWEBOK v3.0, Software Engineering Body of Knowledge  
- User Requirements Document  

### 1.5 Overview  
This document is structured into sections detailing the system's overview, functional and non-functional requirements, use case diagrams, and additional considerations relevant to building the InDrive competitor application.

---

## 2. Overall Description

### 2.1 Product Perspective  
The application is designed for Android and iOS platforms, integrating real-time GPS tracking, payment gateways, and driver-rider communication. Its modular architecture ensures scalability and flexibility for expanding features.

### 2.2 Product Functions  
- User registration and authentication.  
- Fare negotiation between riders and drivers.  
- Real-time ride tracking and ETA updates.  
- Trip history and payment management.  
- Driver rating and feedback system.  

### 2.3 User Classes and Characteristics  
- **Riders**: Individuals using the app to book rides.  
- **Drivers**: Professionals offering ride services.  
- **Admins**: Manage operations, ensuring app functionality and resolving issues.

### 2.4 Operating Environment  
The app will function on Android and iOS devices, with backend services hosted on cloud infrastructure. It requires internet connectivity and access to device GPS functionality.

### 2.5 Design and Implementation Constraints  
- Must comply with transport and data privacy regulations.  
- Performance constrained by mobile device capabilities and network availability.  
- Dependency on third-party mapping and payment APIs.  

### 2.6 Assumptions and Dependencies  
- Users have smartphones with GPS and stable internet connections.  
- Reliable integration with mapping services for accurate navigation and ETA.  
- Drivers comply with local transportation regulations.  

---

## 3. System Features

### 3.1 Ride Booking  
**Description:** Riders can book rides and negotiate fares with drivers.  
**Functional Requirements:**  
- The system shall allow riders to enter pickup and drop-off locations.  
- The system shall enable fare negotiation before confirming the ride.  
- The system shall provide real-time updates on ride status and ETA.

---

## 4. Use Case Diagrams  

### 4.1 Overview  
A use case diagram visually represents the interactions between actors and the system, focusing on their goals and the system's responses.  

### Actors  
- **Rider**: Books rides, negotiates fares, and tracks trips.  
- **Driver**: Accepts rides and navigates to destinations.  
- **Admin**: Manages users, trips, and resolves issues.
  

---

### Ideal Path: Good Use Case  
**Use Case Name**: **Rider Books a Ride**  
**Goal**: Rider successfully books and completes a ride.  
1. Rider opens the app and logs in.  
2. Enters pickup and drop-off locations.  
3. Negotiates fare with the driver.  
4. Confirms the ride.  
5. Tracks the ride in real-time.  
6. Completes the ride and provides feedback.
   
![image](https://github.com/user-attachments/assets/5c5eaa97-0551-43d4-bafb-a70d7618fc36)

---

### Error Path: Error Use Case  
**Use Case Name**: **Driver Cancels Ride**  
**Goal**: Rider must rebook due to driver cancellation.  
1. Driver accepts the ride request.  
2. Driver cancels the ride before arrival.  
3. The system notifies the rider and suggests alternative drivers.  
4. Rider books another ride.
![error case1](https://github.com/user-attachments/assets/290c66ca-f386-483e-92cd-9b7e0a4b6051)

---

### Abuse Path: Abuse Use Case  
**Use Case Name**: **Fake Ride Request**  
**Goal**: Prevent misuse of the platform by fake riders.  
1. A fake rider places a booking without intent to ride.  
2. The system detects repeated cancellations from the same account.  
3. Flags the account for admin review.  
4. Suspends the account after verification of abuse.  
![abuse case2](https://github.com/user-attachments/assets/f68ce8ee-fdb2-461b-bc1c-a2f962251c09)

---

## 5. Non-Functional Requirements  

### 5.1 Performance Requirements  
- The system shall process ride requests within 3 seconds.  
- Location updates shall refresh every 2 seconds during a trip.

### 5.2 Security Requirements  
- Data encryption at rest and in transit.  
- OTP for ride confirmation and account verification.  
- Regular audits for system vulnerabilities.  

### 5.3 Scalability  
- The system shall handle up to 100,000 concurrent users.  

---

## 6. Other Requirements  

- **Localization**: Support for multiple languages and currencies.  
- **Accessibility**: Compliance with WCAG 2.1 guidelines.  

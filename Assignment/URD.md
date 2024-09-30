# InDrive Clone - User Requirements Documentation (URD)

## 1. Introduction

This document outlines the user requirements for the development of an InDrive clone, a ride-hailing mobile application. The system allows users to request rides and drivers to offer their services in a location-based setting. Unlike traditional ride-hailing services, this app will allow passengers and drivers to negotiate fare prices.

### 1.1 Purpose

The purpose of this document is to provide a detailed description of the requirements of the ride-hailing application. This includes the app’s core functionalities, target audience, user interactions, and system constraints.

### 1.2 Scope

This document defines the functional and non-functional requirements for the InDrive clone. It is intended for developers, testers, and project stakeholders to ensure the system meets user expectations.

---

## 2. User Requirements

### 2.1 Target Users
- **Passengers**: Individuals who need to book rides.
- **Drivers**: Individuals offering ride services.
- **Admin/Support Staff**: For managing user issues, payments, and disputes.

---

## 3. Functional Requirements

### 3.1 Passenger Features

1. **User Registration & Login**
   - Allow passengers to register using email, phone number, or social media.
   - Login options include email/password, social media, or OTP-based login.

2. **Ride Booking**
   - Passengers can enter a destination and pick-up point.
   - Option to see available drivers nearby.
   - Ability to request a ride with a preferred fare or negotiate fare.

3. **Fare Negotiation**
   - Passengers can offer a suggested fare and negotiate with drivers.

4. **Ride Tracking**
   - Real-time tracking of drivers on a map using GPS.
   - Notification for when the driver arrives.

5. **Payment Options**
   - Multiple payment methods including cash, credit card, mobile wallets, or UPI.
   - Secure transactions with fare breakdown and invoice generation.

6. **Ride Rating and Feedback**
   - Ability to rate drivers and provide feedback after the trip.

7. **Ride History**
   - View past rides and payments.
   - Option to reorder the same ride from history.

### 3.2 Driver Features

1. **Driver Registration & Login**
   - Drivers can register using email or phone number.
   - Submit vehicle details and upload required documents.

2. **Ride Requests**
   - Drivers receive notifications about nearby ride requests.
   - Option to accept or negotiate the fare with the passenger.

3. **Ride Management**
   - Navigate to the passenger's pick-up location.
   - Complete the ride and update status.

4. **Earnings Tracking**
   - Track earnings on a daily, weekly, and monthly basis.
   - View payment history and commission deductions.

5. **Availability Status**
   - Toggle between online and offline mode.
   - Option to accept scheduled rides.

### 3.3 Admin/Support Features

1. **User Management**
   - Ability to manage both drivers and passengers.
   - Option to suspend or ban users in case of disputes.

2. **Ride and Payment Monitoring**
   - Track ongoing and completed rides.
   - Handle payment disputes and refund requests.

3. **Reports and Analytics**
   - Generate reports on system usage, payment transactions, and user activity.

---

## 4. Non-Functional Requirements

### 4.1 Performance
- The app must be responsive and provide results within 3 seconds for most user interactions.
- Must handle up to 100,000 simultaneous users across all regions.

### 4.2 Scalability
- The system should be scalable to support an increasing number of drivers and passengers as the app grows.

### 4.3 Security
- All transactions must be encrypted.
- User information should be securely stored and protected from unauthorized access.
- Implement two-factor authentication for critical operations like payments.

### 4.4 Usability
- The user interface should be intuitive and easy to navigate.
- Offer language options for users in different regions.

### 4.5 Availability
- The system must have 99.9% uptime to ensure reliable ride bookings and payments.

---

## 5. System Requirements

### 5.1 Hardware Requirements
- GPS and internet connectivity for both passengers and drivers.
- Smartphones with Android (version 8.0 and above) and iOS (version 11 and above).

### 5.2 Software Requirements
- Backend system: Node.js, Python, or Java.
- Database: MySQL, PostgreSQL, or MongoDB.
- Mobile Platforms: Android Studio, Swift.

---

## 6. User Interfaces

1. **Passenger App Interface**
   - Home screen with location input and ride request button.
   - Map view showing available drivers.
   - Fare negotiation screen.

2. **Driver App Interface**
   - Notifications for new ride requests.
   - Map with navigation to pick-up points.
   - Ride completion screen with earnings summary.

3. **Admin Panel**
   - Dashboard to monitor users, rides, and payments.

---

## 7. Constraints and Assumptions

- The app assumes users will have access to GPS-enabled smartphones.
- Availability of payment gateways to support online transactions.
- The system assumes good internet connectivity for tracking and real-time notifications.

---

## 8. Glossary

- **Passenger**: A user requesting rides.
- **Driver**: A user providing ride services.
- **Fare Negotiation**: The process by which passengers and drivers agree on a price.


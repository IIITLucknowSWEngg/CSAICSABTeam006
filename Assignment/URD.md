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

## 8 Continuous Integration (CI) and Continuous Deployment (CD)

To ensure efficient and high-quality development and deployment of the InDrive clone application, a CI/CD pipeline will be implemented. This section outlines the CI/CD requirements.

---

### 8.1 Continuous Integration (CI)

CI focuses on automating code integration, testing, and validation. Key CI requirements include:

1. *Version Control Integration*
   - Use a Git-based repository system like GitHub, GitLab, or Bitbucket for source code management.
   - Enforce branching and merging policies to maintain code stability.

2. *Automated Build*
   - Configure tools like Jenkins, CircleCI, or GitHub Actions to automatically build the application whenever code is committed or merged into the main branch.
   - Ensure builds for both Android and iOS platforms are generated.

3. *Automated Testing*
   - Implement unit tests, integration tests, and UI tests to validate new features or updates.
   - Use frameworks like Jest, Mocha, or JUnit for backend testing and Appium or Espresso for mobile app testing.
   - Automatically run tests as part of the CI pipeline.

4. *Code Quality and Security Analysis*
   - Integrate tools like SonarQube for static code analysis to maintain code quality.
   - Use security scanners to identify vulnerabilities in code dependencies.

5. *Notification and Feedback*
   - Notify the development team via Slack, email, or other channels about build and test results.

---

### 8.2 Continuous Deployment (CD)

CD automates the release process, ensuring smooth updates to production with minimal downtime. Key CD requirements include:

1. *Staging Environment*
   - Set up a staging environment to test features in a production-like setting.
   - Allow manual approval before deploying to production.

2. *Automated Deployment*
   - Use tools like Jenkins, GitLab CI/CD, or AWS CodePipeline to automate deployment to servers or app stores.
   - Implement zero-downtime deployment strategies using techniques like blue-green or canary deployment.

3. *Versioning and Rollback*
   - Maintain a versioning system for each release to track changes.
   - Enable rollback to the previous stable version in case of deployment issues.

4. *Monitoring and Logging*
   - Integrate tools like ELK Stack, New Relic, or Datadog for application performance monitoring.
   - Monitor deployment logs and handle exceptions or errors.

5. *App Store Deployment*
   - Automate submission of app updates to the Google Play Store and Apple App Store using tools like Fastlane.

---

### 8.3 CI/CD Workflow Summary

1. *Developer Commit*
   - Developers commit code changes to the repository.
   - Trigger CI pipeline.

2. *Build and Test*
   - Automated builds are generated.
   - Unit, integration, and UI tests are executed.

3. *Code Quality Check*
   - Static code analysis and security scans are performed.

4. *Deployment to Staging*
   - If tests pass, the build is deployed to the staging environment.
   - QA and stakeholder approval.

5. *Production Deployment*
   - Post-approval, the build is deployed to the production environment or app stores.
   - Application monitoring ensures smooth operation.

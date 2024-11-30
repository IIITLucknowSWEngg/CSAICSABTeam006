# Scope of the Project: InDrive App

## Software Scope

The **InDrive App** aims to provide a comprehensive platform for ride-sharing and carpooling services. The app is designed to connect drivers with passengers, optimize travel routes, and facilitate secure and seamless payments. The focus is on creating an eco-friendly, cost-effective, and user-friendly solution for urban and intercity transportation.

---

### Objectives
- Build a robust platform for ride-sharing with intuitive navigation and matching algorithms.
- Ensure user security through identity verification and real-time tracking.
- Provide features for efficient route optimization and pricing calculations.
- Support multi-lingual content and local currency transactions for a global audience.

---

### Target Audience
- **Drivers**: Individuals offering rides for personal or professional purposes.
- **Passengers**: Users looking for convenient, affordable, and eco-friendly travel options.
- **Administrators**: Personnel managing user data, trip logs, and system analytics.

---

### Exclusions
The current scope excludes features like autonomous vehicle integration, AR for route visualization, and blockchain-based payment systems, which may be considered in future iterations.

---

## Methodology

The development of the **InDrive App** will follow the **Agile Software Development** methodology, enabling flexibility, iterative updates, and stakeholder collaboration.

### Key Phases

#### 1. **Requirements Gathering**
- Collect functional and non-functional requirements, including:
  - User Management (Drivers and Passengers)
  - Trip Management
  - Payment Gateway Integration
  - Real-Time Tracking and Notifications

#### 2. **Planning and Design**
- **Front-End**: Use **Flutter** for cross-platform compatibility.
- **Back-End**: RESTful API services powered by **Node.js**.
- **Database**: Use **PostgreSQL** for secure and scalable data storage.
- Wireframe core features like user registration, trip booking, and payments.

#### 3. **Development**
- Iterative sprints for manageable progress:
  - Sprint 1: User Authentication, Profile Setup
  - Sprint 2: Trip Booking and Matching
  - Sprint 3: Payment Integration
  - Sprint 4: Real-Time Tracking and Notifications

#### 4. **Testing**
- Conduct comprehensive testing:
  - **Unit Testing**: Validate individual components.
  - **Integration Testing**: Verify the interaction between modules.
  - **Performance Testing**: Simulate high user loads.
  - **Security Testing**: Ensure data protection and encryption.

#### 5. **Deployment**
- Deploy on **AWS** or **Google Cloud** for scalability.
- Implement CI/CD pipelines for seamless updates.
- Enable disaster recovery mechanisms with regular backups.

#### 6. **Maintenance and Iteration**
- Gather user feedback post-launch and prioritize updates.
- Monitor performance using tools like **New Relic** or **Google Analytics**.

---

## Included Features

### Core Features
| **Feature**             | **Description**                                              | **Status**    |
|-------------------------|-------------------------------------------------------------|---------------|
| **User Registration**    | Sign-up for drivers and passengers.                         | ✅ |
| **Login/Authentication** | Secure login with password encryption and OTP.              | ✅ |
| **Profile Management**   | Edit personal and vehicle details.                          | ✅ |
| **Ride Matching**         | Match drivers and passengers based on location and route.  | ✅ |
| **Trip Booking**         | Book rides with estimated time and cost.                   | ✅ |
| **Payment Gateway**      | Integrate multiple payment options (UPI, cards, wallets).   | ✅ |
| **Real-Time Tracking**   | GPS-enabled trip tracking for safety.                       | ✅ |
| **Notifications**        | Alerts for booking confirmation, updates, and payments.     | ✅ |
| **User Reviews**         | Allow users to rate rides and provide feedback.             | ✅ |
| **Admin Dashboard**      | Interface for system monitoring and management.             | ✅ |

---

### Advanced Features
| **Feature**              | **Description**                                            | **Status**    |
|--------------------------|-----------------------------------------------------------|---------------|
| **Route Optimization**    | AI-powered shortest and most cost-efficient routes.       | ✅ |
| **Fare Estimation**       | Dynamic pricing based on distance, time, and demand.      | ✅ |
| **Loyalty Rewards**       | Points for frequent users redeemable for discounts.       | ✅ |
| **Emergency Assistance**  | SOS feature for user safety during rides.                 | ✅ |
| **Multi-Language Support**| Content available in regional languages.                 | ✅ |
| **Carpooling Options**    | Option to share rides for cost-sharing.                   | ✅ |
| **Admin Analytics**       | Dashboard for analyzing user and system data.             | ✅ |

---

### Integrations
| **Integration**          | **Description**                                            | **Status**    |
|--------------------------|-----------------------------------------------------------|---------------|
| **Maps Integration**      | Use Google Maps or Mapbox for route and trip details.     | ✅ |
| **Payment Systems**       | Integrate PayPal, Stripe, and UPI.                        | ✅ |
| **SMS/Email Notifications**| Notify users of updates via SMS and email.               | ✅ |

---

## Excluded Features

### Excluded Features
| **Feature**               | **Description**                                          | **Status**    |
|---------------------------|---------------------------------------------------------|---------------|
| **Autonomous Vehicles**    | Integration with self-driving cars.                    | ❌ |
| **AR for Routes**          | Augmented reality navigation and route visualization.  | ❌ |
| **Blockchain Payments**    | Cryptocurrency-based payment systems.                  | ❌ |

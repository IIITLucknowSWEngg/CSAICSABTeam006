
| **Test Scenario**       | **Happy Path**                           | **Error Path**                          | **Abused Path**                       |
|--------------------------|------------------------------------------|-----------------------------------------|---------------------------------------|
| **User Registration**    | User is successfully registered.        | Registration fails due to invalid data.| User temporarily blocked for abuse.  |
| **Booking a Ride**       | Ride successfully booked.               | Booking fails due to errors.           | User restricted for abuse.           |
| **Fare Negotiation**     | Fare negotiation successful.            | No drivers accept fare.                | User restricted for abuse.           |
| **Payment**              | Payment completed successfully.         | Payment fails due to insufficient funds.| User flagged for abuse.              |
| **Driver Ratings**       | Rating successfully submitted.          | Submission fails due to missing data.  | User restricted for abuse.           |
| **Location Tracking**    | Tracking displayed in real time.        | Tracking fails due to GPS issues.      | Tracking restricted for abuse.       |
| **Push Notifications**   | Notifications delivered successfully.   | Notification delivery fails and retries.| Spam handled via throttling.         |
| **Customer Support**     | Support ticket created successfully.    | Submission fails due to insufficient info.| User restricted for abuse.         |
| **Driver Registration**  | Driver successfully registered.         | Registration fails due to missing docs.| Driver flagged and banned for abuse. |

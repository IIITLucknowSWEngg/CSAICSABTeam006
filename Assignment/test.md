# Test Results for InDrive  

### Project Name: InDrive  
### Description: InDrive is a ride-hailing app focusing on fare negotiation, real-time location tracking, and user-friendly ride management.  

---  

## Test Results  

### 1. User Registration  
#### Description: A user registers for the app by providing valid details.  

| Test Case       | Input                     | Expected Output                                                                 | Result                                   |
|------------------|---------------------------|---------------------------------------------------------------------------------|-----------------------------------------|
| **Happy Path**   | Valid phone number and OTP | User is successfully registered and redirected to the home screen.              | **Pass**: User registered successfully. |
| **Error Path**   | Invalid phone number format | Registration fails, showing "Invalid phone number format."                      | **Pass**: Error message displayed.      |
| **Abused Path**  | Invalid OTP attempts (5+) | Registration fails, and the user is temporarily blocked for further attempts.   | **Pass**: User temporarily blocked.     |

---  

### 2. Booking a Ride  
#### Description: A user books a ride by entering pickup and drop-off locations.  

| Test Case       | Input                     | Expected Output                                                                 | Result                                   |
|------------------|---------------------------|---------------------------------------------------------------------------------|-----------------------------------------|
| **Happy Path**   | Valid locations and fare | Ride is successfully booked, and a driver is assigned.                         | **Pass**: Ride booked successfully.     |
| **Error Path**   | Invalid pickup location  | Booking fails, displaying "Invalid location. Please try again."                 | **Pass**: Error message displayed.      |
| **Abused Path**  | Rapid location changes   | Booking is restricted temporarily due to suspicious behavior.                   | **Pass**: Abuse detected, user restricted.|

---  

### 3. Fare Negotiation  
#### Description: A user negotiates the fare with a driver.  

| Test Case       | Input                     | Expected Output                                                                 | Result                                   |
|------------------|---------------------------|---------------------------------------------------------------------------------|-----------------------------------------|
| **Happy Path**   | Reasonable proposed fare | Fare is accepted by the driver, and the ride is confirmed.                     | **Pass**: Negotiation successful.       |
| **Error Path**   | No driver accepts fare   | Booking fails, showing "No drivers available for the proposed fare."           | **Pass**: Error message displayed.      |
| **Abused Path**  | Multiple lowball offers  | User is restricted from further negotiations temporarily.                       | **Pass**: Abuse detected, user restricted.|

---  

### 4. Payment  
#### Description: A user completes a payment after a ride.  

| Test Case       | Input                     | Expected Output                                                                 | Result                                   |
|------------------|---------------------------|---------------------------------------------------------------------------------|-----------------------------------------|
| **Happy Path**   | Valid payment details     | Payment is processed successfully, and the receipt is displayed.               | **Pass**: Payment completed.            |
| **Error Path**   | Insufficient wallet balance | Payment fails, showing "Insufficient funds. Please add money or choose another method." | **Pass**: Error message displayed.      |
| **Abused Path**  | Multiple failed payment attempts | Account flagged for suspicious behavior, and further payments are blocked temporarily. | **Pass**: User flagged for abuse.       |

---  

### 5. Driver Ratings  
#### Description: A user rates a driver after completing a ride.  

| Test Case       | Input                     | Expected Output                                                                 | Result                                   |
|------------------|---------------------------|---------------------------------------------------------------------------------|-----------------------------------------|
| **Happy Path**   | Valid rating and feedback | Rating is saved successfully, and the driver’s profile is updated.              | **Pass**: Rating submitted.             |
| **Error Path**   | No rating provided       | Submission fails, showing "Rating cannot be empty."                             | **Pass**: Error message displayed.      |
| **Abused Path**  | Spamming ratings         | User is restricted from submitting ratings for a period.                        | **Pass**: Abuse detected, user restricted.|

---  

### 6. Location Tracking  
#### Description: A user tracks their ride in real time.  

| Test Case       | Input                     | Expected Output                                                                 | Result                                   |
|------------------|---------------------------|---------------------------------------------------------------------------------|-----------------------------------------|
| **Happy Path**   | Valid ride in progress    | The app displays the driver’s real-time location and estimated arrival time.    | **Pass**: Tracking displayed.           |
| **Error Path**   | GPS disabled             | Tracking fails, showing "Please enable location services to track your ride."   | **Pass**: Error message displayed.      |
| **Abused Path**  | Frequent location refresh | User’s tracking is temporarily delayed due to excessive requests.               | **Pass**: Abuse detected, tracking restricted.|

---  

### 7. Push Notifications  
#### Description: Notify users about ride updates.  

| Test Case       | Input                     | Expected Output                                                                 | Result                                   |
|------------------|---------------------------|---------------------------------------------------------------------------------|-----------------------------------------|
| **Happy Path**   | Valid ride status update  | User receives timely notifications for booking confirmation, driver arrival, and ride completion. | **Pass**: Notifications delivered.     |
| **Error Path**   | Notification failure     | Notification fails, logging the issue and retrying delivery.                    | **Pass**: Issue logged, retry successful.|
| **Abused Path**  | Excessive notifications (spam) | Notifications are throttled to prevent overload.                               | **Pass**: Spam handled appropriately.   |

---  

### 8. Customer Support  
#### Description: A user contacts customer support for ride issues.  

| Test Case       | Input                     | Expected Output                                                                 | Result                                   |
|------------------|---------------------------|---------------------------------------------------------------------------------|-----------------------------------------|
| **Happy Path**   | Valid issue submission    | Support ticket is created, and the user receives a response.                   | **Pass**: Ticket created successfully.  |
| **Error Path**   | Invalid issue description | Submission fails, showing "Please provide more details about the issue."       | **Pass**: Error message displayed.      |
| **Abused Path**  | Spamming support requests | User is restricted from submitting additional tickets temporarily.              | **Pass**: Abuse detected, user restricted.|

---  

### 9. Driver Registration  
#### Description: A driver registers for the app by providing valid details and documentation.  

| Test Case       | Input                     | Expected Output                                                                 | Result                                   |
|------------------|---------------------------|---------------------------------------------------------------------------------|-----------------------------------------|
| **Happy Path**   | Valid details and documents | Driver account is successfully created and activated.                          | **Pass**: Driver registered.            |
| **Error Path**   | Missing documents         | Registration fails, showing "All required documents must be uploaded."         | **Pass**: Error message displayed.      |
| **Abused Path**  | Fake or duplicate documents | Registration is flagged, and the driver is banned.                             | **Pass**: Abuse detected, driver banned.|

---  

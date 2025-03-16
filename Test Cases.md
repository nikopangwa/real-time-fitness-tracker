# Test Cases - Real-Time Fitness Tracker  

## Functional Test Cases  

| **Test Case ID** | **Requirement ID** | **Description** | **Steps** | **Expected Result** | **Actual Result** | **Status (Pass/Fail)** |
|----------------|----------------|----------------|---------|----------------|----------------|----------------|
| TC-001 | FR-01 | Track Real-Time Activity | 1. User starts workout. <br> 2. System retrieves data. <br> 3. System displays real-time metrics. | Live fitness metrics appear on the screen. | - | - |
| TC-002 | FR-02 | Set Personalized Fitness Goals | 1. User navigates to goal setting. <br> 2. Enters goal details. <br> 3. Clicks save. | Goal is saved successfully. | - | - |
| TC-003 | FR-03 | Receive Real-Time Workout Feedback | 1. User starts workout. <br> 2. System provides live feedback. | Feedback messages appear based on workout data. | - | - |
| TC-004 | FR-04 | View Fitness History | 1. User selects history section. <br> 2. System retrieves past workouts. | User sees past workouts with details. | - | - |
| TC-005 | FR-05 | Connect Wearable Device | 1. User selects "Connect Device". <br> 2. System scans for devices. <br> 3. User selects a device. | Device connects successfully. | - | - |
| TC-006 | FR-06 | Share Fitness Achievements on Social Media | 1. User completes a workout. <br> 2. Clicks "Share Achievement". <br> 3. Selects a social media platform. | Workout summary is posted on selected platform. | - | - |
| TC-007 | FR-07 | Receive Goal Achievement Notifications | 1. User completes a fitness goal. <br> 2. System detects completion. <br> 3. Notification is sent. | User receives a notification. | - | - |
| TC-008 | FR-08 | Compete in Fitness Challenges with Friends | 1. User starts a challenge. <br> 2. Invites friends. <br> 3. System tracks progress. | Challenge is created and friends are notified. | - | - |

---

## **Non-Functional Test Cases**  

| **Test Case ID** | **Requirement ID** | **Description** | **Steps** | **Expected Result** | **Actual Result** | **Status (Pass/Fail)** |
|----------------|----------------|----------------|---------|----------------|----------------|----------------|
| TC-009 | NFR-01 | Performance Test: Handle 1,000 concurrent users | 1. Simulate 1,000 users logging in simultaneously. <br> 2. Measure system response time. | System maintains response time ≤ 2 seconds. | - | - |
| TC-010 | NFR-02 | Security Test: Encrypt user data | 1. Register a new user. <br> 2. Check how password is stored in the database. | Password is encrypted using AES-256 and not stored in plaintext. | - | - |


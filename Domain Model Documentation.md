```mermaid
 Domain Model – Real-Time Fitness Tracker

Key Entities and Attributes

 1. User
- userId: String
- name: String
- email: String
- role: Enum {Athlete, Coach, Admin}

 2. WorkoutSession
- sessionId: String
- startTime: DateTime
- endTime: DateTime
- status: Enum {Scheduled, InProgress, Completed, Canceled}
- type: Enum {Cardio, Strength, HIIT}

 3. Device
- deviceId: String
- deviceType: String
- batteryLevel: Int
- status: Enum {Online, Offline}

4. FitnessData
- dataId: String
- heartRate: Int
- steps: Int
- calories: Float
- timestamp: DateTime

5. Goal
- goalId: String
- type: Enum {WeightLoss, Endurance, Strength}
- targetValue: Float
- currentProgress: Float
- status: Enum {InProgress, Achieved, Failed}
- 
 6. Notification
- notificationId: String
- message: String
- timestamp: DateTime
- read: Boolean

Relationships

- A **User** can participate in multiple **WorkoutSessions**.
- A **WorkoutSession** collects **FitnessData** in real time.
- Each **User** can own multiple **Devices**.
- A **Device** sends **FitnessData** to the system.
- **Users** can set multiple **Goals**.
- The system sends **Notifications** to **Users** based on progress or alerts.

## Business Logic Rules

- A **WorkoutSession** can only be "Completed" if it was "InProgress".
- A **Goal** automatically updates **status** based on currentProgress vs. targetValue.
- A **Device** must be "Online" to send **FitnessData".
- **Notifications** are marked as read when the user views them.

```


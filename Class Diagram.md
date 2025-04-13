```mermaid
classDiagram
class User {
  -userId: String
  -name: String
  -email: String
  -role: String
  +startSession()
  +viewProgress()
}

class WorkoutSession {
  -sessionId: String
  -startTime: DateTime
  -endTime: DateTime
  -status: String
  -type: String
  +start()
  +end()
}

class Device {
  -deviceId: String
  -deviceType: String
  -batteryLevel: Int
  -status: String
  +connect()
  +disconnect()
}

class FitnessData {
  -dataId: String
  -heartRate: Int
  -steps: Int
  -calories: Float
  -timestamp: DateTime
  +processData()
}

class Goal {
  -goalId: String
  -type: String
  -targetValue: Float
  -currentProgress: Float
  -status: String
  +updateProgress()
  +checkStatus()
}

class Notification {
  -notificationId: String
  -message: String
  -timestamp: DateTime
  -read: Boolean
  +markAsRead()
}

User "1" -- "0..*" WorkoutSession : participates in
User "1" -- "0..*" Goal : sets
User "1" -- "0..*" Notification : receives
User "1" -- "0..*" Device : owns
WorkoutSession "1" -- "0..*" FitnessData : collects
Device "1" -- "0..*" FitnessData : transmits

---

 Class Diagram Design Explanation

- **User** is the central actor who owns devices, receives notifications, and tracks fitness goals.
- **Device** transmits **FitnessData**, which is tied to **WorkoutSessions**.
- **Goal** and **Notification** entities personalize and enhance the fitness experience.
- Multiplicities show that users can have multiple sessions, goals, and devices.
- Operations (e.g., `markAsRead()`, `updateProgress()`) reflect essential system behaviors.
- Aggregation is implied (not explicitly drawn) in relationships like User → Device, where the lifecycle is independent.

---


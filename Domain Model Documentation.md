 classDiagram
class User {
- userId: String
- name: String
+ logWorkout()
+ trackProgress()
}
class Device {
- deviceId: String
- deviceType: String
+ syncData()
}
class WorkoutSession {
- sessionId: String
- startTime: DateTime
- endTime: DateTime
+ startSession()
+ endSession()
}
class FitnessData {
- dataId: String
- heartRate: Int
- steps: Int
+ calculateMetrics()
}
class Goal {
- goalId: String
- goalType: String
- targetValue: Int
+ updateProgress()
+ isAchieved()
}
class Notification {
- notificationId: String
- message: String
+ send()
}

User "1" -- "0..*" WorkoutSession : initiates
User "1" -- "1..*" Goal : sets
Device "1" -- "0..*" FitnessData : syncsTo
WorkoutSession "1" -- "1..*" FitnessData : records
Goal "1" --> "0..*" FitnessData : evaluates
User "1" -- "0..*" Notification : receives

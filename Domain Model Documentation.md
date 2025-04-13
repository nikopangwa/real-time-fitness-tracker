### Domain Model Table

| Entity       | Attributes                                 | Methods                          | Relationships                                     | Business Rules                                      |
|--------------|--------------------------------------------|----------------------------------|---------------------------------------------------|-----------------------------------------------------|
| User         | userId, name, email                        | register(), login(), logout()    | Has many Workouts, has one Profile                | A user must register before accessing the system.   |
| Workout      | workoutId, type, duration, date            | startWorkout(), endWorkout()     | Belongs to User, logs Metrics                     | A workout must have a type and duration.            |
| Profile      | profileId, age, weight, height             | updateProfile()                  | Belongs to User                                   | Profile data is used to personalize metrics.        |
| Metrics      | metricId, caloriesBurned, heartRate        | calculateCalories()              | Belongs to Workout                                | Metrics are generated after a workout session.      |
| Goal         | goalId, type, targetValue, status          | setGoal(), updateGoal()          | Belongs to User                                   | Users can set multiple goals.                       |
| Notification | notificationId, message, timestamp         | sendNotification()               | Sent to User                                      | Notifications trigger on goal updates/workouts.     |
| Device       | deviceId, name, batteryLevel               | syncData()                       | Associated with User (0..*)                        | A user can pair multiple devices.                   |




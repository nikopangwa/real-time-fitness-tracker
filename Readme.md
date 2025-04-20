

---

 Implemented Design Patterns

1. Simple Factory
- Centralized factory class that creates objects without exposing instantiation logic.
- Example: `WorkoutFactory.createWorkout("cardio")`

 2. Factory Method
- Abstract creator class with a factory method overridden by subclasses.
- Example: `Trainer.createPlan()` in subclasses like `YogaTrainer` and `StrengthTrainer`.

3. Abstract Factory
- Interface for creating families of related objects without specifying concrete classes.
- Example: `FitnessEquipmentFactory` producing related `Tracker` and `Device` objects.

 4. Builder
- Step-by-step construction of complex objects using a builder class.
- Example: `WorkoutPlanBuilder` constructs a customizable `WorkoutPlan`.

5. Prototype
- Cloning existing objects without coupling to their concrete classes.
- Example: `UserProfile.clone()` creates a deep copy of user settings.
6. Singleton
- Ensures a class has only one instance with a global access point.
- Example: `FitnessTrackerManager.getInstance()`.

---
Unit Testing

All patterns are tested using **JUnit 5**. Each test validates:
- Object creation correctness.
- Expected behavior.
- Pattern-specific functionality (e.g., single instance for Singleton, cloning for Prototype).

Run tests using:
```bash
./gradlew test





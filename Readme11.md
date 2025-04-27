
Real-Time Fitness Tracker - Persistence Repository
Project Overview
This project implements a persistence repository layer for the domain models of a real-time fitness tracker system. The repository layer uses an in-memory storage solution via HashMap to manage various entities like users, workouts, profiles, goals, notifications, and devices. The system follows the Repository Pattern to abstract the data access logic and support easy switching between storage solutions (e.g., in-memory storage, database, file system) in the future.

Key Features
In-memory repositories using HashMap for CRUD operations.

Support for various entities such as User, Workout, Profile, Goal, Notification, and Device.

Repository interfaces using Generics to avoid duplication across entity repositories.

Abstraction layer to allow switching storage backends in the future (e.g., using Dependency Injection or Factory Pattern).

Unit tests for each repository to ensure correct behavior.

Domain Entities
The following domain entities are supported by the persistence layer:

User: Represents a user of the fitness tracker.

Workout: Represents a workout session.

Profile: Represents a user's profile containing personal information.

Goal: Represents a fitness goal set by a user.

Notification: Represents a notification sent to users.

Device: Represents a fitness tracking device used by the user.

Setup Instructions
Clone the repository:

bash
Copy
Edit
git clone https://github.com/your-username/fitness-tracker-repository.git
cd fitness-tracker-repository
Build the project:

If you're using Maven, run the following command to build the project:

bash
Copy
Edit
mvn clean install
For Gradle users:

bash
Copy
Edit
gradle build
Run the unit tests:

After building the project, run the unit tests to ensure everything is working properly.

For Maven:

bash
Copy
Edit
mvn test
For Gradle:

bash
Copy
Edit
gradle test
Alternatively, you can run the tests directly from your IDE (e.g., IntelliJ IDEA, Eclipse).

Repository Structure
/src
Contains the main codebase, including:

Domain Models: Entity classes like User, Workout, etc.

Repositories: Interfaces and implementations for accessing data.

Factories: Abstraction mechanisms for swapping storage backends.

/repositories
Contains the repository interfaces and in-memory implementations for entities.

InMemory: Implementations using HashMap for in-memory storage.

Interfaces: Generic and entity-specific repository interfaces.

/factories
Contains factory classes for abstracting storage solutions.

/tests
Contains unit tests for each of the repositories. These tests verify CRUD operations, edge cases, and ensure the integrity of the data management logic.

/README.md
Contains the documentation and explanations of the project, how it works, and how to set it up.

Design Decisions
Generic Repository Interfaces: Used generics to create a flexible and reusable repository interface, eliminating the need to create separate repository classes for each entity.

In-Memory Storage: Implemented using HashMap for fast data retrieval and manipulation during testing. This in-memory solution will later be replaced with a more permanent storage backend, such as a database or file system, using abstraction layers.

Factory Pattern / Dependency Injection: The repository layer is abstracted using the Factory Pattern (or Dependency Injection) to allow easy switching of storage mechanisms (in-memory, database, file system) without modifying the business logic. The storage backend is injected into the services based on the required solution.

Future-Proofing
To ensure the system can scale and switch to a real database or other storage solutions in the future:

RepositoryFactory provides an abstraction layer for initializing repositories with different storage types (e.g., "MEMORY", "DATABASE").

FileSystemBookRepository (stub) is a future-proofing design example for integrating a file-based storage solution (e.g., storing data in JSON files).

Tests
Unit tests are written for all repository methods (CRUD operations):

UserRepositoryTest

WorkoutRepositoryTest

ProfileRepositoryTest

GoalRepositoryTest

NotificationRepositoryTest

DeviceRepositoryTest

Each test ensures that repositories correctly handle entities' lifecycle, such as creating, retrieving, updating, and deleting entities.

Example Usage
Here’s an example of how to use the in-memory repositories in the project:

java
Copy
Edit
public class Main {
    public static void main(String[] args) {
        // Example: Using InMemoryUserRepository
        InMemoryUserRepository userRepository = new InMemoryUserRepository();
        User newUser = new User("1", "John Doe", "john.doe@example.com");

        // Save user
        userRepository.save(newUser);

        // Retrieve user by ID
        User retrievedUser = userRepository.findById("1");
        System.out.println("Retrieved User: " + retrievedUser.getName());

        // Update user
        newUser.setName("Johnathan Doe");
        userRepository.save(newUser);

        // Delete user
        userRepository.delete("1");
    }
}

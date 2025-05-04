package services;

import entities.User;
import entities.Workout;
import entities.Goal;
import repositories.UserRepository;
import repositories.WorkoutRepository;
import repositories.GoalRepository;

import java.util.List;
import java.util.Optional;

// User Service
public class UserService {
    private final UserRepository userRepo;

    public UserService(UserRepository userRepo) {
        this.userRepo = userRepo;
    }

    public User createUser(User user) {
        return userRepo.save(user);
    }

    public Optional<User> getUserById(String id) {
        return userRepo.findById(id);
    }

    public List<User> getAllUsers() {
        return userRepo.findAll();
    }

    public User updateUser(User user) {
        return userRepo.save(user);
    }
}

package tests.services;

import entities.User;
import org.junit.jupiter.api.Test;
import repositories.inmemory.InMemoryUserRepository;
import services.UserService;

import static org.junit.jupiter.api.Assertions.*;

class UserServiceTest {

    @Test
    void testCreateUserStoresUserCorrectly() {
        InMemoryUserRepository repo = new InMemoryUserRepository();
        UserService service = new UserService(repo);

        User newUser = new User("u1", "Alice");
        User created = service.createUser(newUser);

        assertEquals("u1", created.getId());
        assertEquals("Alice", repo.findById("u1").get().getName());
    }
}

package tests.services;

import entities.Workout;
import org.junit.jupiter.api.Test;
import repositories.inmemory.InMemoryWorkoutRepository;
import services.WorkoutService;

import static org.junit.jupiter.api.Assertions.*;

class WorkoutServiceTest {

    @Test
    void testCompleteWorkoutMarksWorkoutAsCompleted() {
        InMemoryWorkoutRepository repo = new InMemoryWorkoutRepository();
        WorkoutService service = new WorkoutService(repo);

        Workout workout = new Workout("w1", "Pushups", false);
        repo.save(workout);

        Workout updated = service.completeWorkout("w1");

        assertTrue(updated.isCompleted());
        assertEquals("w1", updated.getId());
    }
}


package tests.services;

import entities.Goal;
import org.junit.jupiter.api.Test;
import repositories.inmemory.InMemoryGoalRepository;
import services.GoalService;

import static org.junit.jupiter.api.Assertions.*;

class GoalServiceTest {

    @Test
    void testAchieveGoalSetsStatusToAchieved() {
        InMemoryGoalRepository repo = new InMemoryGoalRepository();
        GoalService service = new GoalService(repo);

        Goal goal = new Goal("g1", "Run 5km", false);
        repo.save(goal);

        Goal achieved = service.achieveGoal("g1");

        assertTrue(achieved.isAchieved());
        assertEquals("g1", achieved.getId());
    }
}


// Workout Service
public class WorkoutService {
    private final WorkoutRepository workoutRepo;

    public WorkoutService(WorkoutRepository workoutRepo) {
        this.workoutRepo = workoutRepo;
    }

    public Workout createWorkout(Workout workout) {
        return workoutRepo.save(workout);
    }

    public Optional<Workout> getWorkoutById(String id) {
        return workoutRepo.findById(id);
    }

    public List<Workout> getAllWorkouts() {
        return workoutRepo.findAll();
    }

    public Workout updateWorkout(Workout workout) {
        return workoutRepo.save(workout);
    }

    public Workout markWorkoutComplete(String id) {
        Workout workout = workoutRepo.findById(id)
                .orElseThrow(() -> new RuntimeException("Workout not found"));
        workout.setCompleted(true);
        return workoutRepo.save(workout);
    }
}

// Goal Service
public class GoalService {
    private final GoalRepository goalRepo;

    public GoalService(GoalRepository goalRepo) {
        this.goalRepo = goalRepo;
    }

    public Goal createGoal(Goal goal) {
        return goalRepo.save(goal);
    }

    public Optional<Goal> getGoalById(String id) {
        return goalRepo.findById(id);
    }

    public List<Goal> getAllGoals() {
        return goalRepo.findAll();
    }

    public Goal updateGoal(Goal goal) {
        return goalRepo.save(goal);
    }

    public Goal markGoalAchieved(String id) {
        Goal goal = goalRepo.findById(id)
                .orElseThrow(() -> new RuntimeException("Goal not found"));
        goal.setAchieved(true);
        return goalRepo.save(goal);
    }
}

/tests
  └── /services
       ├── UserServiceTest.java
       ├── WorkoutServiceTest.java
       └── GoalServiceTest.java

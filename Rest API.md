/api
  ├── UserController.java
  ├── WorkoutController.java
  └── GoalController.java


package api;

import entities.User;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;
import services.UserService;

import java.util.List;

@RestController
@RequestMapping("/api/users")
public class UserController {

    private final UserService service;

    public UserController(UserService service) {
        this.service = service;
    }

    @GetMapping
    public List<User> getAllUsers() {
        return service.getAllUsers();
    }

    @PostMapping
    public ResponseEntity<User> createUser(@RequestBody User user) {
        return ResponseEntity.ok(service.createUser(user));
    }

    @GetMapping("/{id}")
    public ResponseEntity<User> getUser(@PathVariable String id) {
        return service.getUserById(id)
                .map(ResponseEntity::ok)
                .orElse(ResponseEntity.notFound().build());
    }
}


package api;

import entities.Workout;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;
import services.WorkoutService;

import java.util.List;

@RestController
@RequestMapping("/api/workouts")
public class WorkoutController {

    private final WorkoutService service;

    public WorkoutController(WorkoutService service) {
        this.service = service;
    }

    @GetMapping
    public List<Workout> getAllWorkouts() {
        return service.getAllWorkouts();
    }

    @PostMapping
    public ResponseEntity<Workout> createWorkout(@RequestBody Workout workout) {
        return ResponseEntity.ok(service.createWorkout(workout));
    }

    @PostMapping("/{id}/complete")
    public ResponseEntity<Workout> completeWorkout(@PathVariable String id) {
        return ResponseEntity.ok(service.completeWorkout(id));
    }
}


package api;

import entities.Goal;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;
import services.GoalService;

import java.util.List;

@RestController
@RequestMapping("/api/goals")
public class GoalController {

    private final GoalService service;

    public GoalController(GoalService service) {
        this.service = service;
    }

    @GetMapping
    public List<Goal> getAllGoals() {
        return service.getAllGoals();
    }

    @PostMapping
    public ResponseEntity<Goal> createGoal(@RequestBody Goal goal) {
        return ResponseEntity.ok(service.createGoal(goal));
    }

    @PostMapping("/{id}/achieve")
    public ResponseEntity<Goal> achieveGoal(@PathVariable String id) {
        return ResponseEntity.ok(service.achieveGoal(id));
    }
}


package api;

import entities.*;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;
import services.*;

import java.util.List;

@RestController
@RequestMapping("/api/users")
public class UserController {
    private final UserService service;
    public UserController(UserService service) {
        this.service = service;
    }
    @GetMapping
    public List<User> getAllUsers() {
        return service.getAllUsers();
    }
    @PostMapping
    public ResponseEntity<User> createUser(@RequestBody User user) {
        return ResponseEntity.ok(service.createUser(user));
    }
    @GetMapping("/{id}")
    public ResponseEntity<User> getUser(@PathVariable String id) {
        return service.getUserById(id)
                .map(ResponseEntity::ok)
                .orElse(ResponseEntity.notFound().build());
    }
}

@RestController
@RequestMapping("/api/workouts")
public class WorkoutController {
    private final WorkoutService service;
    public WorkoutController(WorkoutService service) {
        this.service = service;
    }
    @GetMapping
    public List<Workout> getAllWorkouts() {
        return service.getAllWorkouts();
    }
    @PostMapping
    public ResponseEntity<Workout> createWorkout(@RequestBody Workout workout) {
        return ResponseEntity.ok(service.createWorkout(workout));
    }
    @PostMapping("/{id}/complete")
    public ResponseEntity<Workout> completeWorkout(@PathVariable String id) {
        return ResponseEntity.ok(service.completeWorkout(id));
    }
}

@RestController
@RequestMapping("/api/goals")
public class GoalController {
    private final GoalService service;
    public GoalController(GoalService service) {
        this.service = service;
    }
    @GetMapping
    public List<Goal> getAllGoals() {
        return service.getAllGoals();
    }
    @PostMapping
    public ResponseEntity<Goal> createGoal(@RequestBody Goal goal) {
        return ResponseEntity.ok(service.createGoal(goal));
    }
    @PostMapping("/{id}/achieve")
    public ResponseEntity<Goal> achieveGoal(@PathVariable String id) {
        return ResponseEntity.ok(service.achieveGoal(id));
    }
}


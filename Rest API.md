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


package api;

import entities.User;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;
import services.UserService;

import java.util.List;

@RestController
@RequestMapping("/api/users")
public class UserController {

    private final UserService userService;

    public UserController(UserService userService) {
        this.userService = userService;
    }

    @GetMapping
    public ResponseEntity<List<User>> getAllUsers() {
        return ResponseEntity.ok(userService.getAllUsers());
    }

    @PostMapping
    public ResponseEntity<User> createUser(@RequestBody User user) {
        return ResponseEntity.ok(userService.createUser(user));
    }

    @PutMapping("/{id}")
    public ResponseEntity<User> updateUser(@PathVariable String id, @RequestBody User user) {
        return ResponseEntity.ok(userService.updateUser(id, user));
    }

    @PostMapping("/{id}/activate")
    public ResponseEntity<User> activateUser(@PathVariable String id) {
        return ResponseEntity.ok(userService.activateUser(id));
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

    private final WorkoutService workoutService;

    public WorkoutController(WorkoutService workoutService) {
        this.workoutService = workoutService;
    }

    @GetMapping
    public ResponseEntity<List<Workout>> getAllWorkouts() {
        return ResponseEntity.ok(workoutService.getAllWorkouts());
    }

    @PostMapping
    public ResponseEntity<Workout> createWorkout(@RequestBody Workout workout) {
        return ResponseEntity.ok(workoutService.createWorkout(workout));
    }

    @PutMapping("/{id}")
    public ResponseEntity<Workout> updateWorkout(@PathVariable String id, @RequestBody Workout workout) {
        return ResponseEntity.ok(workoutService.updateWorkout(id, workout));
    }

    @PostMapping("/{id}/complete")
    public ResponseEntity<Workout> completeWorkout(@PathVariable String id) {
        return ResponseEntity.ok(workoutService.completeWorkout(id));
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

    private final GoalService goalService;

    public GoalController(GoalService goalService) {
        this.goalService = goalService;
    }

    @GetMapping
    public ResponseEntity<List<Goal>> getAllGoals() {
        return ResponseEntity.ok(goalService.getAllGoals());
    }

    @PostMapping
    public ResponseEntity<Goal> createGoal(@RequestBody Goal goal) {
        return ResponseEntity.ok(goalService.createGoal(goal));
    }

    @PutMapping("/{id}")
    public ResponseEntity<Goal> updateGoal(@PathVariable String id, @RequestBody Goal goal) {
        return ResponseEntity.ok(goalService.updateGoal(id, goal));
    }

    @PostMapping("/{id}/achieve")
    public ResponseEntity<Goal> markGoalAchieved(@PathVariable String id) {
        return ResponseEntity.ok(goalService.markGoalAchieved(id));
    }
}


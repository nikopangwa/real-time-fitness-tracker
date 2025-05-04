<dependency>
  <groupId>org.springdoc</groupId>
  <artifactId>springdoc-openapi-starter-webmvc-ui</artifactId>
  <version>2.2.0</version>
</dependency>


@RestController
@RequestMapping("/api/users")
@Tag(name = "Users", description = "Endpoints for managing users")
public class UserController {

    @Operation(summary = "Get all users")
    @ApiResponse(responseCode = "200", description = "List of users")
    @GetMapping
    public List<User> getAllUsers() {
        return userService.getAllUsers();
    }

    @Operation(summary = "Create a new user")
    @ApiResponse(responseCode = "201", description = "User created")
    @PostMapping
    public ResponseEntity<User> createUser(@RequestBody User user) {
        User saved = userService.createUser(user);
        return new ResponseEntity<>(saved, HttpStatus.CREATED);
    }

    @Operation(summary = "Update user by ID")
    @ApiResponses({
        @ApiResponse(responseCode = "200", description = "User updated"),
        @ApiResponse(responseCode = "404", description = "User not found")
    })
    @PutMapping("/{id}")
    public User updateUser(@PathVariable String id, @RequestBody User user) {
        return userService.updateUser(id, user);
    }
}


openapi: 3.0.1
info:
  title: Real-Time Fitness Tracker API
  description: API for managing users, workouts, and goals
  version: 1.0.0
paths:
  /api/users:
    get:
      summary: Get all users
      responses:
        '200':
          description: OK
    post:
      summary: Create a new user
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/User'
      responses:
        '201':
          description: User created
  /api/users/{id}:
    put:
      summary: Update a user
      parameters:
        - name: id
          in: path
          required: true
          schema:
            type: string
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/User'
      responses:
        '200':
          description: User updated
        '404':
          description: User not found
components:
  schemas:
    User:
      type: object
      properties:
        id:
          type: string
        name:
          type: string
        email:
          type: string


openapi: 3.0.1
info:
  title: Real-Time Fitness Tracker API
  description: API for managing users, workouts, and goals
  version: 1.0.0
servers:
  - url: http://localhost:8080

paths:
  /api/users:
    get:
      summary: Get all users
      responses:
        '200':
          description: List of users
    post:
      summary: Create a new user
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/User'
      responses:
        '201':
          description: User created

  /api/users/{id}:
    put:
      summary: Update an existing user
      parameters:
        - in: path
          name: id
          required: true
          schema:
            type: string
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/User'
      responses:
        '200':
          description: User updated
        '404':
          description: User not found

  /api/workouts:
    get:
      summary: Get all workouts
      responses:
        '200':
          description: List of workouts
    post:
      summary: Create a new workout
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/Workout'
      responses:
        '201':
          description: Workout created

  /api/workouts/{id}:
    put:
      summary: Update an existing workout
      parameters:
        - in: path
          name: id
          required: true
          schema:
            type: string
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/Workout'
      responses:
        '200':
          description: Workout updated

  /api/goals:
    get:
      summary: Get all goals
      responses:
        '200':
          description: List of goals
    post:
      summary: Create a new goal
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/Goal'
      responses:
        '201':
          description: Goal created

  /api/goals/{id}:
    put:
      summary: Update an existing goal
      parameters:
        - in: path
          name: id
          required: true
          schema:
            type: string
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/Goal'
      responses:
        '200':
          description: Goal updated

components:
  schemas:
    User:
      type: object
      properties:
        id:
          type: string
        name:
          type: string
        email:
          type: string

    Workout:
      type: object
      properties:
        id:
          type: string
        type:
          type: string
        duration:
          type: integer
          format: int32

    Goal:
      type: object
      properties:
        id:
          type: string
        userId:
          type: string
        description:
          type: string
        target:
          type: integer




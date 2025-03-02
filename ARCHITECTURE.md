'''mermaid
C4Context
    title System Context diagram for Real-Time Fitness Tracker

    Person(user, "Fitness User", "A person who wants to track their fitness activities and health metrics")
    
    System(fitnessTracker, "Real-Time Fitness Tracker", "Allows users to track fitness activities, set goals, analyze performance, and receive recommendations")
    
    System_Ext(wearableDevices, "Wearable Devices", "Physical fitness trackers that collect user activity data")
    System_Ext(healthAPIs, "Health Platforms", "Third-party health data platforms like Apple Health and Google Fit")
    System_Ext(socialMedia, "Social Media Platforms", "Platforms for sharing achievements and connecting with friends")
    System_Ext(nutritionApps, "Nutrition Applications", "Third-party apps for tracking food intake and nutrition")
    
    Rel(user, fitnessTracker, "Uses")
    Rel(wearableDevices, fitnessTracker, "Sends activity data to")
    Rel(fitnessTracker, healthAPIs, "Exchanges health data with")
    Rel(fitnessTracker, socialMedia, "Shares achievements on")
    Rel(fitnessTracker, nutritionApps, "Integrates nutrition data from")
    Rel(user, wearableDevices, "Wears and interacts with")
    '''

    '''mermaid
  C4Container
    title Container diagram for Real-Time Fitness Tracker

    Person(user, "Fitness User", "A person who wants to track their fitness activities and health metrics")
    
    System_Boundary(fitnessTrackerSystem, "Real-Time Fitness Tracker") {
        Container(webApp, "Web Application", "React, TypeScript", "Provides all fitness tracking functionality via web browser")
        Container(mobileApp, "Mobile Application", "React Native", "Provides all fitness tracking functionality via mobile device")
        Container(apiGateway, "API Gateway", "Express.js, Node.js", "Handles API requests from applications and devices")
        Container(realTimeService, "Real-Time Service", "Node.js, Socket.io", "Processes and distributes real-time fitness data")
        Container(userService, "User Service", "Node.js, Express", "Handles user authentication and profile management")
        Container(activityService, "Activity Service", "Node.js, Express", "Manages workout data and activity tracking")
        Container(analyticsService, "Analytics Service", "Python, Flask", "Analyzes user performance and generates insights")
        Container(recommendationEngine, "Recommendation Engine", "Python, ML Models", "Generates personalized workout recommendations")
        Container(notificationService, "Notification Service", "Node.js", "Sends alerts and reminders to users")
        ContainerDb(database, "Database", "MongoDB", "Stores user profiles, activities, and analytics data")
        ContainerDb(dataWarehouse, "Data Warehouse", "PostgreSQL", "Stores historical and aggregated data for analysis")
    }
    
    System_Ext(wearableDevices, "Wearable Devices", "Physical fitness trackers")
    System_Ext(healthAPIs, "Health Platforms", "Third-party health platforms")
    System_Ext(socialMedia, "Social Media", "Social platforms")
    System_Ext(nutritionApps, "Nutrition Apps", "Nutrition tracking apps")
    
    Rel(user, webApp, "Uses", "HTTPS")
    Rel(user, mobileApp, "Uses", "HTTPS")
    Rel(webApp, apiGateway, "Makes API calls to", "JSON/HTTPS")
    Rel(mobileApp, apiGateway, "Makes API calls to", "JSON/HTTPS")
    Rel(mobileApp, realTimeService, "Subscribes to real-time updates", "WebSockets")
    Rel(webApp, realTimeService, "Subscribes to real-time updates", "WebSockets")
    Rel(apiGateway, userService, "Routes user requests to", "JSON/HTTPS")
    Rel(apiGateway, activityService, "Routes activity requests to", "JSON/HTTPS")
    Rel(apiGateway, analyticsService, "Routes analytics requests to", "JSON/HTTPS")
    Rel(realTimeService, activityService, "Sends real-time data to", "Message Queue")
    Rel(activityService, database, "Reads from and writes to", "MongoDB Driver")
    Rel(userService, database, "Reads from and writes to", "MongoDB Driver")
    Rel(analyticsService, database, "Reads from", "MongoDB Driver")
    Rel(analyticsService, dataWarehouse, "Reads from and writes to", "SQL")
    Rel(analyticsService, recommendationEngine, "Requests recommendations from", "REST")
    Rel(recommendationEngine, dataWarehouse, "Reads historical data from", "SQL")
    Rel(notificationService, recommendationEngine, "Receives scheduled recommendations from", "Message Queue")
    Rel(notificationService, mobileApp, "Sends push notifications to", "Firebase")
    Rel(wearableDevices, apiGateway, "Sends data to", "JSON/HTTPS")
    Rel(apiGateway, healthAPIs, "Exchanges data with", "JSON/HTTPS")
    Rel(apiGateway, socialMedia, "Posts achievements to", "OAuth/REST")
    Rel(apiGateway, nutritionApps, "Retrieves nutrition data from", "REST")
    '''


    '''mermaid
    C4Component
    title Component diagram for Activity Service

    Container_Boundary(activityService, "Activity Service") {
        Component(activityController, "Activity Controller", "Express Router", "Handles HTTP requests related to activities and workouts")
        Component(activityManager, "Activity Manager", "TypeScript", "Business logic for processing activity data")
        Component(workoutProcessor, "Workout Processor", "TypeScript", "Processes and validates workout data")
        Component(goalTracker, "Goal Tracker", "TypeScript", "Tracks user progress toward fitness goals")
        Component(metricCalculator, "Metric Calculator", "TypeScript", "Calculates derived metrics from raw activity data")
        Component(deviceConnector, "Device Connector", "TypeScript", "Handles data from various wearable devices")
        Component(dataValidator, "Data Validator", "TypeScript", "Validates incoming fitness data")
        Component(activityRepository, "Activity Repository", "TypeScript", "Data access layer for activity data")
        Component(goalRepository, "Goal Repository", "TypeScript", "Data access layer for goal data")
        Component(eventEmitter, "Event Emitter", "TypeScript", "Publishes events to the message queue")
    }
    
    ContainerDb(database, "Database", "MongoDB", "Stores user activities and goals")
    Container(realTimeService, "Real-Time Service", "Node.js", "Distributes real-time updates")
    Container(apiGateway, "API Gateway", "Express.js", "Routes API requests")
    Container(notificationService, "Notification Service", "Node.js", "Sends notifications")
    
    Rel(apiGateway, activityController, "Sends activity requests to", "REST")
    Rel(activityController, activityManager, "Uses")
    Rel(activityManager, workoutProcessor, "Uses")
    Rel(activityManager, goalTracker, "Uses")
    Rel(activityManager, metricCalculator, "Uses")
    Rel(workoutProcessor, deviceConnector, "Uses")
    Rel(deviceConnector, dataValidator, "Uses")
    Rel(activityManager, activityRepository, "Uses")
    Rel(goalTracker, goalRepository, "Uses")
    Rel(activityRepository, database, "Reads from and writes to", "MongoDB Driver")
    Rel(goalRepository, database, "Reads from and writes to", "MongoDB Driver")
    Rel(goalTracker, eventEmitter, "Publishes goal events to")
    Rel(activityManager, eventEmitter, "Publishes activity events to")
    Rel(eventEmitter, realTimeService, "Sends events to", "Message Queue")
    Rel(eventEmitter, notificationService, "Sends achievement notifications to", "Message Queue")
    '''

    # Architectural Design

## C4 Model Diagrams

### 1. Context Diagram

[C4 Context Diagram showing the system and its interactions with users, wearable devices, and external systems]

The Context Diagram illustrates how the Real-Time Fitness Tracker interacts with:
- Fitness Users who directly use the system
- Wearable Devices that provide fitness data
- External Health Platforms for data exchange
- Social Media Platforms for sharing achievements
- Nutrition Applications for integrated health tracking

### 2. Container Diagram

[C4 Container Diagram showing the high-level technical components of the system]

The Container Diagram breaks down the system into its major components:
- Web Application: Browser-based interface for users
- Mobile Application: Native mobile interface for iOS and Android
- API Gateway: Central entry point for all client requests
- Real-Time Service: Manages websocket connections for live updates
- User Service: Handles authentication and user management
- Activity Service: Processes fitness activities and workouts
- Analytics Service: Analyzes user performance data
- Recommendation Engine: Generates personalized fitness suggestions
- Notification Service: Manages user alerts and reminders
- Database: Stores user data, activities, and metrics
- Data Warehouse: Stores historical data for analysis

### 3. Component Diagram for Activity Service

[C4 Component Diagram showing the detailed components of the Activity Service]

The Component Diagram for the Activity Service illustrates its internal structure:
- Activity Controller: Handles HTTP requests
- Activity Manager: Core business logic
- Workout Processor: Validates and processes workouts
- Goal Tracker: Monitors progress toward fitness goals
- Metric Calculator: Derives fitness metrics from raw data
- Device Connector: Interfaces with different wearable devices
- Data Validator: Ensures data quality and integrity
- Activity Repository: Data access for activity records
- Goal Repository: Data access for user goals
- Event Emitter: Publishes events to other system components

### 4. End-to-End Components

The system architecture ensures end-to-end functionality through:

1. **Data Collection Layer**
   - Wearable device integration
   - Manual activity input
   - Third-party API connections

2. **Data Processing Layer**
   - Real-time data validation
   - Metric calculation
   - Data transformation

3. **Business Logic Layer**
   - Activity management
   - Goal tracking
   - User profile management
   - Recommendation generation

4. **Presentation Layer**
   - Web interface
   - Mobile application
   - Notification system
   - Data visualization

5. **Integration Layer**
   - Health platform connections
   - Social media sharing
   - Nutrition app integration

6. **Data Storage Layer**
   - User profile database
   - Activity and metrics database
   - Historical data warehouse
   - Caching system
    


    

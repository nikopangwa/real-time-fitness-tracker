# [Real-Time-Fitness-Tracker] - Architectural Modeling (C4 Diagrams)

## Introduction

**Project Title:** [Real-Time Fitness Tracker]
**Domain:** [Heathcare: This systems purpose is to improve health monitoring and fitnes tracking]
**Problem Statement:** [Provide users with health metrics and real-time  tracking of fitness activities ]
**Individual Scope:** [The project focuses on main features of heart rate monitoring, step counting, activity logging and fitness tracking which are doable within a given timeframe]

## C4 Diagrams 

### System Context Diagram

'''mermaid
C4Context
    title System Context Diagram for [Real-Time Fitness Tracker]
    Person(user, "User", "A person tracking their fitness.")
    System([Real-Time Fitness Tracker], "[Real-Time-Fitness-Tracker]", "Tracks health metrics and fitness activities.")
    External_System(device, "Fitness Device", "Provides sensor data.")
    External_System(cloud, "Cloud Services", "Stores and processes data.")

    Rel(user, [Real-Time Fitness Tracker], "Uses")
    Rel(device, [Real-Time Fitness Tracker], "Sends data to ")
    Rel([Real-Time Fitness Tracker], cloud, "Stores data in ")

    
C4Container
    title Container Diagram for [Real-Time Fitness Tracker]
    Container(mobile, "Mobile App", "Mobile application for users.", "Kotlin/Swift")
    Container(api, "API Server", "Handles data processing and communication.", "Node.js/Python")
    Container(database, "Database", "Stores user data.", "PostgreSQL/MongoDB")
    Container(auth, "Authentication Service", "Handles user authentication.", "OAuth 2.0")

    Rel(mobile, api, "uses API")
    Rel(api, database, "Stores data in")
    Rel(mobile, auth, "Authenticates with")
    Rel(api, auth, "Authenticates with")

C4Component
    title Component Diagram for API Server
    Container(api, "API Server", "Handles data processing and communication.", "Node.js/Python")
    Component(data, "Data bProcessing", "Processes fitness data.", "Module")
    Component(user, "User Management", "Manages user accounts.", "Module")
    Component(storage, "Data Storage", "Handles database Interactions.", "Module")

    Rel(api, data, "Uses")
    Rel(api, user, "Uses")
    Rel(api, storage, "Uses")

    


    

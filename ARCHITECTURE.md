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

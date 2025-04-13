Reflection: Designing the Domain Model and Class Diagram
Designing the domain model and class diagram for the real-time fitness tracker system was both a rewarding and challenging experience. It required a deep understanding of object-oriented design principles, alignment with previous assignments, and thoughtful decision-making around system structure.

1. Challenges Faced in Designing the Model
One of the first challenges was choosing the appropriate level of abstraction. In a real-time system like a fitness tracker, there are many moving parts: data from devices, user goals, notifications, real-time analytics, and more. Deciding which entities to model as full-fledged classes and which to treat as attributes required careful consideration. For example, we debated whether to model HeartRate and StepCount as separate entities or include them as attributes of FitnessData. We chose the latter to maintain simplicity without sacrificing functionality.

Another challenge was modeling relationships and multiplicity. For instance, a user might own multiple devices, each generating its own stream of data. Similarly, WorkoutSessions collect data from devices and contribute to Goal tracking. Modeling these one-to-many relationships accurately in Mermaid.js while maintaining clarity was a learning curve.

Defining methods (behaviors) for each class was another area of complexity. It was tempting to overload entities with too many operations. For example, in the User class, we initially considered including goal management methods, but later refactored those into the Goal class to follow the Single Responsibility Principle. This helped us keep the design more modular and scalable.

2. Alignment with Prior Work
The class diagram closely aligns with the functional requirements and use cases defined in Assignment 4 and 5. For example:

The WorkoutSession class maps directly to use cases like Start Session and End Session.

The Goal entity was informed by user stories around tracking fitness goals, such as As a user, I want to see my progress toward weekly step goals.

State transitions from Assignment 8 (e.g., session going from Not Started → Active → Completed) were directly translated into method logic in the WorkoutSession class.

By building on this previous work, the class diagram not only models the system's static structure but also supports its dynamic behavior, providing a consistent view of the system architecture.

3. Trade-offs Made
We made several design trade-offs to balance completeness and simplicity. For instance, we avoided introducing too many specialized subclasses (like Smartwatch and FitnessBand) under Device, instead using an attribute like deviceType. While inheritance could offer more granularity, it would have introduced unnecessary complexity at this stage of design.

Similarly, we opted to model the Notification system as a standalone class with a simple structure, rather than integrating complex messaging or event queues, which would be more appropriate at the implementation level.

These trade-offs helped us keep the diagram focused and maintainable, while still covering essential system behavior.

4. Lessons Learned
This assignment reinforced several important object-oriented design principles:

The importance of encapsulation: Keeping attributes private and defining clear methods helped us think about how data flows through the system.

Modularity and separation of concerns: Breaking down responsibilities into discrete classes makes the system easier to evolve and extend.

UML and visual modeling are powerful tools for ensuring all team members share the same mental model of the system.

It also became clear how essential domain modeling is in bridging the gap between stakeholder requirements and actual code. With a clear class diagram, developers have a solid foundation to start building features that align with business logic and user expectations.











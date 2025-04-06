```mermaid
stateDiagram
    [*] --> Registered
    Registered --> Verified : Email confirmed
    Verified --> Suspended : Policy violation
    Verified --> Deactivated : User deactivates
    Suspended --> Reactivated : Admin restores
    Deactivated --> [*]
    Reactivated --> Verified

```

```mermaid
stateDiagram
    [*] --> Scheduled
    Scheduled --> InProgress : Start
    InProgress --> Paused : Pause
    Paused --> InProgress : Resume
    InProgress --> Completed : Finish
    Completed --> [*]
```

```mermaid
stateDiagram
    [*] --> Set
    Set --> Active : Begin tracking
    Active --> Achieved : Goal met
    Active --> Abandoned : Cancelled
    Achieved --> [*]
    Abandoned --> [*]
```

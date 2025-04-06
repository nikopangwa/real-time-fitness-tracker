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


stateDiagram-v2
    [*] --> Registered : User signs up
    Registered --> Verified : Email confirmed
    Verified --> Suspended : Policy violation
    Verified --> Deactivated : User request
    Suspended --> Reactivated : Admin approval
    Deactivated --> [*]
    Reactivated --> Verified



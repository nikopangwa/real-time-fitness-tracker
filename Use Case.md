```mermaid
graph TD;
    %% Define Actors
    User["User"]
    Admin["Admin"]
    WearableDevice["Wearable Device"]
    HealthPlatform["External Health Platform"]
    SocialMedia["Social Media"]
    NutritionApp["Nutrition App"]

    %% Define Use Cases
    UC1["Connect Wearable Device"]
    UC2["Track Real-Time Activity"]
    UC3["Set Fitness Goals"]
    UC4["Receive Notifications"]
    UC5["View Historical Data"]
    UC6["Receive Workout Recommendations"]
    UC7["Share Achievements"]
    UC8["Participate in Challenges"]
    UC9["Sync with Health Platform"]
    UC10["Integrate Nutrition Data"]

    %% User interactions
    User -->|Connects| UC1
    User -->|Monitors| UC2
    User -->|Sets| UC3
    User -->|Receives| UC4
    User -->|Views| UC5
    User -->|Receives| UC6
    User -->|Shares| UC7
    User -->|Joins| UC8

    %% Admin interactions
    Admin -->|Manages| UC5
    Admin -->|Configures| UC6
    Admin -->|Oversees| UC8

    %% External System Interactions
    WearableDevice -->|Sends Data| UC1
    HealthPlatform -->|Syncs Data| UC9
    SocialMedia -->|Posts Updates| UC7
    NutritionApp -->|Shares Data| UC10




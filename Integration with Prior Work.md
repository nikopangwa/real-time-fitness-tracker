## 🔗 Integration with Prior Work

This section maps the **State Transition Diagrams** and **Activity Diagrams** created in Assignment 8 to functional requirements (from Assignment 4) and Agile user stories (from Assignment 6).

---

### 🧩 State Transition Diagram Mapping

| Object              | Functional Requirement(s)                    | Related User Story(ies)                                  |
|---------------------|----------------------------------------------|-----------------------------------------------------------|
| **User Account**     | FR-001: Register and manage account          | US-01: As a user, I want to create and manage my account. |
| **Workout Session**  | FR-003: Pause/resume workout                 | US-03: As a user, I want to pause and resume workouts.    |
| **Fitness Goal**     | FR-004: Set and track fitness goals          | US-04: As a user, I want to set personal fitness goals.   |
| **Subscription**     | FR-006: Manage subscriptions                 | US-06: As a user, I want to manage my subscription plan.  |
| **Payment**          | FR-007: Secure payment processing            | US-07: As a user, I want to make secure payments.         |
| **Progress Tracker** | FR-005: Record fitness progress              | US-05: As a user, I want to track my fitness progress.    |
| **Device Connection**| FR-008: Sync wearable devices                | US-08: As a user, I want to sync my wearable device.      |

---

### 🌀 Activity Diagram Mapping

| Workflow            | Functional Requirement(s)                    | Related User Story(ies)                                  |
|----------------------|----------------------------------------------|-----------------------------------------------------------|
| **User Registration** | FR-001: Account creation                    | US-01: User registration and verification                 |
| **Start Workout**     | FR-003: Manage workout sessions             | US-03: Start, pause, resume workouts                      |
| **Track Fitness Goal**| FR-004: Goal tracking                       | US-04: Monitor goal progress                              |
| **Manage Subscription**| FR-006: Subscription handling              | US-06: Modify subscription                                |
| **Process Payment**   | FR-007: Payment validation                  | US-07: Complete transactions                              |
| **Connect Wearable**  | FR-008: Device sync                         | US-08: Connect device and receive data                    |
| **Reset Progress**    | FR-005: Reset metrics                       | US-09: Reset fitness progress                             |
| **Generate Report**   | FR-009: Reporting capability                | US-10: Generate performance summary                       |

---

### 📁 README Linking (GitHub Integration)

To maintain clear documentation, link your diagrams and explanations in your GitHub `README.md`:

```markdown
## 📊 Diagrams and Modeling (Assignment 8)

- [📘 State Transition Diagrams](./diagrams/state_diagrams.md)
- [🌀 Activity Workflow Diagrams](./diagrams/activity_diagrams.md)
- [📖 Diagram Explanations](./diagrams/diagrams_explanation.md)
- [🔍 Integration with Prior Work](./integration_with_prior_work.md)
- [💡 Reflection](./assignment8_reflection.md)

These diagrams directly trace back to:
- [Functional Requirements (Assignment 4)](../Assignment4/requirements.md)
- [User Stories and Tasks (Assignment 6)](../Assignment6/user_stories.md)


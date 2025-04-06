State Transition Diagram Explanations

. User Account
This diagram shows the lifecycle of a user account, beginning from registration to verification and possible suspension or deactivation.
Key States: Registered, Verified, Suspended, Deactivated, Reactivated
Mapped Requirement: FR-001: Users must register, verify, and manage their account status.

2. Workout Session
Represents the typical flow of a workout session from being scheduled, started, paused, resumed, and completed.
Key States: Scheduled, InProgress, Paused, Completed
Mapped Requirement: FR-003: Allow users to manage workout session states like pause/resume.

3. Fitness Goal
Tracks the lifecycle of a fitness goal, including setting, activating, achieving, or abandoning it.
Key States: Set, Active, Achieved, Abandoned
Mapped Requirement: FR-004: Users can set and track fitness goals.

4. Subscription
Describes how a user’s subscription evolves over time, starting with a trial, becoming active, expiring, and renewing.
Key States: Trial, Active, Expired, Renewed
Mapped Requirement: FR-006: Users must be able to manage subscriptions.

5. Payment
Covers the payment flow from initiation to success or failure, with a retry option.
Key States: Pending, Completed, Failed
Mapped Requirement: FR-007: Payments must be processed and retried if needed.

6. Progress Tracker
Handles the internal status of tracked fitness data (e.g., weight or steps).
Key States: Untracked, Tracking, Completed, Reset
Mapped Requirement: FR-005: Track user metrics over time.

7. Device Connection
Shows how a wearable device connects to the system.
Key States: Disconnected, Connecting, Connected, Error
Mapped Requirement: FR-008: System must sync with wearable devices.

Activity Diagram Explanations

User Registration
This diagram maps the user onboarding process, including form submission, validation, and email confirmation.
Workflow Highlights: Decision for email confirmation; System handles account creation.
Stakeholder Need: Ensures secure onboarding for new users.

2. Start Workout
Shows how a user starts a session, from selecting an activity to beginning and pausing/resuming the session.
Workflow Highlights: Includes pause/resume as user actions.
Stakeholder Need: Supports flexible workout tracking.

3. Track Fitness Goal
Describes the steps to update and monitor a fitness goal based on progress data.
Workflow Highlights: Decision if goal is met; System updates status.
Stakeholder Need: Enables performance feedback.

4. Manage Subscription
Covers the subscription process from trial to activation and renewal.
Workflow Highlights: Decisions on payment; user/system roles in updates.
Stakeholder Need: Smooth access control for premium features.

5. Process Payment
Covers validation, processing, and response for user payments.
Workflow Highlights: Includes decision on payment success and retries.
Stakeholder Need: Ensures secure and user-friendly transactions.

6. Connect Wearable
Describes pairing a wearable device and syncing health data.
Workflow Highlights: Decision if pairing is successful; retries on failure.
Stakeholder Need: Ensures real-time tracking with user devices.

7. Reset Progress
Covers how users clear historical data and start fresh.
Workflow Highlights: Decision point for confirmation.
Stakeholder Need: Flexibility to reset and realign fitness goals.

8. Generate Report
Outlines how a user can generate a summary of workouts and metrics.
Workflow Highlights: Parallel actions—generate PDF and update dashboard.
Stakeholder Need: Accessible insights on performance.



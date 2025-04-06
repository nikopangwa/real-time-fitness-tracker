 Reflection

 Challenges Faced

 Choosing the Right Level of Detail
One of the key challenges was deciding how granular the states and actions should be. Too much detail made the diagrams cluttered, while too little omitted essential behaviors. For example, in the **Workout Session** state diagram, I initially added every possible UI interaction, which overwhelmed the diagram. I refined it to only key state transitions (e.g., "Paused", "In Progress", "Completed"), improving clarity.

 Aligning Diagrams with Agile Artifacts
Another challenge was maintaining consistency with the user stories and sprint tasks defined in Assignment 6. I had to regularly trace each diagram element back to a requirement or user story to ensure alignment. This required cross-referencing multiple files and occasionally adjusting transitions to better reflect actual user flows.

 Visualizing Concurrent Actions
For the activity diagrams, showing parallel processes like **"Send Confirmation Email"** and **"Update Inventory"** (in workflows like user registration or workout start) was tricky. Using swimlanes helped clarify which actor (User vs. System) performed each action and allowed for better visualization of concurrency.

---

Lessons Learned

Creating these diagrams helped me better understand the dynamic behavior of the system. I saw how **state diagrams model object behavior over time**, while **activity diagrams focus on process flows and actor responsibilities**. This distinction helped me think more clearly about system design and architecture.

---

Comparison: State vs. Activity Diagrams

| Aspect                    | State Transition Diagrams                        | Activity Diagrams                                      |
|---------------------------|--------------------------------------------------|--------------------------------------------------------|
| Focus                    | Object behavior over time                        | Workflow or process logic                              |
| Best For                 | Modeling lifecycle of entities (e.g., user, goal) | Mapping full user/system processes (e.g., registration) |
| Actors Involved          | Usually system objects                           | Clearly separates roles with swimlanes                 |
| Visualization Style      | States + transitions                            | Actions, decisions, flows, and concurrency             |

---

Agile Alignment

These diagrams reinforced core Agile principles:
- **Continuous delivery**: Defined clear transitions that enable seamless updates (e.g., switching between workout states).
- **Collaboration**: The visual representation made it easier to share design with teammates for feedback.
- **Adaptability**: If requirements change, updating diagrams is relatively quick and helps realign the team instantly.

---


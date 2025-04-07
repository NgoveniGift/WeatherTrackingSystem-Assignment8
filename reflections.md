Reflection

Choosing Granularity for States/Actions
One of the main challenges was finding the right level of granularity in the activity diagrams. Too much detail made the diagrams cluttered and hard to read, while too little risked omitting key workflows that stakeholders care about. For instance, in the Location workflow, we initially broke down every sub-action like "validate coordinates" or "format region string", but this overwhelmed the diagram. Eventually, we grouped these into higher-level actions like Validate Location to improve readability without losing meaning.

 Aligning Diagrams with Agile User Stories
Another challenge was aligning the activity diagrams with our Agile user stories and sprint tasks from Assignment 6. Agile often emphasizes outcomes over processes, while activity diagrams require modeling every step explicitly. We had to re-interpret stories like "As a user, I want to see weather for my current location" into step-by-step activities (e.g., Get User Location → Request Weather → Display Output). This helped clarify implementation details but required back-and-forth between diagrams and sprint planning.

State Diagrams vs. Activity Diagrams
State diagrams model the behavior of a single object across time, showing how it transitions based on internal or external triggers. For example, the User Session state diagram shows how a session moves from Idle to Active to Terminated.

In contrast, activity diagrams capture the workflow of a process, not just one object. They're great for visualizing how different system components interact during an event — like the full process of fetching and displaying weather data, involving user input, location services, and weather APIs.

Both are valuable:

Use state diagrams when focusing on object lifecycles.
Use activity diagrams for end-to-end process modeling across components.



# WeatherTrackingSystem-Assignment8

# 🌤️ Weather Tracking System

This repository contains the design and modeling for the Weather Tracking System built in Rust. This includes:

- 📌 Object State Diagrams
- 🧭 Activity Workflow Diagrams
- 📚 Functional Requirement Traceability
- 🏃 Agile Sprint/User Story Alignment
- 🧠 Developer Reflection

---

## 📁 Directory Structure


---

## 🧭 Activity Diagrams

### 1. Fetch Weather Activity

```mermaid
flowchart TD
    A[User initiates request] --> B[App checks cache]
    B -- Cache hit --> C[Return cached weather]
    B -- Cache miss --> D[Fetch user location]
    D --> E[Call weather API]
    E --> F[Parse and validate response]
    F --> G[Store in cache]
    G --> H[Display weather to user]

Explanation:
This diagram represents the main workflow for fetching weather data. It ensures performance by checking the cache first, then falls back to API calls. This meets the efficiency and scalability concerns of stakeholders by optimizing network calls and data reuse.

2.  Get User Location Activity

flowchart TD
    A[Request location permission] --> B[Check device location settings]
    B --> C[Get GPS coordinates]
    C --> D[Validate coordinates]
    D --> E[Return valid location or error]

Explanation:
Parallel actions and error handling are shown clearly. Ensures user privacy and error management, which are critical stakeholder concerns, especially regarding device-level permissions and fallback behavior.

3. Alert Generation Activity

flowchart TD
    A[Monitor incoming weather data] --> B[Check for severe conditions]
    B -->|No| C[No alert triggered]
    B -->|Yes| D[Generate alert message]
    D --> E[Send push/email alert]
    E --> F[Log alert in database]

Explanation:
This diagram shows real-time responsiveness. Stakeholders are concerned with user safety, so ensuring immediate notification of extreme weather is key.

State Diagrams
Weather Object State Diagram

stateDiagram-v2
    [*] --> Unfetched
    Unfetched --> Fetching
    Fetching --> Cached : API Success
    Fetching --> Error : API Fail
    Cached --> Refreshing
    Refreshing --> Cached : Update Success
    Error --> Fetching : Retry
Explanation:
This state diagram maps the lifecycle of weather data. It highlights states like Unfetched, Cached, and Error, supporting robust error recovery and freshness — key stakeholder needs for data accuracy.

 Traceability to Prior Work

# Assignment 4: Functional Requirements

| Diagram                     | Functional Requirement                        |
|----------------------------|-----------------------------------------------|
| Fetch Weather Activity     | **FR1**: Display current weather data         |
| User Location Activity     | **FR2**: Use device location for weather      |
| Alert Generation Activity  | **FR3**: Notify user of severe weather        |
| Weather State Diagram      | **FR4**: Cache and refresh weather data       |


# Assignment 6: User Stories & Sprint Tasks

| Diagram                    | User Story                                              | Sprint Task                |
|---------------------------|----------------------------------------------------------|----------------------------|
| Fetch Weather Activity    | **US1**: As a user, I want to view updated weather info  | Implement fetch & cache logic |
| User Location Activity    | **US2**: As a user, I want weather based on my location  | GPS and permissions         |
| Alert Generation Activity | **US3**: As a user, I want alerts during severe weather  | Set up alert engine         |
| Weather State Diagram     | **US4**: As a dev, I want weather states to be consistent| Handle cache lifecycle      |

Reflection

Choosing Granularity
Finding the right level of detail was difficult. Overly detailed diagrams were hard to read, while vague ones missed critical logic. The balance was struck by grouping technical steps like "validate response" into higher-level actions like Parse and Display.

Aligning with Agile Stories
Agile user stories focus on outcomes, but activity diagrams require step-by-step logic. This meant breaking down "get weather" into actions like permission requests, API calls, caching, etc. This clarified the implementation path but was time-consuming to trace back.

State vs. Activity Diagrams
State diagrams (like for weather objects) are excellent for modeling internal transitions of a single object.

Activity diagrams show system-wide flows and inter-component interaction.

Both were essential — one for understanding what changes, the other for how things flow.


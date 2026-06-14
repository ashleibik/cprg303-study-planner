ADR 2 — Hardware (Local Notifications)



Status



Accepted



Context



Schedinuity is a study planner application that allows students to create tasks and reminders. Users need to receive notifications about upcoming assignments, exams, and deadlines even when the application is closed. The team needed to choose a hardware-related feature that supports the application's reminder functionality while remaining within the project scope.



Decision



Use local notifications provided by the mobile device operating system. Notifications will be scheduled when users create reminders and will be delivered at the specified time, even when the application is not actively running.



Consequences



Easier:



\* Supports the core reminder functionality of the application.

\* Works without requiring a backend server.

\* Functions even when the application is closed.

\* Fits within the project scope and timeline.

\* Improves user productivity and organization.



More difficult:



\* Requires users to grant notification permissions.

\* Notification behavior may vary slightly between Android and iOS devices.

\* Notifications are limited to the local device.



Alternatives Considered



Remote Push Notifications



Rejected because a backend server would increase complexity and development time.



No Notification System



Rejected because reminders are a core feature of the application.




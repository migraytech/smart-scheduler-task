# smart-scheduler-task
Een moderne applicatie waar gebruikers hun taken kunnen plannen, reminders krijgen en slimme suggesties ontvangen op basis van eerdere activiteiten.

                    ┌──────────────────────────────┐
                    │          Frontend             │
                    └──────────────┬────────────────┘
                                   │
                                   ▼
                         ┌────────────────┐
                         │  API Gateway   │  ← Spring Cloud Gateway
                         └───────┬────────┘
        ┌────────────────────────┼──────────────────────────┐
        │                        │                          │
        ▼                        ▼                          ▼
┌──────────────┐       ┌────────────────┐        ┌────────────────────┐
│ Task Service │       │ User Service   │        │ Notification Svc   │
└──────┬───────┘       └───────┬────────┘        └────────┬──────────┘
       │                       │                         │
       ▼                       ▼                         ▼
   Task Repo              User Repo               Activity / Log Repo
       │                       │                         │
       └─────────────── Shared Database or separate DBs ─┘

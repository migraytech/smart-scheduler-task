# smart-scheduler-task
Een moderne applicatie waar gebruikers hun taken kunnen plannen, reminders krijgen en slimme suggesties ontvangen op basis van eerdere activiteiten.


# flowchart TB

    FE[Frontend]

    FE --> GW[API Gateway<br/>(Spring Cloud Gateway)]

    GW --> TS[Task Service]
    GW --> US[User Service]
    GW --> NS[Notification Service]

    TS --> TR[(Task Repo)]
    US --> UR[(User Repo)]
    NS --> NR[(Activity / Log Repo)]

    TR --- DB[(Shared Database<br/>of Separate DBs)]
    UR --- DB
    NR --- DB


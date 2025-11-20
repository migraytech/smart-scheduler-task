# smart-scheduler-task
Een moderne applicatie waar gebruikers hun taken kunnen plannen, reminders krijgen en slimme suggesties ontvangen op basis van eerdere activiteiten.


#flowchart TB
    FE[Frontend<br/>(React / Angular / Thymeleaf)]
    FE --> GW[API Gateway<br/>(Spring Cloud Gateway)]

    %% Microservices
    GW --> TS[Task Service<br/>(Spring Boot)]
    GW --> US[User Service<br/>(Spring Boot)]
    GW --> NS[Notification Service<br/>(Spring Boot)]

    %% Repositories
    TS --> TR[(Task Repository<br/>PostgreSQL / MySQL)]
    US --> UR[(User Repository<br/>PostgreSQL / MySQL)]
    NS --> NR[(Activity / Log Repository<br/>PostgreSQL / MySQL)]

    TR --- DB[(Shared DB / Separate DBs)]
    UR --- DB
    NR --- DB

    %% Message Broker
    MB[(Message Broker<br/>Kafka / RabbitMQ)]
    TS --> MB
    US --> MB
    NS --> MB
    MB --> TS
    MB --> US
    MB --> NS

    %% Optional: Async events
    TS -.-> NS[Notification Service triggers events]



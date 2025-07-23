# Распределенный трекер задач
Распределенный трекер задач (аналог Jira)
```mermaid  
graph TD;
    A[API Gateway]-->B[Auth Service];
    A[API Gateway]-->C[Task Service];
    A[API Gateway]-->D[Notification Service];
    B[Auth Service]-->E[Keycloak];
    C[Task Service]-->F[PostgreSQL];
    C[Task Service]-->G[Kafka];
    D[Notification Service]-->H[Redis];
    C[Task Service]-->I[Analytics Service];
    I[Analytics Service]-->J[Elasticsearch];
``` 

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

Что делает:

Микросервисная архитектура (Spring Boot + Spring Cloud)

Управление задачами с тегами и дедлайнами

Уведомления в реальном времени через WebSocket

Аналитика продуктивности

Технологии:

Spring Boot 3 (Web, Data JPA, Security)

Apache Kafka для межсервисного взаимодействия

PostgreSQL + Redis для кэширования

Keycloak для OAuth2-аутентификации

Docker + Kubernetes

Prometheus + Grafana для мониторинга

Фишки:

Реализация Saga-паттерна для транзакций

Нагрузочное тестирование с Gatling

Генерация PDF-отчетов с Apache PDFBox

Интеграция с Google Calendar API

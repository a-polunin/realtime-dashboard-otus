# Схема слоя входа: клиент → шлюз → сервисы

```mermaid
flowchart TB
    WEB[Веб-дашборд<br/>SPA]:::ext
    RN[Мобильное приложение<br/>React Native]:::ext
    B2B[Партнёрская интеграция<br/>B2B API]:::ext

    subgraph GW[API Gateway]
        direction TB
        EDGE[TLS, роутинг, /v1<br/>trace id, аномальный трафик]
        AUTH[Аутентификация,<br/>rate limiting, квоты по тарифу]:::gen
        WSU[WS/SSE upgrade,<br/>распределение соединений]
        CACHE[(короткий кэш<br/>снапшота)]:::db
        EDGE --> AUTH --> WSU
        AUTH --- CACHE
    end

    subgraph S[Dashboard сервис]
        direction TB
        DELIV[Доставка клиентам<br/>подписки, досыл с версии]
        STATE[Состояние матча<br/>согласованные версии]
        LOG[Хранилище событий матча]
        CALC[Пересчёт метрик]
        ARB[Выбор и валидация источников]
        INT[Интеграция с провайдерами]

        INT --> ARB --> LOG
        LOG --> CALC --> STATE
        LOG --> STATE
        STATE -->|новая версия| DELIV
    end

    P[Провайдеры данных]:::ext --> INT

    WEB -->|"HTTPS: снапшот, история<br/>WS: поток версий"| EDGE
    RN -->|"HTTPS + WS,<br/>тот же контракт"| EDGE
    B2B -->|"HTTPS: пулл матчей,<br/>история после матча"| EDGE

    WSU -->|подписка на матч| DELIV
    AUTH -->|снапшот / история| STATE
    DELIV -->|поток версий| WEB
    DELIV --> RN

    classDef ext fill:#c8f0c8,stroke:#333
    classDef db fill:#fff2b8,stroke:#333
    classDef gen fill:#dcd6f7,stroke:#333
```

### Что здесь видно

Вход один на все три клиента, BFF-прослойки между шлюзом и сервисами нет: шлюз отдаёт запрос ровно одному сервису, а не собирает ответ из нескольких. Realtime и обычные запросы расходятся уже за шлюзом - поток версий идёт через доставку клиентам, снапшот и история берутся у состояния матча

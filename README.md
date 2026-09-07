# realtime-dashboard-otus

Учебный pet-проект в рамках курса OTUS по архитектуре ПО.

## О проекте

Прорабатывается архитектура сервиса, который в реальном времени показывает
футбольную аналитику (счёт, события матча, xG, владение мячом и т.д.),
получая данные от нескольких провайдеров и раздавая их клиентам через
WebSocket/SSE.

Сам сервис — учебный, код не является целью проекта. Цель — потренироваться
в проектировании архитектуры.

## Структура репозитория

- [`docs/01-quality-attributes.md`](docs/01-quality-attributes.md) — драйверы и атрибуты качества (ISO 25010)
- [`docs/02-utility-tree.md`](docs/02-utility-tree.md) — дерево полезности и сценарии (S1–S5)
- [`docs/03-trade-off.md`](docs/03-trade-off.md) — анализ ключевого архитектурного trade-off'а
- [`docs/04-capabilities.md`](docs/04-capabilities.md) — возможности и типы поддоменов (core/supporting/generic)
- [`docs/05-service-boundaries.md`](docs/05-service-boundaries.md) — границы сервисов: ответственность и владение данными
- [`docs/06-cohesion-coupling.md`](docs/06-cohesion-coupling.md) — проверка cohesion/coupling и риск связанности
- [`docs/07-services-diagram.md`](docs/07-services-diagram.md) — диаграмма сервисов и пример DIP
- [`docs/08-event-storming.md`](docs/08-event-storming.md) — Event Storming, Bounded Context, Context Map и сверка с границами сервисов
- [`docs/09-rendering-model.md`](docs/09-rendering-model.md) — модель рендеринга фронтенда, code splitting и эффект на LCP/TTFB
- [`docs/10-cicd.md`](docs/10-cicd.md) — CI/CD пайплайн фронтенда
- [`docs/11-frontend-architecture.md`](docs/11-frontend-architecture.md) — архитектура фронтенд-кода (почему не FSD)
- [`docs/12-risk-matrix.md`](docs/12-risk-matrix.md) — матрица рисков
- [`docs/13-slo-sli.md`](docs/13-slo-sli.md) — SLO/SLI по узлам системы
- [`docs/14-degradation-map.md`](docs/14-degradation-map.md) — карта деградации (веб + React Native)
- [`docs/15-clients-and-scenarios.md`](docs/15-clients-and-scenarios.md) — клиенты системы (веб, React Native, партнёрский API) и их сценарии
- [`docs/16-entry-layer.md`](docs/16-entry-layer.md) — слой входа: нужен ли BFF и что выносим на шлюз
- [`docs/17-caching/`](docs/17-caching/) — кэширование: данные и точки, стратегии инвалидации, вопросы к бэкенду
- [`docs/18-sync-async.md`](docs/18-sync-async.md) — синхронный и асинхронный API: sync/async по сценариям, оркестрация vs хореография, контракты
- [`docs/19-idempotency.md`](docs/19-idempotency.md) — идемпотентность и коммутативность: ключи идемпотентности и дедупликация повторов
- [`docs/20-auth-model.md`](docs/20-auth-model.md) — аутентификация и авторизация: роли, вход и точка проверки токена, RBAC+ABAC, проверка принадлежности объекта
- [`docs/adr/`](docs/adr/) — Architecture Decision Records
- [`docs/views/`](docs/views/) — C4-диаграммы (Context, Container), схема слоя входа и исходники в Excalidraw

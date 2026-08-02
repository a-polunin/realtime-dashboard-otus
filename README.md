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
- [`docs/adr/`](docs/adr/) — Architecture Decision Records
- [`docs/views/`](docs/views/) — C4-диаграммы (Context, Container) и исходники в Excalidraw

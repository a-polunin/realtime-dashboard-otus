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
- [`docs/adr/`](docs/adr/) — Architecture Decision Records
- [`docs/views/`](docs/views/) — C4-диаграммы (Context, Container) и исходники в Excalidraw

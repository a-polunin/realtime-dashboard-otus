# CI/CD фронтенда

**Пайплайн:** lint+typecheck → unit-тесты → build (Vite/webpack) → deploy на ephemeral-окружение по PR → e2e на нём → deploy на staging при мерже в main → manual approve → deploy на prod.

**Окружения:** dev (локально), ephemeral per-PR (превью для ревью и e2e, живёт до мерджа), staging, prod.

**SSR:** его нет — решение зафиксировано в [09-rendering-model.md](09-rendering-model.md), у нас чистый CSR.

**CDN:** да, бандл после build льётся на CDN (в staging и prod), это и даёт минимальный TTFB, о котором говорили в модели рендеринга.

**Масштабирование:** для фронтенда оно, по сути, не нужно — статика на CDN уже горизонтально размножена edge-нодами провайдера, никаких инстансов приложения не поднимаем и не скейлим.

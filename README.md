# Project Docs

## Назначение

Этот репозиторий хранит проектную документацию и правила работы с ней.

`README.md` - короткая входная точка для нового читателя. Детальные факты, решения, требования и процессы должны жить в профильных документах из структуры ниже.

## Быстрый старт

1. Откройте [`00-context/DOCS.md`](00-context/DOCS.md) - карту всей документации и правила владения фактами.
2. Прочитайте [`01-product/strategy/PROJECT.md`](01-product/strategy/PROJECT.md) - суть проекта, цели, границы и владельцы.
3. Проверьте [`01-product/strategy/STATE.md`](01-product/strategy/STATE.md) - текущее состояние, последние решения и открытые вопросы.
4. Посмотрите [`01-product/strategy/ROADMAP.md`](01-product/strategy/ROADMAP.md) - спринты, вехи и приоритеты.
5. Посмотрите [`01-product/planning/BACKLOG.md`](01-product/planning/BACKLOG.md) - очередь задач вне текущего спринта.
6. Посмотрите [`01-product/planning/PLAN.md`](01-product/planning/PLAN.md) - текущий спринт.
7. Для участия в работе прочитайте [`02-team/people/ONBOARDING.md`](02-team/people/ONBOARDING.md).

## Структура

```text
00-context/      Карта документации и правила source of truth
01-product/      Продукт: strategy, planning, requirements, growth, knowledge
02-team/         Команда: people, process, agents, templates
03-engineering/  Инженерия: architecture, stack
04-quality/      Соглашения, тестирование и баги
05-operations/   Окружения, деплой, безопасность и поддержка
06-history/      История изменений
```

## Главное правило

Один факт должен иметь один основной документ-владелец.

Если информация уже относится к существующему документу, нужно обновить этот документ, а не создавать новый файл. `README.md` не заменяет профильные документы и не должен дублировать их содержимое.

## Рабочая модель

Документация поддерживает CEO-first процесс:

```text
User -> CEO Agent -> план для Product Owner -> командный план для sprint/task -> назначенная роль -> review -> обновленный source of truth -> результат пользователю
```

Маршрутизация задач описана в [`02-team/process/TASK_ROUTING.md`](02-team/process/TASK_ROUTING.md), процесс работы - в [`02-team/process/WORKFLOW.md`](02-team/process/WORKFLOW.md), правила ревью - в [`02-team/process/REVIEW_POLICY.md`](02-team/process/REVIEW_POLICY.md). Формат планирования через CEO описан в [`02-team/agents/CEO_AGENT.md`](02-team/agents/CEO_AGENT.md).

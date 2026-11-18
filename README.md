# Project Docs

## Назначение

Этот репозиторий хранит проектную документацию и правила работы с ней.

`README.md` - короткая входная точка для нового читателя. Детальные факты, решения, требования и процессы должны жить в профильных документах из структуры ниже.

## Быстрый старт

1. Откройте [`00-context/DOCS.md`](00-context/DOCS.md) - карту всей документации и правила владения фактами.
2. Прочитайте [`01-product/strategy/PROJECT.md`](01-product/strategy/PROJECT.md) - суть проекта, цели, границы и владельцы.
3. Выберите [профиль проекта](07-project-types/README.md) и зафиксируйте его в `PROJECT.md`: для игры — [17 этапов с проверкой пользователя после каждого](07-project-types/games/GAME_LIFECYCLE.md); для сервиса — существующий регламент из 18 этапов. Отдельные профили веб- и других проектов будут добавлены позднее.
4. Проверьте [`01-product/strategy/STATE.md`](01-product/strategy/STATE.md) - этапы выбранного процесса, разрешённые действия, решения пользователя и открытые вопросы.
5. Посмотрите [`01-product/strategy/ROADMAP.md`](01-product/strategy/ROADMAP.md) - спринты, вехи и приоритеты.
6. Посмотрите [`01-product/planning/BACKLOG.md`](01-product/planning/BACKLOG.md) - очередь задач вне текущего спринта.
7. Посмотрите [`01-product/planning/PLAN.md`](01-product/planning/PLAN.md) - текущий спринт.
8. Проверьте [`02-team/process/SPRINT_REGULATION.md`](02-team/process/SPRINT_REGULATION.md) - проектные правила шести обязательных этапов спринта.
9. Для участия в работе прочитайте [`02-team/people/ONBOARDING.md`](02-team/people/ONBOARDING.md).

## Структура

```text
00-context/      Карта документации и правила source of truth
01-product/      Продукт: strategy, planning, requirements, growth, knowledge
02-team/         Команда: people, process, agents, templates
03-engineering/  Инженерия: architecture, stack
04-quality/      Соглашения, тестирование и баги
05-operations/   Окружения, команды, скрипты, деплой, безопасность и поддержка
06-history/      История изменений
07-project-types/ Профили: игры; будущие веб- и другие проекты
```

## Игровые проекты

[Игровой профиль](07-project-types/games/README.md) содержит полный регламент, шаблон единой цели, дизайн игры, форму проверки, реестр этапов и учебный пример. Он применяется **только к играм**. Прежний комплект по трём этапам сохранён в его архиве. Для подключения используйте [PROJECT_SETUP.md](07-project-types/games/PROJECT_SETUP.md).

## Главное правило

Один факт должен иметь один основной документ-владелец.

Если информация уже относится к существующему документу, нужно обновить этот документ, а не создавать новый файл. `README.md` не заменяет профильные документы и не должен дублировать их содержимое.

Исключение: команды можно дублировать в профильных документах для удобства, если они совпадают с [`05-operations/COMMANDS.md`](05-operations/COMMANDS.md).

## Рабочая модель

Документация поддерживает CEO-first процесс:

```text
User -> CEO Agent -> план для Product Owner -> командный план для sprint/task -> назначенная роль -> review -> обновленный source of truth -> результат пользователю
```

Жизненный цикл выбирается по [типу проекта](07-project-types/README.md). Приёмка этапа игры пользователем обязательна и не заменяется решением CEO Agent или завершением спринта. Маршрутизация задач - в [`02-team/process/TASK_ROUTING.md`](02-team/process/TASK_ROUTING.md), процесс работы - в [`02-team/process/WORKFLOW.md`](02-team/process/WORKFLOW.md), цикл спринта - в [`02-team/process/SPRINT_REGULATION.md`](02-team/process/SPRINT_REGULATION.md), правила ревью - в [`02-team/process/REVIEW_POLICY.md`](02-team/process/REVIEW_POLICY.md). Формат планирования через CEO описан в [`02-team/agents/CEO_AGENT.md`](02-team/agents/CEO_AGENT.md).

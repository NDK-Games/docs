# DOCS

## Назначение

Этот документ - карта всей проектной документации.

Он нужен, чтобы любой участник проекта быстро понял:

- какие документы существуют;
- где хранить разные типы информации;
- какой документ является source of truth;
- как управлять проектом через CEO-first цепочку;
- когда создавать ветки, задачи, ревью и handoff;
- какие документы не нужно дублировать.

## Главное правило

Один факт должен иметь один основной документ-владелец.

Если информация уже относится к существующему документу, нужно обновить этот документ, а не создавать новый файл. Новый документ создается только тогда, когда у него есть отдельный читатель, владелец и зона ответственности.

## Управленческий принцип

Вся работа идет сверху вниз через CEO Agent.

Пользователь не заполняет документы руками. Пользователь сообщает намерение, проблему, ограничение или решение. CEO Agent сам:

- оформляет входящий запрос;
- определяет приоритет и тип работы;
- назначает Product Manager, CTO, Tech Lead или другую роль;
- поручает нижестоящей роли заполнить нужный шаблон;
- контролирует review, QA, документацию и итоговый статус;
- возвращает пользователю готовое решение, результат или короткий блокирующий вопрос.

Цепочка по умолчанию:

```text
User
└─ CEO Agent
   ├─ Product Manager Agent
   ├─ CTO Agent
   └─ Tech Lead Agent
      ├─ Developer Feature Agent
      ├─ Developer Bug Fix Agent
      ├─ Developer Test Writer Agent
      ├─ Developer Code Reviewer Agent
      ├─ QA Agent
      ├─ Security Agent
      ├─ DevOps Agent
      └─ Documentation Agent
```

## Каноническая структура

```text
docs/
├─ README.md
├─ 00-context/
│  └─ DOCS.md
├─ 01-product/
│  ├─ strategy/
│  │  ├─ PROJECT.md
│  │  ├─ ROADMAP.md
│  │  └─ STATE.md
│  ├─ planning/
│  │  ├─ BACKLOG.md
│  │  └─ PLAN.md
│  ├─ requirements/
│  │  ├─ REQUIREMENTS.md
│  │  └─ USER_FLOWS.md
│  ├─ growth/
│  │  ├─ MONETIZATION.md
│  │  └─ ANALYTICS.md
│  └─ knowledge/
│     └─ WIKI.md
├─ 02-team/
│  ├─ people/
│  │  ├─ TEAM.md
│  │  ├─ ROLES.md
│  │  └─ ONBOARDING.md
│  ├─ process/
│  │  ├─ WORKFLOW.md
│  │  ├─ TASK_ROUTING.md
│  │  ├─ BRANCHING.md
│  │  └─ REVIEW_POLICY.md
│  ├─ agents/
│  └─ templates/
├─ 03-engineering/
│  ├─ architecture/
│  │  ├─ ARCHITECTURE.md
│  │  ├─ DATA_MODEL.md
│  │  ├─ API.md
│  │  ├─ INTEGRATIONS.md
│  │  └─ adr/
│  └─ stack/
│     ├─ STACK.md
│     └─ CONCERNS.md
├─ 04-quality/
│  ├─ CONVENTIONS.md
│  ├─ TESTING.md
│  └─ BUGS.md
├─ 05-operations/
│  ├─ ENVIRONMENT.md
│  ├─ DEPLOYMENT.md
│  ├─ RELEASE_CHECKLIST.md
│  ├─ OBSERVABILITY.md
│  ├─ SECURITY.md
│  └─ TROUBLESHOOTING.md
├─ 06-history/
│  └─ CHANGELOG.md
└─ 99-archive/
   └─ project-specific/
```

## Порядок чтения

Для нового участника:

1. [`README.md`](../README.md)
2. [`01-product/strategy/PROJECT.md`](../01-product/strategy/PROJECT.md)
3. [`01-product/requirements/REQUIREMENTS.md`](../01-product/requirements/REQUIREMENTS.md)
4. [`01-product/requirements/USER_FLOWS.md`](../01-product/requirements/USER_FLOWS.md)
5. [`01-product/strategy/STATE.md`](../01-product/strategy/STATE.md)
6. [`01-product/strategy/ROADMAP.md`](../01-product/strategy/ROADMAP.md)
7. [`01-product/planning/BACKLOG.md`](../01-product/planning/BACKLOG.md)
8. [`01-product/planning/PLAN.md`](../01-product/planning/PLAN.md)
9. [`02-team/people/ONBOARDING.md`](../02-team/people/ONBOARDING.md)
10. [`02-team/people/TEAM.md`](../02-team/people/TEAM.md)
11. [`02-team/people/ROLES.md`](../02-team/people/ROLES.md)
12. Релевантные документы из `03-engineering/`, `04-quality/` и `05-operations/`

Для текущей работы в CEO-first режиме:

1. User сообщает CEO Agent цель, проблему или решение.
2. CEO Agent проверяет [`01-product/strategy/PROJECT.md`](../01-product/strategy/PROJECT.md), [`01-product/strategy/ROADMAP.md`](../01-product/strategy/ROADMAP.md), [`01-product/planning/BACKLOG.md`](../01-product/planning/BACKLOG.md), [`01-product/strategy/STATE.md`](../01-product/strategy/STATE.md) и [`01-product/planning/PLAN.md`](../01-product/planning/PLAN.md).
3. CEO Agent выбирает маршрут в [`02-team/process/TASK_ROUTING.md`](../02-team/process/TASK_ROUTING.md).
4. Назначенная роль заполняет нужный шаблон или обновляет документ-владелец.
5. Tech Lead Agent решает, нужна ли ветка по [`02-team/process/BRANCHING.md`](../02-team/process/BRANCHING.md).
6. После выполнения включается [`02-team/process/REVIEW_POLICY.md`](../02-team/process/REVIEW_POLICY.md) и нужные quality checks.
7. Documentation Agent обновляет source of truth.
8. CEO Agent принимает итог и сообщает пользователю результат.

## Source of Truth

| Тип информации | Где хранить |
| --- | --- |
| Короткая входная точка и навигация по репозиторию | [`README.md`](../README.md) |
| Суть проекта, цели, границы | [`01-product/strategy/PROJECT.md`](../01-product/strategy/PROJECT.md) |
| Стабильные знания, FAQ, глоссарий | [`01-product/knowledge/WIKI.md`](../01-product/knowledge/WIKI.md) |
| Требования и acceptance criteria | [`01-product/requirements/REQUIREMENTS.md`](../01-product/requirements/REQUIREMENTS.md) |
| Пользовательские сценарии, точки входа, ветки поведения | [`01-product/requirements/USER_FLOWS.md`](../01-product/requirements/USER_FLOWS.md) |
| Монетизация, реклама, покупки, подписки | [`01-product/growth/MONETIZATION.md`](../01-product/growth/MONETIZATION.md) |
| Аналитика, события, конверсии, воронки | [`01-product/growth/ANALYTICS.md`](../01-product/growth/ANALYTICS.md) |
| Крупные этапы, спринты и приоритеты | [`01-product/strategy/ROADMAP.md`](../01-product/strategy/ROADMAP.md) |
| Очередь задач вне текущего спринта | [`01-product/planning/BACKLOG.md`](../01-product/planning/BACKLOG.md) |
| Текущий спринт и рабочий план | [`01-product/planning/PLAN.md`](../01-product/planning/PLAN.md) |
| Текущее состояние, последние решения, открытые вопросы | [`01-product/strategy/STATE.md`](../01-product/strategy/STATE.md) |
| Участники и режим работы | [`02-team/people/TEAM.md`](../02-team/people/TEAM.md) |
| Роли и зоны ответственности | [`02-team/people/ROLES.md`](../02-team/people/ROLES.md) |
| Маршрутизация задач | [`02-team/process/TASK_ROUTING.md`](../02-team/process/TASK_ROUTING.md) |
| Процесс работы команды, циклы, правила задач | [`02-team/process/WORKFLOW.md`](../02-team/process/WORKFLOW.md) |
| Быстрый ввод нового человека в проект | [`02-team/people/ONBOARDING.md`](../02-team/people/ONBOARDING.md) |
| Ветки | [`02-team/process/BRANCHING.md`](../02-team/process/BRANCHING.md) |
| Ревью | [`02-team/process/REVIEW_POLICY.md`](../02-team/process/REVIEW_POLICY.md) |
| Стек | [`03-engineering/stack/STACK.md`](../03-engineering/stack/STACK.md) |
| Архитектура | [`03-engineering/architecture/ARCHITECTURE.md`](../03-engineering/architecture/ARCHITECTURE.md) |
| Данные | [`03-engineering/architecture/DATA_MODEL.md`](../03-engineering/architecture/DATA_MODEL.md) |
| API и интерфейсы | [`03-engineering/architecture/API.md`](../03-engineering/architecture/API.md) |
| Интеграции | [`03-engineering/architecture/INTEGRATIONS.md`](../03-engineering/architecture/INTEGRATIONS.md) |
| Технические риски и долг | [`03-engineering/stack/CONCERNS.md`](../03-engineering/stack/CONCERNS.md) |
| Соглашения | [`04-quality/CONVENTIONS.md`](../04-quality/CONVENTIONS.md) |
| Тестирование | [`04-quality/TESTING.md`](../04-quality/TESTING.md) |
| Баги | [`04-quality/BUGS.md`](../04-quality/BUGS.md) |
| Окружения и конфигурация | [`05-operations/ENVIRONMENT.md`](../05-operations/ENVIRONMENT.md) |
| Деплой и rollback | [`05-operations/DEPLOYMENT.md`](../05-operations/DEPLOYMENT.md) |
| Релизная проверка | [`05-operations/RELEASE_CHECKLIST.md`](../05-operations/RELEASE_CHECKLIST.md) |
| Метрики, логи, алерты | [`05-operations/OBSERVABILITY.md`](../05-operations/OBSERVABILITY.md) |
| Безопасность и доступы | [`05-operations/SECURITY.md`](../05-operations/SECURITY.md) |
| Диагностика проблем | [`05-operations/TROUBLESHOOTING.md`](../05-operations/TROUBLESHOOTING.md) |
| История релизов | [`06-history/CHANGELOG.md`](../06-history/CHANGELOG.md) |

## README.md

[`README.md`](../README.md) - корневая входная точка в репозиторий документации.

README должен:

- кратко объяснять назначение репозитория;
- направлять нового читателя к [`00-context/DOCS.md`](DOCS.md) и ключевым документам;
- показывать верхнеуровневую структуру каталогов;
- напоминать правило source of truth.

README не должен хранить требования, решения, технические контракты, планы, статусы, инструкции по деплою или другие детальные факты. Для таких данных нужно обновлять профильный документ-владелец из таблицы Source of Truth.

## 01-product

В `01-product/` должны оставаться продуктовые и управленческие документы:

- `strategy/PROJECT.md`
- `strategy/ROADMAP.md`
- `strategy/STATE.md`
- `planning/BACKLOG.md`
- `planning/PLAN.md`
- `requirements/REQUIREMENTS.md`
- `requirements/USER_FLOWS.md`
- `growth/MONETIZATION.md`
- `growth/ANALYTICS.md`
- `knowledge/WIKI.md`

Не нужно держать здесь технические реализации, test plans, release runbooks, инфраструктурные инструкции и документы по конкретным одноразовым фичам. Их нужно:

- перенести в `requirements/REQUIREMENTS.md`, если это требования;
- перенести в `requirements/USER_FLOWS.md`, если это пользовательские сценарии;
- перенести в `growth/MONETIZATION.md`, если это реклама, покупки, подписки или paywall;
- перенести в `growth/ANALYTICS.md`, если это события, воронки, метрики или конверсии;
- перенести в `strategy/STATE.md`, если это текущее состояние, активный вопрос или последнее решение;
- перенести в `knowledge/WIKI.md`, если это стабильное знание;
- перенести в `03-engineering/architecture/` или `03-engineering/stack/`, если это технический контракт;
- перенести в `04-quality/`, если это тестовый checklist;
- перенести в `05-operations/`, если это эксплуатация;
- отправить в `99-archive/`, если документ специфичен для старого проекта или больше не является активным.

## 02-team

`02-team/` описывает, как выполнять работу через людей или агентов в CEO-first модели.

Ключевые документы:

- [`people/TEAM.md`](../02-team/people/TEAM.md) - общая модель команды.
- [`people/ROLES.md`](../02-team/people/ROLES.md) - роли и зоны ответственности.
- [`process/TASK_ROUTING.md`](../02-team/process/TASK_ROUTING.md) - маршрутизация задач сверху вниз.
- [`process/WORKFLOW.md`](../02-team/process/WORKFLOW.md) - цикл работы, статусы, handoff и acceptance.
- [`people/ONBOARDING.md`](../02-team/people/ONBOARDING.md) - быстрый ввод нового человека.
- [`process/BRANCHING.md`](../02-team/process/BRANCHING.md) - правила веток.
- [`process/REVIEW_POLICY.md`](../02-team/process/REVIEW_POLICY.md) - правила ревью.

Основные группы:

- Management: CEO Agent, CTO Agent, Product Manager Agent, Tech Lead Agent.
- Development: Developer Feature Agent, Developer Bug Fix Agent, Developer Test Writer Agent, Developer Code Reviewer Agent.
- Quality: QA Agent, Security Agent.
- Operations: DevOps Agent.
- Knowledge: Documentation Agent.

Роли можно совмещать, но вход остается один: CEO Agent. В маленьком проекте CEO Agent может последовательно выполнить остальные роли. В командной работе CEO Agent назначает владельцев, review и handoff.

## Ветки

Ветки используются при необходимости:

- параллельная работа;
- code review;
- риск конфликтов;
- рискованный refactor;
- релизная изоляция;
- работа нескольких агентов.

Если проект ведет один человек и изменение маленькое, отдельная ветка не обязательна. Правило описано в [`02-team/process/BRANCHING.md`](../02-team/process/BRANCHING.md).

## Архив

`99-archive/project-specific/` хранит старые или проектно-специфичные документы, которые не должны влиять на новый универсальный шаблон.

Архив нужен только для сохранения истории и возможного ручного переноса полезных фрагментов. Архивные документы не являются source of truth.

## Как добавлять новый документ

Перед созданием нового файла ответьте:

1. Какой факт этот документ будет хранить?
2. Почему это не помещается в существующий source of truth?
3. Кто владелец документа?
4. Кто читатель документа?
5. Когда документ должен обновляться?

Если ответы не ясны, лучше обновить существующий документ.

## Как удалять или объединять документы

Документ нужно удалить, объединить или отправить в архив, если он:

- дублирует другой документ;
- описывает уже завершенную одноразовую задачу;
- содержит устаревшую проектно-специфичную информацию;
- не имеет владельца;
- не используется для принятия решений, разработки, качества или операций.

Перед удалением перенесите полезные факты в актуальный source of truth.

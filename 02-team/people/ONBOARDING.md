# ONBOARDING

## Назначение

Этот документ помогает быстро ввести нового участника-человека в проект: что читать, как собрать и запустить проект, какие команды использовать и какие типовые ошибки ожидать.

Для агентов процесс описан в [`TEAM.md`](TEAM.md), [`../process/TASK_ROUTING.md`](../process/TASK_ROUTING.md) и файлах `../agents/`.

## Быстрый старт

1. Прочитать [`../00-context/DOCS.md`](../../00-context/DOCS.md).
2. Прочитать [`01-product/strategy/PROJECT.md`](../../01-product/strategy/PROJECT.md).
3. Прочитать [`01-product/strategy/STATE.md`](../../01-product/strategy/STATE.md).
4. Прочитать [`01-product/strategy/ROADMAP.md`](../../01-product/strategy/ROADMAP.md).
5. Прочитать [`01-product/planning/BACKLOG.md`](../../01-product/planning/BACKLOG.md).
6. Прочитать проектные правила этапов в [`SPRINT_REGULATION.md`](../process/SPRINT_REGULATION.md).
7. Прочитать [`01-product/planning/PLAN.md`](../../01-product/planning/PLAN.md).
8. Проверить свою роль в [`ROLES.md`](ROLES.md).
9. Настроить окружение по [`../05-operations/ENVIRONMENT.md`](../../05-operations/ENVIRONMENT.md).
10. Запустить проект и тесты.

## Что понять в первый день

- Что делает проект.
- Кто пользователь.
- Какой текущий фокус.
- Какие документы являются source of truth.
- Как задачи проходят через CEO-first процесс.
- Как в проекте устроены аналитика, планирование, разработка, тестирование, публикация и отчет.
- Где смотреть баги и качество.
- Как запускать проект локально.

## Локальная сборка и запуск

Команды ниже должны совпадать с одноименными строками из [`../../05-operations/COMMANDS.md`](../../05-operations/COMMANDS.md).

Описание проектных скриптов хранится в [`../../05-operations/SCRIPTS.md`](../../05-operations/SCRIPTS.md).

## Основные команды

| Команда | Назначение | Когда использовать |
| --- | --- | --- |
| `TODO` | Установка зависимостей | Первый запуск или обновление зависимостей |
| `TODO` | Локальный запуск | Разработка |
| `TODO` | Тесты | Перед review или релизом |
| `TODO` | Линт | Перед сдачей изменений |
| `TODO` | Format | Перед review, если поддерживается проектом |
| `TODO` | Build | Перед релизом или деплоем |

## Доступы

| Доступ | Кому нужен | Кто выдает | Где описан |
| --- | --- | --- | --- |
| Репозиторий | Разработчики, reviewers |  |  |
| Staging | QA, Product, Developers |  |  |
| Production | Ограниченный круг |  | [`../05-operations/SECURITY.md`](../../05-operations/SECURITY.md) |
| Analytics и store-данные | Analyst, Product, CEO |  | [`01-product/growth/ANALYTICS.md`](../../01-product/growth/ANALYTICS.md) |

## Типовые ошибки

| Ошибка | Симптом | Что проверить | Куда смотреть |
| --- | --- | --- | --- |
| Не установлены зависимости | Команда запуска падает | Версии runtime и package manager | [`03-engineering/stack/STACK.md`](../../03-engineering/stack/STACK.md) |
| Нет переменных окружения | Ошибка конфигурации | `.env`, secrets, environment docs | [`../05-operations/ENVIRONMENT.md`](../../05-operations/ENVIRONMENT.md) |
| Нет доступа | 401 / 403 / permission denied | Роли и доступы | [`../05-operations/SECURITY.md`](../../05-operations/SECURITY.md) |
| Тесты падают локально | Красный test run | Версии, fixtures, локальная среда | [`../04-quality/TESTING.md`](../../04-quality/TESTING.md) |

## Как брать задачу

Новый участник не должен выбирать случайную задачу из документов.

Правильный порядок:

1. CEO Agent или Tech Lead Agent назначает задачу и owner.
2. Участник читает связанный контекст.
3. Если нужен branch, Tech Lead Agent задает ветку по [`BRANCHING.md`](../process/BRANCHING.md).
4. Участник выполняет задачу.
5. Участник передает результат через review и handoff.

## Первые задачи для нового участника

| Задача | Цель | Проверка |
| --- | --- | --- |
| Собрать проект локально | Проверить окружение | Build проходит |
| Запустить тесты | Проверить toolchain | Tests проходят или известны причины |
| Исправить маленький docs/task issue | Пройти процесс review | Review завершен |

## Куда обращаться

| Вопрос | К кому / куда |
| --- | --- |
| Приоритеты и scope | CEO Agent / Product Manager Agent |
| Техническое решение | CTO Agent / Tech Lead Agent |
| Баги и тесты | QA Agent / Developer Bug Fix Agent |
| Метрики, воронки, аномалии и отчеты | Analyst Agent |
| Деплой и окружения | DevOps Agent |
| Документация | Documentation Agent |

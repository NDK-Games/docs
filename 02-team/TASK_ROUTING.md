# TASK_ROUTING

## Назначение

Этот документ помогает CEO Agent быстро понять, кому отдавать задачу и какой шаблон должен быть заполнен агентом.

Пользователь не выбирает маршрут и не заполняет шаблон. Пользователь описывает цель или проблему. CEO Agent выполняет intake, выбирает маршрут, назначает owner и передает работу вниз.

## CEO intake

Каждый входящий запрос сначала проходит через CEO Agent.

| Вход пользователя | Что делает CEO Agent | Следующая роль |
| --- | --- | --- |
| "Хочу сделать..." | Проверяет ценность, приоритет и scope | Product Manager Agent |
| "Нужно исправить..." | Определяет влияние и срочность | Tech Lead Agent / Developer Bug Fix Agent |
| "Появился риск..." | Решает, бизнес это, техника, качество или безопасность | CTO / QA / Security |
| "Нужно выпустить..." | Проверяет готовность и go / no-go | DevOps Agent |
| "Нужно организовать команду..." | Назначает роли, owners и правила веток | Tech Lead Agent |
| "Обнови документацию..." | Определяет source of truth | Documentation Agent |

## Маршрутизация

| Тип задачи | Кто назначает | Основная роль | Подключить при необходимости | Шаблон |
| --- | --- | --- | --- | --- |
| Новая функция | CEO Agent | Product Manager Agent -> Tech Lead -> Developer Feature Agent | QA | [`FEATURE_TEMPLATE.md`](TEMPLATES/FEATURE_TEMPLATE.md) |
| Баг | CEO Agent | Tech Lead -> Developer Bug Fix Agent | QA | [`BUGFIX_TEMPLATE.md`](TEMPLATES/BUGFIX_TEMPLATE.md) |
| Тесты | CEO Agent / Tech Lead | Developer Test Writer Agent | QA, Feature Developer | [`TASK_TEMPLATE.md`](TEMPLATES/TASK_TEMPLATE.md) |
| Ревью | CEO Agent / Tech Lead | Developer Code Reviewer Agent | Security, QA | [`REVIEW_TEMPLATE.md`](TEMPLATES/REVIEW_TEMPLATE.md) |
| Архитектурное решение | CEO Agent | CTO Agent | Tech Lead, Security | ADR |
| Релиз / деплой | CEO Agent | DevOps Agent | QA, Tech Lead | [`../05-operations/RELEASE_CHECKLIST.md`](../05-operations/RELEASE_CHECKLIST.md) |
| Документация | CEO Agent | Documentation Agent | Владелец области | [`TASK_TEMPLATE.md`](TEMPLATES/TASK_TEMPLATE.md) |

## Жизненный цикл задачи

1. CEO Intake: пользовательский запрос превращен в управляемую запись.
2. CEO Triage: понятны приоритет, риск, scope и следующая роль.
3. Delegation: CEO Agent назначил owner и передал задачу вниз.
4. Execution: работа выполняется в основном потоке или отдельной ветке.
5. Review: код, тесты, продуктовая логика и документация проверены.
6. CEO Acceptance: CEO Agent принимает итог или возвращает на доработку.
7. Done: результат принят, документы обновлены, follow-up вынесен отдельно.

## Правило автозаполнения

Шаблоны из `TEMPLATES/` заполняет назначенная роль:

- Product Manager Agent заполняет feature scope и acceptance criteria.
- Tech Lead Agent заполняет технический план, owner и ветку.
- Developer Agent заполняет реализацию, проверки и handoff.
- QA Agent заполняет test report и баги.
- Documentation Agent обновляет source of truth.
- CEO Agent обновляет итоговый статус и управленческое решение.

Если данных не хватает, агент не оставляет пустой шаблон пользователю. Он либо делает разумное допущение и помечает его, либо задает короткий блокирующий вопрос.

## Приоритеты

| Приоритет | Значение | Требование |
| --- | --- | --- |
| P0 | Блокирует пользователей, релиз или данные | Работать немедленно |
| P1 | Важная функциональность или серьезная регрессия | Планировать в текущий фокус |
| P2 | Полезное улучшение или средний баг | Планировать по capacity |
| P3 | Низкий риск, polish, cleanup | Делать только если не мешает P0-P2 |

## Definition of Ready

- Цель понятна.
- Есть owner.
- Есть критерии приемки.
- Известны основные риски.
- Понятно, нужна ли отдельная ветка.

## Definition of Done

- Изменение реализовано.
- Проверки выполнены или явно указано, что не удалось проверить.
- Ревью пройдено, если оно требуется.
- Документация обновлена.
- Follow-up задачи не спрятаны внутри комментариев.

# TASK_ROUTING

## Назначение

Этот документ помогает CEO Agent быстро понять, кому отдавать задачу и какой шаблон должен быть заполнен агентом.

Пользователь не выбирает маршрут и не заполняет шаблон. Пользователь описывает цель или проблему. CEO Agent выполняет intake, выбирает маршрут, назначает owner и передает работу вниз.

## CEO intake

Каждый входящий запрос сначала проходит через CEO Agent.

| Вход пользователя | Что делает CEO Agent | Следующая роль |
| --- | --- | --- |
| "CEO, сделай..." | Определяет уровень `roadmap | sprint | task`, готовит план для Product Owner и, для `sprint` / `task`, командный план | Product Manager Agent / Tech Lead Agent |
| "Хочу сделать..." | Проверяет ценность, приоритет и scope | Product Manager Agent |
| "Нужно исправить..." | Определяет влияние и срочность | Tech Lead Agent / Developer Bug Fix Agent |
| "Появился риск..." | Решает, бизнес это, техника, качество или безопасность | CTO / QA / Security |
| "Проанализируй показатели / воронку / поведение..." | Уточняет решение, период, метрики и доступные источники данных | Analyst Agent |
| "Показатель изменился / появилась аномалия..." | Определяет влияние и срочность, назначает проверку данных и причин | Analyst Agent / Product Manager Agent / Tech Lead Agent |
| "Нужно выпустить..." | Проверяет готовность и go / no-go | DevOps Agent |
| "Нужно организовать команду..." | Назначает роли, owners и правила веток | Tech Lead Agent |
| "Обнови документацию..." | Определяет source of truth | Documentation Agent |

## Маршрутизация

| Тип задачи | Кто назначает | Основная роль | Подключить при необходимости | Шаблон |
| --- | --- | --- | --- | --- |
| Новая функция | CEO Agent | Product Manager Agent -> Tech Lead -> Developer Feature Agent | QA | [`FEATURE_TEMPLATE.md`](../templates/FEATURE_TEMPLATE.md) |
| Баг | CEO Agent | Tech Lead -> Developer Bug Fix Agent | QA | [`BUGFIX_TEMPLATE.md`](../templates/BUGFIX_TEMPLATE.md) |
| Тесты | CEO Agent / Tech Lead | Developer Test Writer Agent | QA, Feature Developer | [`TASK_TEMPLATE.md`](../templates/TASK_TEMPLATE.md) |
| Ревью | CEO Agent / Tech Lead | Developer Code Reviewer Agent | Security, QA | [`REVIEW_TEMPLATE.md`](../templates/REVIEW_TEMPLATE.md) |
| Проверка качества аналитики | CEO Agent / Product Manager | Analyst Agent | Tech Lead, QA | [`ANALYTICS_REPORT_TEMPLATE.md`](../templates/ANALYTICS_REPORT_TEMPLATE.md) |
| Метрики, воронки, сегменты, поведение, монетизация | CEO Agent / Product Manager | Analyst Agent | Tech Lead, Documentation | [`ANALYTICS_REPORT_TEMPLATE.md`](../templates/ANALYTICS_REPORT_TEMPLATE.md) |
| Аномалия, анализ релиза или A/B-теста | CEO Agent | Analyst Agent | Product Manager, Tech Lead, QA | [`ANALYTICS_REPORT_TEMPLATE.md`](../templates/ANALYTICS_REPORT_TEMPLATE.md) |
| Анализ отзывов | CEO Agent / Product Manager | Analyst Agent | QA, Product Manager | [`ANALYTICS_REPORT_TEMPLATE.md`](../templates/ANALYTICS_REPORT_TEMPLATE.md) |
| Архитектурное решение | CEO Agent | CTO Agent | Tech Lead, Security | ADR |
| Релиз / деплой | CEO Agent | DevOps Agent | QA, Tech Lead | [`../05-operations/RELEASE_CHECKLIST.md`](../../05-operations/RELEASE_CHECKLIST.md) |
| Документация | CEO Agent | Documentation Agent | Владелец области | [`TASK_TEMPLATE.md`](../templates/TASK_TEMPLATE.md) |

## Жизненный цикл задачи

1. CEO Intake: пользовательский запрос превращен в управляемую запись.
2. CEO Planning: выбран уровень `roadmap | sprint | task` и подготовлен рабочий план для Product Owner.
3. CEO Triage: понятны приоритет, риск, scope и следующая роль.
4. Team Plan: для `sprint` или `task` описаны owner, агенты, зоны ответственности, последовательные шаги, параллельные работы, зависимости, handoff и проверки.
5. Delegation: CEO Agent назначил owner и передал задачу вниз.
6. Execution: работа выполняется в основном потоке или отдельной ветке.
7. Review: код, тесты, продуктовая логика и документация проверены.
8. CEO Acceptance: CEO Agent принимает итог или возвращает на доработку.
9. Done: результат принят, документы обновлены, follow-up вынесен отдельно.

## Правило автозаполнения

Шаблоны из `../templates/` заполняет назначенная роль:

- CEO Agent отвечает за наличие рабочего плана для Product Owner и командного плана для `sprint` / `task`.
- Product Manager Agent заполняет feature scope и acceptance criteria.
- Tech Lead Agent заполняет технический план, owner, ветку, зависимости и порядок параллельной / последовательной работы.
- Developer Agent заполняет реализацию, проверки и handoff.
- QA Agent заполняет test report и баги.
- Analyst Agent проверяет качество источников, заполняет [`ANALYTICS_REPORT_TEMPLATE.md`](../templates/ANALYTICS_REPORT_TEMPLATE.md), фиксирует ограничения и передает рекомендации владельцам решений.
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
- Уровень планирования выбран: `roadmap | sprint | task`.
- Рабочий план для Product Owner записан простым языком.
- Есть owner.
- Есть критерии приемки.
- Известны основные риски.
- Для `sprint` или `task` есть командный план: кто что делает, что идет последовательно, что идет параллельно, где handoff и проверки.
- Понятно, нужна ли отдельная ветка.

## Definition of Done

- Изменение реализовано.
- Проверки выполнены или явно указано, что не удалось проверить.
- Ревью пройдено, если оно требуется.
- Документация обновлена.
- Follow-up задачи не спрятаны внутри комментариев.

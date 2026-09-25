# Александр Литвиненко

**AI Product Manager · AI × 1C · Bitrix24 · открытый код**

**Русский** · [English](README.en.md)

Собираю и проверяю способы подключить AI-агента к «1С:Предприятию» и Bitrix24. Публикую то, что работает, и пишу, где у этого границы. Ещё делаю сервисы вокруг 1С и сайты, почти всё живёт на product1c.ru.

[![AI × 1C Guide](https://img.shields.io/badge/гайд-AI%20×%201C-0d7d7d)](https://github.com/Aleksandr-Litvinenko/1c-ai-guide)
[![Telegram](https://img.shields.io/badge/Telegram-@DED__GENA-26A5E4?logo=telegram&logoColor=white)](https://t.me/DED_GENA)

---

## AI × 1C Guide

[**AI × 1C Guide**](https://github.com/Aleksandr-Litvinenko/1c-ai-guide) отвечает на один вопрос: какими способами AI-агент подключается к «1С:Предприятию» и Bitrix24, что даёт каждый способ и где он опасен.

В каталоге 14 проектов экосистемы. Для каждого записаны commit, лицензия, требования, поверхность доступа и известные операции записи, а также что именно проверено: документация, релизный артефакт, локальный CLI smoke-test или живой endpoint.

Четыре подключения разобраны пошагово:

| Подключение | Что подтверждено | Инструкция |
|---|---|---|
| **OData в 1С:Фреш** | Приватный live-GET к «1С:УНФ»: `$metadata`, выборка документов, чтение по `Ref_Key`. Создание непроведённого документа реализовано в рабочем коде | [Чтение и тестовая запись](https://github.com/Aleksandr-Litvinenko/1c-ai-guide/blob/main/guides/1cfresh-odata.md) |
| **Задачи Bitrix24** | Рабочий runtime в `task2bitrix24`: `tasks.task.list`, результаты, списанное время, пользователи, связанные CRM-объекты, пагинация и `batch` | [Список задач и карточка по ID](https://github.com/Aleksandr-Litvinenko/1c-ai-guide/blob/main/guides/bitrix24-tasks.md) |
| **Лиды Bitrix24** | Приватный `crm.lead.add` с контрольным чтением записанных полей; актуальный пример переведён на универсальный `crm.item.add` | [Backend-вебхук и создание лида](https://github.com/Aleksandr-Litvinenko/1c-ai-guide/blob/main/guides/bitrix24-leads.md) |
| **1С-Коннект + Jira + Bitrix24** | Jira-часть проверена живыми анонимными запросами к публичному Jira фонда Apache, повторить можно без учётной записи. SOAP-API 1С-Коннект разобран по официальной документации | [Сверка трёх систем](https://github.com/Aleksandr-Litvinenko/1c-ai-guide/blob/main/guides/connect-jira-bitrix24.md) |

Примеры на Python по умолчанию безопасны: команды чтения не умеют вызывать методы записи, чувствительные значения в выводе скрыты, запись привязана к отпечатку конкретного стенда. Секреты остаются в локальном окружении и не попадают в prompt.

Реестру не хватает end-to-end проверок на Windows и Linux с реальной тестовой базой 1С, негативных тестов запрещённых операций, точных версий платформы, сведений о лицензиях и авторизации. Если есть что прислать, начните с [CONTRIBUTING](https://github.com/Aleksandr-Litvinenko/1c-ai-guide/blob/main/CONTRIBUTING.md).

---

## Сервисы

| Проект | Что делает | Технологии |
|---|---|---|
| [**1cProductMap**](https://github.com/Aleksandr-Litvinenko/1cProductMap) · [map.product1c.ru](https://map.product1c.ru/) | Карта линейки 1С: подбор по задаче и размеру компании, расчёт комплекта по официальному прайсу, заявка сразу в Bitrix24 | Python · JSON Schema |
| [**ProjectControl**](https://github.com/Aleksandr-Litvinenko/ProjectControl) · [projectcrm.ru](https://projectcrm.ru/) | Рабочее место проектного офиса: портфель проектов, обязательные чек-листы, диаграмма Ганта, загрузка специалистов | TypeScript · React · PostgreSQL · Docker |
| [**task2bitrix24**](https://github.com/Aleksandr-Litvinenko/task2bitrix24) | Панель над Bitrix24 и «1С:УНФ»: закрытые часы в Excel, проверка задач перед выставлением счёта, KPI, документы в УНФ одной кнопкой | PHP · Bitrix24 REST · OData |
| [**Ondal**](https://github.com/Aleksandr-Litvinenko/ondal) · [демо](https://ondal.product1c.ru) | Управленческий учёт: счета с согласованием, склад, P&L, ДДС, платёжный календарь и выгрузка в 1С по OData | TypeScript · React · PostgreSQL |
| [**Ладно**](https://github.com/Aleksandr-Litvinenko/ladno) · [демо](https://ladno.product1c.ru) | Демо учёта целиком в браузере: счета, склад, P&L и платёжный календарь | JavaScript без зависимостей |
| [**education1c**](https://github.com/Aleksandr-Litvinenko/education1c) · [edu.product1c.ru](https://edu.product1c.ru/) | Программа адаптации стажёров 1С и менеджеров по продажам, пока до запуска | HTML · CSS · проектирование обучения |

## Сайты

Сайты с WebGL-графикой. Код закрыт, в репозиториях описано, как они сделаны и чем проверены.

- [**Резюме**](https://cv.product1c.ru) · cv.product1c.ru: резюме AI Founder и Product Manager на русском и английском. Граф из частиц на WebGL2 перестраивается под каждый раздел.
- [**Product1C**](https://github.com/Aleksandr-Litvinenko/beautydesign) · [beautydesign.product1c.ru](https://beautydesign.product1c.ru): сайт студии, хромированный объект с эффектом глубины.
- [**Product1C 3D**](https://github.com/Aleksandr-Litvinenko/product1c-new) · [new.product1c.ru](https://new.product1c.ru/): одна сцена из частиц на Three.js проходит пять форм при прокрутке.
- [**cBrain**](https://github.com/Aleksandr-Litvinenko/cbrain) · [cbrain.product1c.ru](https://cbrain.product1c.ru): рой из 110 000 частиц на чистом WebGL2 перестраивается по прокрутке.

## Скиллы для AI-агентов на русском

- [**agent-skills-ru**](https://github.com/Aleksandr-Litvinenko/agent-skills-ru) · [claude.product1c.ru](https://claude.product1c.ru): перевод agent-skills Addy Osmani, 24 скилла от спеки до релиза. На сайте их можно найти и собрать свой набор.
- [**ladny-interface**](https://github.com/Aleksandr-Litvinenko/ladny-interface): адаптация навыков дизайн-инженерии Emil Kowalski, с примером интерфейса для 1С.

## Эксперименты с AI-генерацией кода

Прототипы, которые целиком написали AI-инструменты. За продукты я их не выдаю: они нужны, чтобы сравнить Claude Code, Codex и Qwen на одинаковых задачах. Поэтому часть проектов идёт парами.

- **Crown Defender TD**, 3D tower defense: [версия Claude Code](https://github.com/Aleksandr-Litvinenko/Claude-code.-Crown-Defender-TD-3D-browser-tower-defense-game) и [версия Codex](https://github.com/Aleksandr-Litvinenko/Codex.-Crown-Defender-TD-3D-browser-tower-defense-game).
- **AI Project Executor**, проектные документы по расписанию: [реализация Claude Code](https://github.com/Aleksandr-Litvinenko/Claude_code.-project-crm) и [спецификация Codex](https://github.com/Aleksandr-Litvinenko/Codex.-project-crm).
- **Аркады в браузере**: [GamesIO](https://github.com/Aleksandr-Litvinenko/GamesIO) с десятью играми и [GeneratedGamesIO](https://github.com/Aleksandr-Litvinenko/GeneratedGamesIO) с восемью играми для телефона.
- [**NEUROCORP**](https://github.com/Aleksandr-Litvinenko/neuro_company_claude): компания из ИИ-агентов, человек только согласует проект и КП.
- [**Mini Moba**](https://github.com/Aleksandr-Litvinenko/mini_mobile): MOBA на Unity, 1 на 1 по сети или против бота.
- [**Outpost Siege**](https://github.com/Aleksandr-Litvinenko/OutpostSiegeTD): tower defense на чистом JS, 20 осад по 20 волн.

---

## Как я работаю

- Сначала разбираюсь в бизнес-задаче, модель выбираю потом.
- По умолчанию агент получает доступ только на чтение, а запись подтверждает человек.
- В текстах отделяю проверенный факт от эксперимента и предположения.
- Не называю решение безопасным, пока запрет не проверен негативным тестом.
- Публикую документацию вместе с кодом, а ограничения вместе с результатом.

## Темы

**1С:** «1С:Предприятие» 8.3, 1С:Фреш, 1С:УНФ, стандартный OData-интерфейс, HTTP-сервисы, BSL, 1C:EDT, выгрузка конфигурации.

**Bitrix24:** REST API, входящие вебхуки, задачи, CRM и лиды, `batch`, лимиты запросов.

**AI:** MCP (Model Context Protocol), Agent Skills, Claude Code, Codex, Cursor, function calling, RAG, AI-ассистированная разработка.

**Продукт:** управление продуктом, аудит бизнес-процессов, операционные дашборды, обучение команд 1С.

**Веб:** React, Three.js и WebGL, статические сайты за nginx, выкладка релизами с откатом.

## Контакты

- Telegram: [@DED_GENA](https://t.me/DED_GENA)
- Вопрос по проекту: issue в нужном репозитории

Проекты о 1С в основном на русском: документация экосистемы существует прежде всего на нём. Английские версии добавляю там, где они помогают пользователям и участникам.

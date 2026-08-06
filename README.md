# Архитектор ПО: учебник

Подробный учебник по профессии **архитектора программного обеспечения** — от архитектурного мышления до синтеза реальных систем. Для крепких Middle/Senior-инженеров, которые двигаются к роли архитектора.

**17 модулей · 86 глав.** Каждая глава самодостаточна: теория, примеры кода на TypeScript, развёрнутые кейсы, антипаттерны, упражнения и плотные перекрёстные ссылки между темами.

---

## Что это и для кого

Учебник учит *архитектурному мышлению*, а не заучиванию паттернов. Сквозные принципы, проходящие через все главы:

- **Всё компромисс** — нет «правильной» архитектуры, есть осознанный выбор под контекст с понятой ценой.
- **По нужде, не по моде** — монолит, микросервисы, паттерны и технологии должны заработать своё место.
- **Под контекст** — нет универсально правильной архитектуры; есть уместная бизнесу, стадии и отрасли.
- **«Почему» важнее «как»** — обоснование решения важнее самого решения.
- **Не изобретай** — бери проверенное для общего, строй своё уникальное.
- **Soft skills — ядро роли** — архитектура живёт через людей, коммуникацию и лидерство.
- **Архитектура служит бизнесу** — техника это средство, не цель.

## Формат главы (9 блоков)

1. Зачем это нужно · 2. Теория · 3. Подходы/Паттерны · 4. Пример кода (TypeScript) · 5. Развёрнутый кейс · 6. Антипаттерны и ловушки · 7. Ключевые выводы (чеклист) · 8. Упражнения и вопросы · 9. Что почитать дальше.

Главы Модуля 16 — справочные, у них своя структура.

## Как читать

- **Последовательно** — модули выстроены по нарастанию: мышление → требования → структура → распределённость → данные → эксплуатация → люди → бизнес → синтез. Это рекомендованный путь для первого прохода.
- **По модулям** — каждая глава самодостаточна; можно нырять в нужную тему.
- **Capstone (Модуль 15)** связывает всё воедино — сквозной кейс, тренировка через каты, подготовка к собеседованиям и путь дальнейшего роста.
- **Справочник (Модуль 16)** — для быстрого обращения: числа для оценок и глоссарий с английскими оригиналами терминов.

### Как устроены ссылки

- **`§2.4`** — раздел *внутри текущей главы*.
- **4.4** ссылкой — переход на *другую главу* учебника (модуль 4, глава 4).
- **М8** ссылкой — переход на оглавление модуля.
- В конце каждой главы — блок **«Связанные главы»** (на что опирается и к чему ведёт) и панель навигации «назад / вверх / вперёд».

---

## Оглавление

### Модуль 0. Профессия и мышление
Что такое архитектура, кто такой архитектор и как он думает.

- [0.1. Что такое архитектура](./00-professiya/00-01-chto-takoe-arhitektura.md) — что относится к архитектуре, а что нет; значимые решения и их цена.
- [0.2. Роль и типы архитекторов](./00-professiya/00-02-rol-i-tipy-arhitektorov.md) — виды архитекторов, высота абстракции, место в организации.
- [0.3. Обязанности и мифы](./00-professiya/00-03-obyazannosti-i-mify.md) — чем архитектор реально занят; risk-driven, последний ответственный момент; развенчание мифов.
- [0.4. Архитектурное мышление](./00-professiya/00-04-arhitekturnoe-myshlenie.md) — всё компромисс; односторонние/двусторонние двери; «почему важнее как».
- [0.5. Карьерный трек и soft skills](./00-professiya/00-05-karernyy-trek-i-soft-skills.md) — путь к роли; soft skills как ядро; коммуникация и влияние.

### Модуль 1. Атрибуты качества и требования
Нефункциональные требования, которые лепят архитектуру.

- [1.1. Функциональные vs нефункциональные](./01-atributy-kachestva/01-01-funkcionalnye-vs-nefunkcionalnye.md) — почему НФТ определяют архитектуру (кейс билетов).
- [1.2. Каталог атрибутов качества](./01-atributy-kachestva/01-02-katalog-atributov-kachestva.md) — ISO 25010, ключевые атрибуты и их связи.
- [1.3. ASR и как их вытаскивать](./01-atributy-kachestva/01-03-asr-i-kak-ih-vytaskivat.md) — архитектурно значимые требования; как извлекать у стейкхолдеров.
- [1.4. Сценарии качества](./01-atributy-kachestva/01-04-scenarii-kachestva.md) — измеримые сценарии вместо абстрактных «надёжно/быстро».
- [1.5. Управление компромиссами](./01-atributy-kachestva/01-05-upravlenie-kompromissami.md) — конфликты атрибутов; «достаточно хорошо».

### Модуль 2. Архитектурные стили
Палитра стилей и как выбирать.

- [2.1. Монолит и модульный монолит](./02-stili/02-01-monolit-i-modulnyy-monolit.md) — почему модульный монолит — разумный дефолт.
- [2.2. Слоистая, луковичная, гексагональная, Clean](./02-stili/02-02-sloistaya-lukovichnaya-geksagonalnaya-clean.md) — изоляция домена от инфраструктуры.
- [2.3. Микросервисы и SOA](./02-stili/02-03-mikroservisy-i-soa.md) — премия за распределённость, операционная зрелость, распределённый монолит.
- [2.4. Event-Driven Architecture](./02-stili/02-04-event-driven-architecture.md) — события, асинхронность, развязка.
- [2.5. Микроядро, space-based, pipeline](./02-stili/02-05-microkernel-spacebased-pipeline.md) — специализированные стили под специфичные требования.
- [2.6. Serverless](./02-stili/02-06-serverless.md) — функции, масштаб до нуля, ограничения.
- [2.7. Как выбирать стиль](./02-stili/02-07-kak-vybirat-stil.md) — выбор от требований, не от моды.

### Модуль 3. Декомпозиция и DDD
Как делить систему на части.

- [3.1. Связанность, сцепление, connascence](./03-dekompoziciya-ddd/03-01-svyazannost-sceplenie-connascence.md) — фундамент хороших границ.
- [3.2. Принципы декомпозиции](./03-dekompoziciya-ddd/03-02-principy-dekompozicii.md) — SRP, Парнас, инкапсуляция волатильности.
- [3.3. DDD стратегический](./03-dekompoziciya-ddd/03-03-ddd-strategicheskiy.md) — bounded context, context mapping, ACL, EventStorming.
- [3.4. DDD тактический](./03-dekompoziciya-ddd/03-04-ddd-takticheskiy.md) — агрегат как граница согласованности; антипаттерн анемичной модели.
- [3.5. Границы сервисов и модулей](./03-dekompoziciya-ddd/03-05-granicy-servisov-i-moduley.md) — логическая ≠ физическая граница; владение данными.

### Модуль 4. Распределённые системы
Что меняется, когда система распределена.

- [4.1. Заблуждения и сетевые основы](./04-raspredelennye-sistemy/04-01-zabluzhdeniya-i-setevye-osnovy.md) — 8 заблуждений распределёнки; всё отказывает.
- [4.2. CAP, PACELC, модели согласованности](./04-raspredelennye-sistemy/04-02-cap-pacelc-modeli-soglasovannosti.md) — спектр согласованности, strong vs eventual.
- [4.3. Консенсус: Raft, Paxos](./04-raspredelennye-sistemy/04-03-konsensus-raft-paxos.md) — кворумы, не пиши свой консенсус.
- [4.4. Паттерны устойчивости](./04-raspredelennye-sistemy/04-04-patterny-ustoychivosti.md) — таймауты, retry+backoff+jitter, circuit breaker, bulkhead, backpressure, деградация.
- [4.5. Распределённые транзакции, Saga](./04-raspredelennye-sistemy/04-05-raspredelennye-tranzakcii-saga.md) — компенсации, хореография/оркестрация, идемпотентность, transactional outbox.

### Модуль 5. Данные
Хранение, обработка и интеграция данных.

- [5.1. Выбор хранилища](./05-dannye/05-01-vybor-hranilisch.md) — от формы и доступа; реляционка как дефолт.
- [5.2. Polyglot persistence](./05-dannye/05-02-polyglot-persistence.md) — разные хранилища по нужде; источник истины.
- [5.3. Event Sourcing и CQRS](./05-dannye/05-03-event-sourcing-cqrs.md) — два разных паттерна, когда оправданы.
- [5.4. Стратегии кэширования](./05-dannye/05-04-strategii-keshirovaniya.md) — cache-aside, инвалидация — трудная задача.
- [5.5. Batch и stream конвейеры](./05-dannye/05-05-batch-stream-konveery.md) — ограниченные vs неограниченные данные, CDC, event time, окна.
- [5.6. Паттерны интеграции (EIP)](./05-dannye/05-06-patterny-integracii-eip.md) — умные конечные точки, тупые трубы.
- [5.7. Мультитенантность](./05-dannye/05-07-multitenantnost.md) — silo/pool/bridge, изоляция арендаторов, шумный сосед, стоимость на клиента.

### Модуль 6. Взаимодействие и API
Как части системы общаются.

- [6.1. Синхронное vs асинхронное](./06-vzaimodeystvie-api/06-01-sinhronnoe-vs-asinhronnoe.md) — временна́я связанность, математика доступности.
- [6.2. REST, gRPC, GraphQL](./06-vzaimodeystvie-api/06-02-rest-grpc-graphql.md) — выбор стиля API под контекст.
- [6.3. Очереди, брокеры, streaming, Kafka](./06-vzaimodeystvie-api/06-03-ocheredi-brokery-streaming-kafka.md) — очередь vs лог; гарантии доставки.
- [6.4. Проектирование API и версионирование](./06-vzaimodeystvie-api/06-04-proektirovanie-api-versionirovanie.md) — контракт, аддитивная эволюция.
- [6.5. API Gateway, BFF, Service Mesh](./06-vzaimodeystvie-api/06-05-api-gateway-bff-service-mesh.md) — инфраструктура взаимодействия по нужде.

### Модуль 7. Безопасность
Безопасность как часть архитектуры.

- [7.1. Моделирование угроз (STRIDE)](./07-bezopasnost/07-01-modelirovanie-ugroz-stride.md) — систематический поиск угроз.
- [7.2. Аутентификация и авторизация](./07-bezopasnost/07-02-autentifikaciya-avtorizaciya.md) — AuthN ≠ AuthZ; авторизация объекта против IDOR; не изобретай auth.
- [7.3. Zero Trust](./07-bezopasnost/07-03-zero-trust.md) — не доверяй сети; минимум привилегий; blast radius.
- [7.4. Секреты и шифрование](./07-bezopasnost/07-04-sekrety-shifrovanie.md) — менеджер секретов, хеширование паролей, не изобретай крипто.
- [7.5. Secure by Design и цепочка поставок](./07-bezopasnost/07-05-secure-by-design-supply-chain.md) — shift-left, SCA/SBOM.

### Модуль 8. Надёжность, наблюдаемость, производительность
Чтобы система работала и это было видно.

- [8.1. SLI, SLO, SLA, бюджет ошибок](./08-nadezhnost-nablyudaemost-proizvoditelnost/08-01-sli-slo-sla-error-budget.md) — 100% — неверная цель; бюджет ошибок как руль.
- [8.2. Логи, метрики, трейсинг](./08-nadezhnost-nablyudaemost-proizvoditelnost/08-02-logi-metriki-trasing.md) — три столпа наблюдаемости; золотые сигналы.
- [8.3. SRE-практики](./08-nadezhnost-nablyudaemost-proizvoditelnost/08-03-sre-praktiki.md) — бюджет ошибок, борьба с toil, blameless-постмортемы.
- [8.4. Производительность и профилирование](./08-nadezhnost-nablyudaemost-proizvoditelnost/08-04-proizvoditelnost-profilirovanie.md) — латентность vs throughput; измеряй, не гадай.
- [8.5. Ёмкость и масштабирование](./08-nadezhnost-nablyudaemost-proizvoditelnost/08-05-emkost-i-masshtabirovanie.md) — вертикальное vs горизонтальное; statelessness; пределы.
- [8.6. Отказоустойчивость и DR](./08-nadezhnost-nablyudaemost-proizvoditelnost/08-06-otkazoustojchivost-dr.md) — избыточность, RTO/RPO, проверяй восстановление.

### Модуль 9. Cloud-native, инфраструктура, доставка
Где и как система работает и доставляется.

- [9.1. 12-factor и cloud-native](./09-cloud-native-infrastruktura-dostavka/09-01-12-factor-cloud-native.md) — свойства приложения; lift-and-shift ≠ cloud-native.
- [9.2. Контейнеры и оркестрация](./09-cloud-native-infrastruktura-dostavka/09-02-konteynery-i-orkestraciya.md) — Kubernetes; операционная цена; по нужде.
- [9.3. Инфраструктура как код (IaC)](./09-cloud-native-infrastruktura-dostavka/09-03-iac.md) — декларативность, неизменяемая инфраструктура.
- [9.4. CI/CD и стратегии доставки](./09-cloud-native-infrastruktura-dostavka/09-04-ci-cd-deployment-strategii.md) — часто и мелко; blue-green, canary, feature flags.
- [9.5. Стоимость и FinOps](./09-cloud-native-infrastruktura-dostavka/09-05-stoimost-finops.md) — стоимость как атрибут качества; видимость, right-sizing.
- [9.6. Стратегия тестирования](./09-cloud-native-infrastruktura-dostavka/09-06-strategiya-testirovaniya.md) — тестопригодность как свойство границ; пирамида, контрактные тесты, проверки в проде.

### Модуль 10. Документация и коммуникация
Как доносить архитектуру.

- [10.1. Модель C4](./10-dokumentaciya-kommunikaciya/10-01-c4-model.md) — контекст/контейнеры/компоненты/код; diagrams-as-code.
- [10.2. arc42 и 4+1](./10-dokumentaciya-kommunikaciya/10-02-arc42-4plus1.md) — полная документация и точки зрения.
- [10.3. Architecture Decision Records (ADR)](./10-dokumentaciya-kommunikaciya/10-03-adr.md) — фиксация решений с обоснованием.
- [10.4. UML и другие нотации](./10-dokumentaciya-kommunikaciya/10-04-uml.md) — прагматичный выбор диаграмм под задачу.
- [10.5. Коммуникация со стейкхолдерами](./10-dokumentaciya-kommunikaciya/10-05-kommunikaciya-so-stejkholderami.md) — язык бизнеса vs техники; влияние без полномочий.

### Модуль 11. Оценка и эволюция архитектуры
Как держать архитектуру хорошей во времени.

- [11.1. Оценка архитектуры (ATAM)](./11-ocenka-evolyuciya/11-01-ocenka-atam.md) — оценка против сценариев; точки чувствительности и компромисса.
- [11.2. Эволюционная архитектура и fitness functions](./11-ocenka-evolyuciya/11-02-evolyucionnaya-arhitektura.md) — непрерывная защита от эрозии.
- [11.3. Технический долг](./11-ocenka-evolyuciya/11-03-tehdolg.md) — осознанный vs неосознанный; выплачивай по процентам.
- [11.4. Легаси и strangler fig](./11-ocenka-evolyuciya/11-04-legasi-strangler-fig.md) — почему «переписать» обычно ошибка.
- [11.5. Миграции](./11-ocenka-evolyuciya/11-05-migracii.md) — постепенно и обратимо; миграция данных при сосуществовании.

### Модуль 12. Процессы, организация, люди
Архитектура неотделима от людей.

- [12.1. Закон Конвея](./12-processy-organizaciya-lyudi/12-01-zakon-konveya.md) — структура системы повторяет структуру организации; обратный манёвр.
- [12.2. Team Topologies](./12-processy-organizaciya-lyudi/12-02-team-topologies.md) — типы команд и режимы взаимодействия; когнитивная нагрузка.
- [12.3. Agile, процессы и риски](./12-processy-organizaciya-lyudi/12-03-agile-riski.md) — баланс upfront-дизайна и эволюции; walking skeleton.
- [12.4. Governance и стандарты](./12-processy-organizaciya-lyudi/12-04-governance-standarty.md) — лёгкое управление, guardrails, paved road.
- [12.5. Build vs Buy](./12-processy-organizaciya-lyudi/12-05-build-vs-buy.md) — строй своё конкурентное преимущество, бери готовое для остального.
- [12.6. Лидерство и менторство](./12-processy-organizaciya-lyudi/12-06-liderstvo-mentorstvo.md) — влияние без власти; выращивание команды.

### Модуль 13. Бизнес и стратегия
Архитектура на уровне бизнеса.

- [13.1. Связь с бизнес-целями](./13-biznes-strategiya/13-01-svyaz-s-biznes-celyami.md) — архитектура служит бизнесу; стадия меняет приоритеты.
- [13.2. TCO и ROI](./13-biznes-strategiya/13-02-tco-roi.md) — экономическое обоснование решений; язык денег.
- [13.3. Enterprise Architecture (TOGAF, Zachman)](./13-biznes-strategiya/13-03-ea-togaf-zachman.md) — архитектура предприятия; риск бюрократии.
- [13.4. Отраслевая специфика](./13-biznes-strategiya/13-04-otraslevaya-specifika.md) — приоритеты по отраслям; нет универсально правильной архитектуры.

### Модуль 14. Современные направления
Актуальные направления как эволюция фундаментальных принципов.

- [14.1. Platform Engineering](./14-sovremennye-napravleniya/14-01-platform-engineering.md) — внутренняя платформа (IDP) как продукт; самообслуживание.
- [14.2. Data Mesh](./14-sovremennye-napravleniya/14-02-data-mesh.md) — децентрализация данных; четыре принципа.
- [14.3. Архитектура ML/AI/LLM](./14-sovremennye-napravleniya/14-03-ml-ai-llm.md) — данные, обучение/инференс, дрейф, RAG, не доверяй слепо.
- [14.4. Real-time: доставка данных пользователю](./14-sovremennye-napravleniya/14-04-realtime-streaming.md) — опрос vs push, SSE и WebSocket, fan-out, состояние соединений.

### Модуль 15. Capstone (синтез)
Собираем всё воедино.

- [15.1. Сквозной кейс: от вопроса заказчика к архитектуре](./15-capstone/15-01-skvoznye-keysy.md) — порядок снятия неопределённости; конфликты требований и их цена.
- [15.2. Архитектурные каты](./15-capstone/15-02-arhitekturnye-katy.md) — тренировка мышления практикой.
- [15.3. Подготовка к собеседованиям](./15-capstone/15-03-podgotovka-k-sobesedovaniyam.md) — system design интервью; структура ответа.
- [15.4. Как расти дальше](./15-capstone/15-04-kak-rasti-dalshe.md) — непрерывное обучение; что унести из учебника.

### Модуль 16. Справочник
Материалы для быстрого обращения.

- [16.1. Оценки на салфетке](./16-spravochnik/16-01-ocenki-na-salfetke.md) — числа, которые стоит помнить; задержки, доступность, закон Литтла, стоимость.
- [16.2. Глоссарий](./16-spravochnik/16-02-glossariy.md) — термины с английскими оригиналами и ссылками на главы.

---

## Структура репозитория

```
.
├── README.md
├── 00-professiya/
├── 01-atributy-kachestva/
├── 02-stili/
├── 03-dekompoziciya-ddd/
├── 04-raspredelennye-sistemy/
├── 05-dannye/
├── 06-vzaimodeystvie-api/
├── 07-bezopasnost/
├── 08-nadezhnost-nablyudaemost-proizvoditelnost/
├── 09-cloud-native-infrastruktura-dostavka/
├── 10-dokumentaciya-kommunikaciya/
├── 11-ocenka-evolyuciya/
├── 12-processy-organizaciya-lyudi/
├── 13-biznes-strategiya/
├── 14-sovremennye-napravleniya/
├── 15-capstone/
└── 16-spravochnik/
```

Каждая папка модуля содержит `README.md` с оглавлением модуля и главы вида `NN-MM-slug.md` (NN — номер модуля, MM — номер главы).

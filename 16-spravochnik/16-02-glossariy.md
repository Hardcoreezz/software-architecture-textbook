# Глава 16.2. Глоссарий: термины и их английские оригиналы

> Модуль 16. Справочник
> Уровень: Middle/Senior → подготовка к роли архитектора

---

Профессиональный разговор об архитектуре ведётся на смеси русского и английского: документация, книги и собеседования — почти всегда на английском, а обсуждение в команде — на русском. Поэтому здесь для каждого термина дан английский оригинал и ссылка на главу, где он разобран по-настоящему. Определения намеренно короткие: это указатель, а не учебник.

Термины сгруппированы по темам, внутри группы — по алфавиту.

---

## Профессия и мышление

- **Архитектура** (*software architecture*) — набор значимых решений о структуре системы, дорогих в отмене. → [0.1](../00-professiya/00-01-chto-takoe-arhitektura.md)
- **Большой ком грязи** (*big ball of mud*) — система без различимых границ, где связано всё со всем. → [0.1](../00-professiya/00-01-chto-takoe-arhitektura.md)
- **Высота абстракции** (*altitude*) — уровень, на котором работает архитектор: от кода до ландшафта предприятия. → [0.2](../00-professiya/00-02-rol-i-tipy-arhitektorov.md)
- **Двусторонняя дверь** (*two-way door*) — легко обратимое решение; принимается быстро и локально. → [0.1](../00-professiya/00-01-chto-takoe-arhitektura.md)
- **Злая задача** (*wicked problem*) — задача, условия которой проясняются только в процессе решения. → [0.4](../00-professiya/00-04-arhitekturnoe-myshlenie.md)
- **Односторонняя дверь** (*one-way door*) — решение, откат которого дорог или невозможен. → [0.1](../00-professiya/00-01-chto-takoe-arhitektura.md)
- **Последний ответственный момент** (*last responsible moment*) — принцип откладывать решение до момента, когда дальше откладывать дороже. → [0.3](../00-professiya/00-03-obyazannosti-i-mify.md)
- **Проектирование от рисков** (*risk-driven design*) — вкладывать проектное усилие туда, где риск выше. → [0.3](../00-professiya/00-03-obyazannosti-i-mify.md)
- **Резюме-ориентированная разработка** (*resume-driven development*) — выбор технологии ради портфолио, а не задачи. → [0.1](../00-professiya/00-01-chto-takoe-arhitektura.md)
- **Башня из слоновой кости** (*ivory tower architecture*) — архитектура, оторванная от реальности эксплуатации и команды. → [0.1](../00-professiya/00-01-chto-takoe-arhitektura.md)

## Требования и атрибуты качества

- **Архитектурно значимое требование** (*ASR, architecturally significant requirement*) — требование, определяющее структуру системы. → [1.3](../01-atributy-kachestva/01-03-asr-i-kak-ih-vytaskivat.md)
- **Атрибут качества** (*quality attribute*) — измеримое свойство системы: доступность, масштабируемость, сопровождаемость. → [1.2](../01-atributy-kachestva/01-02-katalog-atributov-kachestva.md)
- **Дерево полезности** (*utility tree*) — приоритизированное дерево атрибутов и сценариев. → [11.1](../11-ocenka-evolyuciya/11-01-ocenka-atam.md)
- **Ограничение** (*constraint*) — рамка, которая не обсуждается: регуляторика, бюджет, существующие системы. → [1.1](../01-atributy-kachestva/01-01-funkcionalnye-vs-nefunkcionalnye.md)
- **Сценарий качества** (*quality attribute scenario*) — проверяемая формулировка: источник, стимул, среда, артефакт, отклик, мера. → [1.4](../01-atributy-kachestva/01-04-scenarii-kachestva.md)
- **Точка компромисса** (*tradeoff point*) — решение, влияющее на несколько атрибутов в разные стороны. → [1.5](../01-atributy-kachestva/01-05-upravlenie-kompromissami.md)
- **Точка чувствительности** (*sensitivity point*) — решение, от которого сильно зависит один атрибут. → [1.5](../01-atributy-kachestva/01-05-upravlenie-kompromissami.md)

## Архитектурные стили

- **Гексагональная архитектура, порты и адаптеры** (*hexagonal, ports and adapters*) — домен в центре, инфраструктура — через порты. → [2.2](../02-stili/02-02-sloistaya-lukovichnaya-geksagonalnaya-clean.md)
- **Инверсия зависимостей** (*dependency inversion*) — зависимость направлена на абстракцию, а не на реализацию. → [2.2](../02-stili/02-02-sloistaya-lukovichnaya-geksagonalnaya-clean.md)
- **Микроядро, архитектура плагинов** (*microkernel, plugin architecture*) — минимальное ядро плюс подключаемые расширения. → [2.5](../02-stili/02-05-microkernel-spacebased-pipeline.md)
- **Микросервисная премия** (*microservice premium*) — постоянная плата сложностью за переход к сервисам. → [2.3](../02-stili/02-03-mikroservisy-i-soa.md)
- **Модульный монолит** (*modular monolith*) — единица развёртывания одна, границы модулей внутри строгие. → [2.1](../02-stili/02-01-monolit-i-modulnyy-monolit.md)
- **Распределённый монолит** (*distributed monolith*) — сервисы разделены физически, но обязаны выкатываться вместе. → [2.3](../02-stili/02-03-mikroservisy-i-soa.md)
- **Событийно-ориентированная архитектура** (*EDA, event-driven architecture*) — взаимодействие через факты о произошедшем. → [2.4](../02-stili/02-04-event-driven-architecture.md)
- **Хореография и оркестрация** (*choreography, orchestration*) — децентрализованное и централизованное управление процессом. → [2.4](../02-stili/02-04-event-driven-architecture.md)
- **Холодный старт** (*cold start*) — задержка первого вызова функции после простоя. → [2.6](../02-stili/02-06-serverless.md)
- **Bespoke-масштаб на пространстве** (*space-based architecture*) — общая сетка данных в памяти вместо общей БД. → [2.5](../02-stili/02-05-microkernel-spacebased-pipeline.md)
- **FaaS / BaaS** (*function/backend as a service*) — функции и готовые серверные сервисы как единицы. → [2.6](../02-stili/02-06-serverless.md)

## Декомпозиция и DDD

- **Агрегат** (*aggregate*) — граница согласованности: кластер объектов, меняемый как целое. → [3.4](../03-dekompoziciya-ddd/03-04-ddd-takticheskiy.md)
- **Анемичная модель** (*anemic domain model*) — объекты без поведения, логика вынесена в сервисы. → [3.4](../03-dekompoziciya-ddd/03-04-ddd-takticheskiy.md)
- **Единый язык** (*ubiquitous language*) — общий словарь бизнеса и разработки внутри контекста. → [3.3](../03-dekompoziciya-ddd/03-03-ddd-strategicheskiy.md)
- **Информационная скрытость** (*information hiding*) — прятать за границей то, что может измениться (Парнас). → [3.2](../03-dekompoziciya-ddd/03-02-principy-dekompozicii.md)
- **Карта контекстов** (*context map*) — схема отношений между ограниченными контекстами. → [3.3](../03-dekompoziciya-ddd/03-03-ddd-strategicheskiy.md)
- **Коннасенс** (*connascence*) — вид и сила связи между элементами; измеряет связанность точнее. → [3.1](../03-dekompoziciya-ddd/03-01-svyazannost-sceplenie-connascence.md)
- **Объект-значение** (*value object*) — объект без идентичности, равный по значению. → [3.4](../03-dekompoziciya-ddd/03-04-ddd-takticheskiy.md)
- **Ограниченный контекст** (*bounded context*) — граница, внутри которой термины имеют одно значение. → [3.3](../03-dekompoziciya-ddd/03-03-ddd-strategicheskiy.md)
- **Предохранительный слой** (*ACL, anti-corruption layer*) — переводчик между контекстами, защищающий модель. → [3.3](../03-dekompoziciya-ddd/03-03-ddd-strategicheskiy.md)
- **Связанность и сцепление** (*coupling, cohesion*) — сила связи между модулями и внутри модуля. → [3.1](../03-dekompoziciya-ddd/03-01-svyazannost-sceplenie-connascence.md)
- **Событийный штурм** (*EventStorming*) — совместная практика поиска границ через события домена. → [3.3](../03-dekompoziciya-ddd/03-03-ddd-strategicheskiy.md)
- **Ядровый домен** (*core domain*) — часть, дающая конкурентное преимущество; сюда вкладывают лучших. → [3.3](../03-dekompoziciya-ddd/03-03-ddd-strategicheskiy.md)

## Распределённые системы

- **Восемь заблуждений** (*fallacies of distributed computing*) — ложные допущения о надёжности и однородности сети. → [4.1](../04-raspredelennye-sistemy/04-01-zabluzhdeniya-i-setevye-osnovy.md)
- **Идемпотентность** (*idempotency*) — повторное применение операции не меняет результат. → [4.5](../04-raspredelennye-sistemy/04-05-raspredelennye-tranzakcii-saga.md)
- **Кворум** (*quorum*) — большинство узлов, необходимое для принятия решения. → [4.3](../04-raspredelennye-sistemy/04-03-konsensus-raft-paxos.md)
- **Компенсация** (*compensating transaction*) — семантическая отмена уже выполненного шага саги. → [4.5](../04-raspredelennye-sistemy/04-05-raspredelennye-tranzakcii-saga.md)
- **Консенсус** (*consensus*) — согласие узлов о значении при отказах и ненадёжной сети. → [4.3](../04-raspredelennye-sistemy/04-03-konsensus-raft-paxos.md)
- **Обратное давление** (*backpressure*) — сигнал источнику замедлиться вместо накопления и падения. → [4.4](../04-raspredelennye-sistemy/04-04-patterny-ustoychivosti.md)
- **Переборка** (*bulkhead*) — изоляция ресурсов, чтобы отказ одной части не утопил остальные. → [4.4](../04-raspredelennye-sistemy/04-04-patterny-ustoychivosti.md)
- **Разделение мозга** (*split-brain*) — две части кластера считают себя главными. → [4.3](../04-raspredelennye-sistemy/04-03-konsensus-raft-paxos.md)
- **Размыкатель цепи** (*circuit breaker*) — временное прекращение вызовов к отказавшей зависимости. → [4.4](../04-raspredelennye-sistemy/04-04-patterny-ustoychivosti.md)
- **Разброс задержки** (*jitter*) — случайная добавка к паузе, разводящая одновременные повторы. → [4.4](../04-raspredelennye-sistemy/04-04-patterny-ustoychivosti.md)
- **Сага** (*saga*) — последовательность локальных транзакций с компенсациями вместо распределённой ACID. → [4.5](../04-raspredelennye-sistemy/04-05-raspredelennye-tranzakcii-saga.md)
- **Согласованность в конечном счёте** (*eventual consistency*) — реплики сойдутся, если прекратить запись. → [4.2](../04-raspredelennye-sistemy/04-02-cap-pacelc-modeli-soglasovannosti.md)
- **Транзакционный ящик** (*transactional outbox*) — запись события в одной транзакции с данными для надёжной публикации. → [4.5](../04-raspredelennye-sistemy/04-05-raspredelennye-tranzakcii-saga.md)
- **Частичный отказ** (*partial failure*) — часть системы недоступна, часть работает; определяющая проблема распределёнки. → [4.1](../04-raspredelennye-sistemy/04-01-zabluzhdeniya-i-setevye-osnovy.md)
- **Шторм повторов** (*retry storm*) — лавина повторов, добивающая уже перегруженный сервис. → [4.4](../04-raspredelennye-sistemy/04-04-patterny-ustoychivosti.md)
- **CAP / PACELC** — компромисс согласованности и доступности при разделении сети и задержки в его отсутствие. → [4.2](../04-raspredelennye-sistemy/04-02-cap-pacelc-modeli-soglasovannosti.md)

## Данные

- **Захват изменений** (*CDC, change data capture*) — поток изменений БД как источник событий. → [5.5](../05-dannye/05-05-batch-stream-konveery.md)
- **Инвалидация кэша** (*cache invalidation*) — согласование кэша с источником истины. → [5.4](../05-dannye/05-04-strategii-keshirovaniya.md)
- **Источник истины** (*source of truth*) — хранилище, которое считается авторитетным для данных. → [5.2](../05-dannye/05-02-polyglot-persistence.md)
- **Лавина запросов к источнику** (*cache stampede*) — одновременный промах многих клиентов после истечения записи. → [5.4](../05-dannye/05-04-strategii-keshirovaniya.md)
- **Мультитенантность** (*multi-tenancy*) — обслуживание нескольких арендаторов одной системой. → [5.7](../05-dannye/05-07-multitenantnost.md)
- **Полиглотное хранение** (*polyglot persistence*) — разные типы хранилищ под разные задачи. → [5.2](../05-dannye/05-02-polyglot-persistence.md)
- **Проекция** (*projection, read model*) — производное представление данных под конкретное чтение. → [5.3](../05-dannye/05-03-event-sourcing-cqrs.md)
- **Разделение команд и запросов** (*CQRS*) — разные модели для записи и для чтения. → [5.3](../05-dannye/05-03-event-sourcing-cqrs.md)
- **Событийное хранение** (*event sourcing*) — состояние как свёртка неизменяемой последовательности событий. → [5.3](../05-dannye/05-03-event-sourcing-cqrs.md)
- **Шумный сосед** (*noisy neighbour*) — арендатор, который своей нагрузкой портит работу остальным. → [5.7](../05-dannye/05-07-multitenantnost.md)
- **Silo / pool / bridge** — выделенная, общая и промежуточная модель изоляции арендаторов. → [5.7](../05-dannye/05-07-multitenantnost.md)
- **Строковая политика доступа** (*row-level security*) — изоляция строк на уровне СУБД, а не кода. → [5.7](../05-dannye/05-07-multitenantnost.md)
- **Умные конечные точки, тупые трубы** (*smart endpoints, dumb pipes*) — логика в сервисах, а не в шине. → [5.6](../05-dannye/05-06-patterny-integracii-eip.md)
- **Cache-aside** — приложение само читает кэш и заполняет его при промахе. → [5.4](../05-dannye/05-04-strategii-keshirovaniya.md)
- **Lambda / Kappa** — двухпутевая (batch + stream) и однопутевая архитектуры обработки. → [5.5](../05-dannye/05-05-batch-stream-konveery.md)

## Взаимодействие и API

- **Временная связанность** (*temporal coupling*) — вызывающий и вызываемый обязаны быть доступны одновременно. → [6.1](../06-vzaimodeystvie-api/06-01-sinhronnoe-vs-asinhronnoe.md)
- **Журнал событий** (*event log*) — упорядоченная сохраняемая последовательность с возможностью перечитывания. → [6.3](../06-vzaimodeystvie-api/06-03-ocheredi-brokery-streaming-kafka.md)
- **Мёртвая очередь** (*dead letter queue*) — место для сообщений, которые не удалось обработать. → [6.3](../06-vzaimodeystvie-api/06-03-ocheredi-brokery-streaming-kafka.md)
- **Сервисная сетка** (*service mesh*) — инфраструктурный слой межсервисной связи: mTLS, повторы, наблюдаемость. → [6.5](../06-vzaimodeystvie-api/06-05-api-gateway-bff-service-mesh.md)
- **Толерантный читатель** (*tolerant reader*) — потребитель игнорирует незнакомые поля, не ломаясь на них. → [6.4](../06-vzaimodeystvie-api/06-04-proektirovanie-api-versionirovanie.md)
- **Шлюз API** (*API gateway*) — единая точка входа: маршрутизация, аутентификация, лимиты. → [6.5](../06-vzaimodeystvie-api/06-05-api-gateway-bff-service-mesh.md)
- **Аддитивная эволюция** (*additive change*) — расширять контракт, не ломая существующих потребителей. → [6.4](../06-vzaimodeystvie-api/06-04-proektirovanie-api-versionirovanie.md)
- **BFF** (*backend for frontend*) — отдельный бэкенд под нужды конкретного клиента. → [6.5](../06-vzaimodeystvie-api/06-05-api-gateway-bff-service-mesh.md)
- **Гарантии доставки** (*at-most-once, at-least-once, exactly-once*) — что обещает транспорт при сбоях. → [6.3](../06-vzaimodeystvie-api/06-03-ocheredi-brokery-streaming-kafka.md)

## Real-time и доставка данных

- **Веерная рассылка** (*fan-out*) — доставка одного события многим получателям; on write или on read. → [14.4](../14-sovremennye-napravleniya/14-04-realtime-streaming.md)
- **Длинный опрос** (*long polling*) — сервер удерживает запрос до появления события. → [14.4](../14-sovremennye-napravleniya/14-04-realtime-streaming.md)
- **Опрос** (*polling*) — периодический запрос клиента «что нового». → [14.4](../14-sovremennye-napravleniya/14-04-realtime-streaming.md)
- **Схлопывание обновлений** (*coalescing*) — хранить последнее состояние вместо очереди промежуточных. → [14.4](../14-sovremennye-napravleniya/14-04-realtime-streaming.md)
- **Событийный поток от сервера** (*SSE, server-sent events*) — однонаправленный push поверх HTTP. → [14.4](../14-sovremennye-napravleniya/14-04-realtime-streaming.md)
- **Webhook** — push-уведомление между системами по HTTP. → [14.4](../14-sovremennye-napravleniya/14-04-realtime-streaming.md)
- **WebSocket** — полнодуплексный канал поверх одного соединения. → [14.4](../14-sovremennye-napravleniya/14-04-realtime-streaming.md)

## Безопасность

- **Авторизация объекта** (*object-level authorization*) — проверка права на конкретную сущность, а не только роли. → [7.2](../07-bezopasnost/07-02-autentifikaciya-avtorizaciya.md)
- **Аутентификация и авторизация** (*authentication, authorization*) — «кто ты» и «что тебе можно». → [7.2](../07-bezopasnost/07-02-autentifikaciya-avtorizaciya.md)
- **Граница доверия** (*trust boundary*) — рубеж, на котором данные перестают считаться проверенными. → [7.1](../07-bezopasnost/07-01-modelirovanie-ugroz-stride.md)
- **Минимум привилегий** (*least privilege*) — ровно те права, что нужны для задачи, и не больше. → [7.3](../07-bezopasnost/07-03-zero-trust.md)
- **Моделирование угроз** (*threat modelling*) — систематический поиск угроз по потокам данных. → [7.1](../07-bezopasnost/07-01-modelirovanie-ugroz-stride.md)
- **Нулевое доверие** (*zero trust*) — сеть не даёт доверия; проверяется каждый запрос. → [7.3](../07-bezopasnost/07-03-zero-trust.md)
- **Радиус поражения** (*blast radius*) — объём ущерба при компрометации одного элемента. → [7.3](../07-bezopasnost/07-03-zero-trust.md)
- **Сдвиг влево** (*shift left*) — переносить проверки безопасности на ранние стадии. → [7.5](../07-bezopasnost/07-05-secure-by-design-supply-chain.md)
- **Цепочка поставок** (*supply chain security*) — риски зависимостей, сборки и артефактов. → [7.5](../07-bezopasnost/07-05-secure-by-design-supply-chain.md)
- **IDOR** (*insecure direct object reference*) — доступ к чужому объекту по угаданному идентификатору. → [7.2](../07-bezopasnost/07-02-autentifikaciya-avtorizaciya.md)
- **OAuth2 / OIDC** — делегирование доступа и аутентификация поверх него. → [7.2](../07-bezopasnost/07-02-autentifikaciya-avtorizaciya.md)
- **RBAC / ABAC** — контроль доступа по ролям и по атрибутам. → [7.2](../07-bezopasnost/07-02-autentifikaciya-avtorizaciya.md)
- **SBOM / SCA** — состав зависимостей и анализ их уязвимостей. → [7.5](../07-bezopasnost/07-05-secure-by-design-supply-chain.md)
- **STRIDE** — шесть категорий угроз: подмена, подделка, отказ от авторства, раскрытие, отказ в обслуживании, повышение прав. → [7.1](../07-bezopasnost/07-01-modelirovanie-ugroz-stride.md)

## Надёжность, наблюдаемость, производительность

- **Бюджет ошибок** (*error budget*) — допустимая доля нарушений SLO; валюта риска. → [8.1](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-01-sli-slo-sla-error-budget.md)
- **Золотые сигналы** (*four golden signals*) — задержка, трафик, ошибки, насыщение. → [8.2](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-02-logi-metriki-trasing.md)
- **Наблюдаемость** (*observability*) — возможность понять внутреннее состояние по внешним сигналам. → [8.2](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-02-logi-metriki-trasing.md)
- **Постмортем без обвинений** (*blameless postmortem*) — разбор инцидента, направленный на систему, а не на людей. → [8.3](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-03-sre-praktiki.md)
- **Распределённая трассировка** (*distributed tracing*) — сшивание пути одного запроса через сервисы. → [8.2](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-02-logi-metriki-trasing.md)
- **Рутина** (*toil*) — повторяющаяся ручная работа без долгосрочной ценности; цель автоматизации. → [8.3](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-03-sre-praktiki.md)
- **Узкое место** (*bottleneck*) — ресурс, ограничивающий пропускную способность всей системы. → [8.4](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-04-proizvoditelnost-profilirovanie.md)
- **Хвостовая задержка** (*tail latency*, p99) — время ответа для худших процентов запросов. → [8.4](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-04-proizvoditelnost-profilirovanie.md)
- **Ёмкость** (*capacity planning*) — расчёт ресурсов под ожидаемую нагрузку и пик. → [8.5](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-05-emkost-i-masshtabirovanie.md)
- **RTO / RPO** — допустимое время восстановления и допустимая потеря данных. → [8.6](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-06-otkazoustojchivost-dr.md)
- **SLI / SLO / SLA** — измеряемый индикатор, внутренняя цель, внешнее обязательство. → [8.1](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-01-sli-slo-sla-error-budget.md)
- **Закон Литтла** (*Little's law*) — одновременных запросов = интенсивность × время ответа. → [16.1](16-01-ocenki-na-salfetke.md)

## Cloud-native, инфраструктура, доставка

- **Двенадцать факторов** (*twelve-factor app*) — набор свойств приложения, пригодного для облака. → [9.1](../09-cloud-native-infrastruktura-dostavka/09-01-12-factor-cloud-native.md)
- **Инфраструктура как код** (*IaC*) — декларативное описание инфраструктуры, версионируемое как код. → [9.3](../09-cloud-native-infrastruktura-dostavka/09-03-iac.md)
- **Канареечный выкат** (*canary release*) — постепенный перевод трафика с наблюдением за метриками. → [9.4](../09-cloud-native-infrastruktura-dostavka/09-04-ci-cd-deployment-strategii.md)
- **Контрактный тест** (*contract test*) — проверка ожиданий потребителя в пайплайне поставщика. → [9.6](../09-cloud-native-infrastruktura-dostavka/09-06-strategiya-testirovaniya.md)
- **Неизменяемая инфраструктура** (*immutable infrastructure*) — сервер не правят, а пересоздают из образа. → [9.3](../09-cloud-native-infrastruktura-dostavka/09-03-iac.md)
- **Пирамида тестов** (*test pyramid*) — распределение проверок по уровням: много быстрых, мало сквозных. → [9.6](../09-cloud-native-infrastruktura-dostavka/09-06-strategiya-testirovaniya.md)
- **Синий-зелёный выкат** (*blue-green deployment*) — переключение трафика между двумя полными средами. → [9.4](../09-cloud-native-infrastruktura-dostavka/09-04-ci-cd-deployment-strategii.md)
- **Флаг функциональности** (*feature flag*) — отделение выката кода от включения поведения. → [9.4](../09-cloud-native-infrastruktura-dostavka/09-04-ci-cd-deployment-strategii.md)
- **Флакующий тест** (*flaky test*) — тест, падающий недетерминированно; разрушает доверие к сборке. → [9.6](../09-cloud-native-infrastruktura-dostavka/09-06-strategiya-testirovaniya.md)
- **Хаос-инжиниринг** (*chaos engineering*) — намеренное внесение отказов для проверки устойчивости. → [9.6](../09-cloud-native-infrastruktura-dostavka/09-06-strategiya-testirovaniya.md)
- **FinOps** — практика управления облачными расходами как атрибутом качества. → [9.5](../09-cloud-native-infrastruktura-dostavka/09-05-stoimost-finops.md)

## Документация и коммуникация

- **Диаграмма как код** (*diagrams as code*) — диаграммы в текстовом виде, версионируемые рядом с кодом. → [10.1](../10-dokumentaciya-kommunikaciya/10-01-c4-model.md)
- **Запись архитектурного решения** (*ADR, architecture decision record*) — решение с контекстом, альтернативами и последствиями. → [10.3](../10-dokumentaciya-kommunikaciya/10-03-adr.md)
- **Модель C4** — четыре уровня масштаба: контекст, контейнеры, компоненты, код. → [10.1](../10-dokumentaciya-kommunikaciya/10-01-c4-model.md)
- **Влияние без полномочий** (*influence without authority*) — проведение решений убеждением, а не властью. → [10.5](../10-dokumentaciya-kommunikaciya/10-05-kommunikaciya-so-stejkholderami.md)
- **arc42 / 4+1** — шаблон архитектурного документа и набор точек зрения. → [10.2](../10-dokumentaciya-kommunikaciya/10-02-arc42-4plus1.md)

## Оценка и эволюция

- **Душитель** (*strangler fig*) — постепенное замещение легаси с перехватом трафика. → [11.4](../11-ocenka-evolyuciya/11-04-legasi-strangler-fig.md)
- **Технический долг** (*technical debt*) — отложенная работа, за которую платят замедлением. → [11.3](../11-ocenka-evolyuciya/11-03-tehdolg.md)
- **Функция пригодности** (*fitness function*) — автопроверка архитектурного свойства в пайплайне. → [11.2](../11-ocenka-evolyuciya/11-02-evolyucionnaya-arhitektura.md)
- **Эрозия архитектуры** (*architectural drift, erosion*) — расхождение реальной структуры с задуманной. → [11.2](../11-ocenka-evolyuciya/11-02-evolyucionnaya-arhitektura.md)
- **ATAM** (*architecture tradeoff analysis method*) — оценка архитектуры против сценариев качества. → [11.1](../11-ocenka-evolyuciya/11-01-ocenka-atam.md)

## Организация и процессы

- **Закон Конвея** (*Conway's law*) — структура системы повторяет структуру коммуникации организации. → [12.1](../12-processy-organizaciya-lyudi/12-01-zakon-konveya.md)
- **Когнитивная нагрузка** (*cognitive load*) — объём, который команда способна удерживать; ограничивает размер куска. → [12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)
- **Обратный манёвр Конвея** (*inverse Conway manoeuvre*) — менять оргструктуру ради желаемой архитектуры. → [12.1](../12-processy-organizaciya-lyudi/12-01-zakon-konveya.md)
- **Ограждения** (*guardrails*) — рамки, внутри которых команды свободны. → [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)
- **Проторённый путь** (*paved road*) — стандартный вариант, который проще всех остальных. → [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)
- **Строить или купить** (*build vs buy*) — строить дифференциатор, брать готовое для остального. → [12.5](../12-processy-organizaciya-lyudi/12-05-build-vs-buy.md)
- **Типы команд** (*stream-aligned, platform, enabling, complicated-subsystem*) — четыре роли команд в Team Topologies. → [12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)
- **Ходячий скелет** (*walking skeleton*) — тонкая сквозная реализация всего пути для ранней проверки. → [12.3](../12-processy-organizaciya-lyudi/12-03-agile-riski.md)
- **BDUF** (*big design up front*) — попытка спроектировать всё заранее. → [12.3](../12-processy-organizaciya-lyudi/12-03-agile-riski.md)

## Бизнес и стратегия

- **Архитектура предприятия** (*EA, enterprise architecture*) — согласование всего ландшафта организации со стратегией. → [13.3](../13-biznes-strategiya/13-03-ea-togaf-zachman.md)
- **Возврат инвестиций** (*ROI*) — что решение приносит относительно затрат. → [13.2](../13-biznes-strategiya/13-02-tco-roi.md)
- **Привязка к поставщику** (*vendor lock-in*) — стоимость смены поставщика как фактор решения. → [12.5](../12-processy-organizaciya-lyudi/12-05-build-vs-buy.md)
- **Совокупная стоимость владения** (*TCO*) — все затраты за жизненный цикл, а не только начальные. → [13.2](../13-biznes-strategiya/13-02-tco-roi.md)
- **TOGAF / Zachman** — процессная рамка и таксономия артефактов в архитектуре предприятия. → [13.3](../13-biznes-strategiya/13-03-ea-togaf-zachman.md)

## Современные направления

- **Внутренняя платформа** (*IDP, internal developer platform*) — самообслуживание для команд разработки. → [14.1](../14-sovremennye-napravleniya/14-01-platform-engineering.md)
- **Дрейф модели** (*model drift*) — деградация качества модели из-за изменения данных. → [14.3](../14-sovremennye-napravleniya/14-03-ml-ai-llm.md)
- **Инъекция в промпт** (*prompt injection*) — подмена инструкции модели через входные данные. → [14.3](../14-sovremennye-napravleniya/14-03-ml-ai-llm.md)
- **Данные как продукт** (*data as a product*) — домен отвечает за свои данные как за продукт с потребителями. → [14.2](../14-sovremennye-napravleniya/14-02-data-mesh.md)
- **Сетка данных** (*data mesh*) — децентрализация владения данными по доменам. → [14.2](../14-sovremennye-napravleniya/14-02-data-mesh.md)
- **RAG** (*retrieval-augmented generation*) — подмешивание найденного контекста в запрос к модели. → [14.3](../14-sovremennye-napravleniya/14-03-ml-ai-llm.md)
- **MLOps** — эксплуатация ML: версионирование данных и моделей, мониторинг качества, переобучение. → [14.3](../14-sovremennye-napravleniya/14-03-ml-ai-llm.md)

<!-- related -->

---

## Связанные главы

**Опирается на:**
- [14.4. Real-time: доставка данных пользователю](../14-sovremennye-napravleniya/14-04-realtime-streaming.md) — опрос vs push, SSE и WebSocket, fan-out, состояние соединений.
- [0.1. Что такое архитектура](../00-professiya/00-01-chto-takoe-arhitektura.md) — что относится к архитектуре, а что нет; значимые решения и их цена.
- [3.3. DDD стратегический](../03-dekompoziciya-ddd/03-03-ddd-strategicheskiy.md) — bounded context, context mapping, ACL, EventStorming.
- [4.4. Паттерны устойчивости](../04-raspredelennye-sistemy/04-04-patterny-ustoychivosti.md) — таймауты, retry+backoff+jitter, circuit breaker, bulkhead, backpressure, деградация.
- [7.2. Аутентификация и авторизация](../07-bezopasnost/07-02-autentifikaciya-avtorizaciya.md) — AuthN ≠ AuthZ; авторизация объекта против IDOR; не изобретай auth.

<!-- nav -->

---

| Назад | Вверх | Вперёд |
|:---|:---:|---:|
| ← [16.1. Оценки на салфетке](16-01-ocenki-na-salfetke.md) | [Модуль 16](README.md) · [Оглавление](../README.md) | — |

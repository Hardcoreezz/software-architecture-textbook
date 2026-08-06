# Глава 14.1. Platform Engineering

> Модуль 14. Современные направления
> Уровень: Middle/Senior → подготовка к роли архитектора

---

## 1. Зачем это нужно

[Модуль 12](../12-processy-organizaciya-lyudi/README.md) ввёл platform-команды ([12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md) — инфраструктура как самообслуживание, снижающая когнитивную нагрузку), а [Модуль 9](../09-cloud-native-infrastruktura-dostavka/README.md) — cloud-native инфраструктуру (контейнеры [9.2](../09-cloud-native-infrastruktura-dostavka/09-02-konteynery-i-orkestraciya.md), IaC [9.3](../09-cloud-native-infrastruktura-dostavka/09-03-iac.md), CI/CD [9.4](../09-cloud-native-infrastruktura-dostavka/09-04-ci-cd-deployment-strategii.md)). **Platform Engineering** — современное направление, оформляющее это в дисциплину: построение *внутренней платформы* (Internal Developer Platform, IDP), которая даёт командам разработки самообслуживание для всего, что им нужно (развёртывание, инфраструктура, наблюдаемость), скрывая сложность. Это ответ на проблему: автономные stream-aligned команды тонут в инфраструктурной сложности (Kubernetes [9.2](../09-cloud-native-infrastruktura-dostavka/09-02-konteynery-i-orkestraciya.md), облако, CI/CD) — платформа берёт это на себя, давая «paved road» ([12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)) как продукт.

Глава открывает [Модуль 14](README.md) (современные направления). Platform Engineering — эволюция DevOps/инфраструктуры в сторону платформы-как-продукта. Прямое продолжение: platform-команды, paved road, cloud-native (М9), когнитивная нагрузка. Как современное направление — даётся с оговоркой, что это развивающаяся практика, не догма.

Установка: **platform engineering строит внутреннюю платформу (IDP) как продукт для команд разработки — самообслуживание для развёртывания/инфраструктуры/наблюдаемости, скрывающее сложность; цель — снизить когнитивную нагрузку команд и ускорить поток, относясь к платформе как к продукту, а не диктату.**

---

## 2. Теория

### 2.1. Проблема, которую решает platform engineering

Автономные команды ([12.1](../12-processy-organizaciya-lyudi/12-01-zakon-konveya.md), [12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)) должны владеть своими сервисами *целиком* ([3.5](../03-dekompoziciya-ddd/03-05-granicy-servisov-i-moduley.md)) — включая развёртывание ([9.4](../09-cloud-native-infrastruktura-dostavka/09-04-ci-cd-deployment-strategii.md)), инфраструктуру ([9.2](../09-cloud-native-infrastruktura-dostavka/09-02-konteynery-i-orkestraciya.md), [9.3](../09-cloud-native-infrastruktura-dostavka/09-03-iac.md)), наблюдаемость ([8.2](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-02-logi-metriki-trasing.md)). Но современная cloud-native инфраструктура *сложна*: Kubernetes, облако, CI/CD, IaC, mesh ([6.5](../06-vzaimodeystvie-api/06-05-api-gateway-bff-service-mesh.md)), наблюдаемость. Если *каждая* команда осваивает и настраивает всё это сама:
- *Когнитивная перегрузка*: команды тонут в инфраструктуре вместо бизнеса.
- *Дублирование:* каждая изобретает своё (как кейс [12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)).
- *Несогласованность:* зоопарк подходов ([12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)).

**Platform Engineering** решает это: специальная команда (platform team [12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)) строит *внутреннюю платформу*, которая предоставляет всё это как *самообслуживание* — команды разработки потребляют, не вникая в глубину. Это оформление platform-команды в дисциплину.

### 2.2. Internal Developer Platform (IDP)

**IDP (Internal Developer Platform)** — внутренняя платформа, дающая командам разработки *самообслуживание* для их нужд:
- *Развёртывание:* запустить сервис в прод без ручной возни с K8s / CI/CD.
- *Инфраструктура:* получить БД ([5.1](../05-dannye/05-01-vybor-hranilisch.md)), очередь ([6.3](../06-vzaimodeystvie-api/06-03-ocheredi-brokery-streaming-kafka.md)), кэш ([5.4](../05-dannye/05-04-strategii-keshirovaniya.md)) self-service, без настройки вручную.
- *Наблюдаемость*: метрики/логи/трейсы из коробки.
- *Стандарты*: безопасность ([Модуль 7](../07-bezopasnost/README.md)), наблюдаемость встроены (paved road [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)).

Команда разработки взаимодействует с IDP через *интерфейс самообслуживания* (портал, CLI, API, манифесты) — описывает, что нужно, платформа предоставляет. Сложность (K8s, облако, mesh) *скрыта* за платформой. Это X-as-a-Service на уровне инфраструктуры разработки.

### 2.3. Платформа как продукт

Ключевая идея (отличающая platform engineering от старой «инфраструктурной команды»): **платформа — это продукт, а её пользователи — команды разработки.** Следствия:
- *Product mindset:* платформа делается *для* разработчиков (developer experience — DX), с учётом их нужд, обратной связи, удобства — как внешний продукт для клиентов.
- *Самообслуживание, не тикеты:* разработчик получает нужное *сам* (self-service), не ждёт тикет к инфраструктурной команде (узкое место, как тяжёлый governance [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)).
- *Обслуживает, не диктует*: платформа *помогает* (paved road — самый лёгкий путь [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)), не *заставляет* («хочешь иначе — можно»). Не контроль-башня.
- *Опциональность paved road:* стандартный путь — самый лёгкий (поощрение, [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)), но не единственно возможный (автономия [12.1](../12-processy-organizaciya-lyudi/12-01-zakon-konveya.md), [12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)).

Это смещает культуру: платформа *служит* командам (как servant leadership [12.6](../12-processy-organizaciya-lyudi/12-06-liderstvo-mentorstvo.md), enablement [12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)), а не командует ими.

### 2.4. Что даёт и когда нужна

Что даёт IDP:
- *Снижение когнитивной нагрузки*: команды фокусируются на бизнесе, не на инфраструктуре.
- *Ускорение потока*: self-service быстрее тикетов; быстрый онбординг.
- *Согласованность*: стандарты (безопасность, наблюдаемость) встроены в платформу — governance через платформу, не комитет.
- *Меньше дублирования:* общее в платформе, не в каждой команде.

Когда нужна (по нужде, как всё):
- *Оправдана:* много команд/сервисов, сложная cloud-native инфраструктура, команды тонут в ней ([12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md) кейс). Тогда платформа окупается (снижает нагрузку многих).
- *Избыточна:* мало команд/сервисов, простая инфраструктура — строить IDP преждевременно (over-engineering, как преждевременный K8s [9.2](../09-cloud-native-infrastruktura-dostavka/09-02-konteynery-i-orkestraciya.md)). Managed-платформы или простота достаточны.

Платформа — *инвестиция* ([12.5](../12-processy-organizaciya-lyudi/12-05-build-vs-buy.md), [13.2](../13-biznes-strategiya/13-02-tco-roi.md)): окупается, когда снижение нагрузки многих команд превышает стоимость её построения/поддержки.

---

## 3. Подходы

**Подход 1.** Строй платформу, когда команды тонут в инфраструктурной сложности (§2.1, §2.4): много команд/сервисов, сложный cloud-native стек. Снижает когнитивную нагрузку ([12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)), ускоряет поток.

**Подход 2.** Делай IDP с самообслуживанием (§2.2): развёртывание, инфраструктура, наблюдаемость — self-service для команд, сложность (K8s [9.2](../09-cloud-native-infrastruktura-dostavka/09-02-konteynery-i-orkestraciya.md), облако) скрыта. X-as-a-Service.

**Подход 3.** Относись к платформе как к продукту (§2.3): пользователи — разработчики; product mindset, developer experience (DX), обратная связь. Не «инфраструктура как ей удобно».

**Подход 4.** Обслуживай, не диктуй ([12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)): платформа помогает (paved road — самый лёгкий путь [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)), не заставляет («хочешь иначе — можно»). Не контроль-башня, а servant ([12.6](../12-processy-organizaciya-lyudi/12-06-liderstvo-mentorstvo.md)).

**Подход 5.** Встраивай стандарты в платформу: безопасность ([Модуль 7](../07-bezopasnost/README.md)), наблюдаемость ([8.2](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-02-logi-metriki-trasing.md)) — из коробки на paved road; governance через платформу, не комитет.

**Подход 6.** Строй по нужде, не преждевременно: для немногих команд/простой инфраструктуры IDP — over-engineering (как K8s [9.2](../09-cloud-native-infrastruktura-dostavka/09-02-konteynery-i-orkestraciya.md)); managed-платформы или простота достаточны. Платформа — инвестиция ([12.5](../12-processy-organizaciya-lyudi/12-05-build-vs-buy.md), [13.2](../13-biznes-strategiya/13-02-tco-roi.md)), окупается при масштабе.

**Подход 7.** Избегай рисков: платформа-диктат (узкое место/башня), преждевременная платформа, платформа без DX. Продукт, обслуживающий, по нужде.

---

## 4. Пример: IDP и самообслуживание (концептуально)

```
# PLATFORM ENGINEERING: внутренняя платформа (IDP) как ПРОДУКТ для команд разработки (§2.2, §2.3).

# БЕЗ платформы (§2.1): каждая команда сама вникает в сложность → перегрузка (12.2), дублирование.
# Команда "Заказы" сама: настраивает K8s (9.2), CI/CD (9.4), IaC (9.3), наблюдаемость (8.2), безопасность (7.x)
#   → тонет в инфраструктуре вместо бизнеса (когнитивная перегрузка 12.2).

# С IDP (§2.2): самообслуживание, сложность СКРЫТА за платформой (X-as-a-Service 12.2).
# Разработчик описывает, ЧТО нужно (манифест/портал) — платформа предоставляет:
service-manifest:
  name: order-api
  needs:
    - database: postgres        # платформа выдаёт managed БД (5.1) self-service, не настраиваешь вручную
    - queue: kafka              # очередь (6.3) из коробки
  deploy: production            # платформа разворачивает (K8s 9.2, CI/CD 9.4 скрыты)
  # ВСТРОЕНО автоматически (paved road 12.4, подход 5):
  #   - наблюдаемость (8.2): метрики/логи/трейсы из коробки
  #   - безопасность (Модуль 7): mTLS (7.3), секреты (7.4), стандарты — встроены
  #   - стандарты соблюдены (governance через платформу 12.4, не комитет)

# Разработчик НЕ вникает в K8s/облако/mesh — фокус на БИЗНЕСЕ (когнитивная нагрузка снижена 12.2).

# ПЛАТФОРМА КАК ПРОДУКТ (§2.3): обслуживает, не диктует (12.4, подход 4).
# - self-service (не тикеты к инфра-команде → не узкое место)
# - developer experience (DX): удобно разработчику (product mindset)
# - paved road самый лёгкий (12.4), но "хочешь иначе — можно, сам отвечаешь" (автономия 12.1)

# ПО НУЖДЕ (§2.4, подход 6): IDP оправдан при МНОГИХ командах/сложной инфраструктуре;
#   для немногих — over-engineering (managed-платформы 9.2 достаточны). Инвестиция (12.5/13.2).
```

**Суть:** без платформы (§2.1) каждая команда сама вникает в сложность (K8s [9.2](../09-cloud-native-infrastruktura-dostavka/09-02-konteynery-i-orkestraciya.md), CI/CD [9.4](../09-cloud-native-infrastruktura-dostavka/09-04-ci-cd-deployment-strategii.md), IaC [9.3](../09-cloud-native-infrastruktura-dostavka/09-03-iac.md), наблюдаемость [8.2](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-02-logi-metriki-trasing.md), безопасность М7) — когнитивная перегрузка ([12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)), дублирование. IDP (§2.2) даёт *самообслуживание*: разработчик описывает, *что* нужно (манифест/портал — managed БД [5.1](../05-dannye/05-01-vybor-hranilisch.md), очередь [6.3](../06-vzaimodeystvie-api/06-03-ocheredi-brokery-streaming-kafka.md), развёртывание), платформа предоставляет, *скрывая* сложность; наблюдаемость и безопасность ([Модуль 7](../07-bezopasnost/README.md)) встроены (paved road [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md) — governance через платформу [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)). Разработчик фокусируется на бизнесе (когнитивная нагрузка снижена [12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)). Платформа — *продукт* (§2.3): self-service (не тикеты — не узкое место), DX, обслуживает не диктует (paved road самый лёгкий, но «иначе можно» — автономия [12.1](../12-processy-organizaciya-lyudi/12-01-zakon-konveya.md)). По нужде (§2.4): оправдан при многих командах, для немногих — over-engineering (managed [9.2](../09-cloud-native-infrastruktura-dostavka/09-02-konteynery-i-orkestraciya.md) достаточны).

---

## 5. Развёрнутый кейс: платформа для команд

Организация с многими автономными командами ([12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)) внедряла platform engineering.

**Проблема: команды тонут в инфраструктуре (§2.1, как кейс [12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)).** Stream-aligned команды владели сервисами целиком ([3.5](../03-dekompoziciya-ddd/03-05-granicy-servisov-i-moduley.md)), включая инфраструктуру. Но cloud-native стек был сложен (K8s [9.2](../09-cloud-native-infrastruktura-dostavka/09-02-konteynery-i-orkestraciya.md), облако, CI/CD [9.4](../09-cloud-native-infrastruktura-dostavka/09-04-ci-cd-deployment-strategii.md), IaC [9.3](../09-cloud-native-infrastruktura-dostavka/09-03-iac.md), наблюдаемость [8.2](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-02-logi-metriki-trasing.md), безопасность [М7](../07-bezopasnost/README.md)), и *каждая* команда осваивала/настраивала всё сама: когнитивная перегрузка ([12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md) — тонули в инфраструктуре вместо бизнеса), дублирование (каждая изобретала своё), несогласованность (зоопарк [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)), медленный онбординг.

**Решение: IDP как продукт (§2.2, §2.3).** Platform-команда построила *внутреннюю платформу* (IDP):
- *Самообслуживание:* команды получали БД ([5.1](../05-dannye/05-01-vybor-hranilisch.md)), очереди ([6.3](../06-vzaimodeystvie-api/06-03-ocheredi-brokery-streaming-kafka.md)), развёртывание self-service (манифест/портал, раздел §4) — без ручной возни с K8s/облаком. Сложность скрыта.
- *Стандарты из коробки (§2.4):* наблюдаемость, безопасность (mTLS [7.3](../07-bezopasnost/07-03-zero-trust.md), секреты [7.4](../07-bezopasnost/07-04-sekrety-shifrovanie.md)) встроены в платформу (paved road [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)) — governance через платформу, не комитет.
- *Продукт, не диктат:* платформу делали *для* разработчиков (product mindset, DX), с обратной связью; self-service (не тикеты — не узкое место); paved road самый лёгкий, но «хочешь иначе — можно» (автономия [12.1](../12-processy-organizaciya-lyudi/12-01-zakon-konveya.md), [12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)). Платформа *обслуживала*, не командовала.

**Результат.** Команды перестали тонуть в инфраструктуре (когнитивная нагрузка снижена [12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)) — фокус вернулся на бизнес; поток ускорился (self-service быстрее тикетов, быстрый онбординг); согласованность (стандарты в платформе [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)) без комитета-узкого места; меньше дублирования (общее в платформе). Platform engineering дал то, что обещал — но потому что платформу делали *как продукт, обслуживающий* команды, а не как инфраструктурный диктат.

**По нужде.** Это была *большая* организация со многими командами и сложной инфраструктурой — IDP окупился (снизил нагрузку многих §2.4, инвестиция [12.5](../12-processy-organizaciya-lyudi/12-05-build-vs-buy.md)/[13.2](../13-biznes-strategiya/13-02-tco-roi.md)). Для маленькой команды его бы не строили (over-engineering — managed-платформы [9.2](../09-cloud-native-infrastruktura-dostavka/09-02-konteynery-i-orkestraciya.md) достаточны).

**Ошибки-контрпримеры.** Команда А не строила платформу при многих командах — каждая тонула в инфраструктуре, дублировала, несогласованно (проблема §2.1 не решена). Команда Б построила платформу как *диктат* (анти-§2.3): инфраструктурная команда делала «как ей удобно» (не для DX), *заставляла* использовать (не paved road, а единственный путь — узкое место/башня, как тяжёлый governance [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)); разработчики сопротивлялись, принятие низкое. Команда В построила полноценный IDP для *трёх* команд (преждевременно §2.4) — огромная инвестиция в платформу без отдачи (over-engineering, managed хватило бы). Уроки: платформа нужна по нужде (многие команды), как продукт (DX, обслуживает), не диктат, не преждевременно.

**Мораль:** platform engineering строит IDP — внутреннюю платформу с самообслуживанием (развёртывание, инфраструктура, наблюдаемость), скрывающую сложность, чтобы команды не тонули в ней (когнитивная нагрузка [12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)) и фокусировались на бизнесе. Ключевое — платформа как *продукт*: для разработчиков (DX), self-service (не тикеты), обслуживает не диктует (paved road [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md), автономия [12.1](../12-processy-organizaciya-lyudi/12-01-zakon-konveya.md)). Встраивает стандарты (governance через платформу [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)). По нужде: при многих командах/сложной инфраструктуре окупается; для немногих — over-engineering. Это оформление platform-команд и cloud-native ([М9](../09-cloud-native-infrastruktura-dostavka/README.md)) в дисциплину.

---

## 6. Антипаттерны и ловушки

**Команды тонут без платформы.** Много команд осваивают сложную инфраструктуру каждая сама (§2.1, кейс А): когнитивная перегрузка ([12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)), дублирование, несогласованность. Платформа (по нужде).

**Платформа-диктат.** Платформа *заставляет*, а не обслуживает; инфраструктурная команда делает «как ей удобно» (§2.3, кейс Б): узкое место/башня (как тяжёлый governance [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)), сопротивление, низкое принятие. Продукт, обслуживающий, paved road (не единственный путь).

**Преждевременная платформа.** Строить IDP для немногих команд/простой инфраструктуры (§2.4, кейс В): over-engineering (как преждевременный K8s [9.2](../09-cloud-native-infrastruktura-dostavka/09-02-konteynery-i-orkestraciya.md)). Managed-платформы или простота достаточны; платформа — инвестиция, окупается при масштабе.

**Платформа без product mindset / DX.** Делать платформу без учёта нужд разработчиков, обратной связи, удобства: низкое принятие, разработчики обходят. Product mindset, DX.

**Тикеты вместо self-service.** Платформа через тикеты к инфра-команде, а не самообслуживание (§2.2): узкое место (как синхронная зависимость [6.1](../06-vzaimodeystvie-api/06-01-sinhronnoe-vs-asinhronnoe.md)), медленно. Self-service.

**Платформа не встраивает стандарты.** IDP без встроенных безопасности/наблюдаемости: теряется governance через платформу, команды настраивают сами (несогласованность). Встрой стандарты (paved road [12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md)).

**Платформа убирает автономию.** Paved road как *единственный* путь, без «иначе можно» (§2.3, против [12.1](../12-processy-organizaciya-lyudi/12-01-zakon-konveya.md), [12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)): убивает автономию команд. Самый лёгкий путь, но не принудительный.

---

## 7. Ключевые выводы (чеклист)

- [ ] **Platform engineering** строит **IDP (внутреннюю платформу)** с самообслуживанием (развёртывание, инфраструктура, наблюдаемость), **скрывающую сложность** (K8s [9.2](../09-cloud-native-infrastruktura-dostavka/09-02-konteynery-i-orkestraciya.md), облако, CI/CD [9.4](../09-cloud-native-infrastruktura-dostavka/09-04-ci-cd-deployment-strategii.md)).
- [ ] Решает проблему: автономные команды ([12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)) **тонут в инфраструктурной сложности** — платформа снижает их когнитивную нагрузку, команды фокусируются на бизнесе.
- [ ] **Платформа — продукт**, пользователи — разработчики: product mindset, **developer experience (DX)**, обратная связь; self-service (не тикеты — не узкое место).
- [ ] **Обслуживает, не диктует** ([12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md), [12.6](../12-processy-organizaciya-lyudi/12-06-liderstvo-mentorstvo.md)): paved road — самый лёгкий путь, но «иначе можно» (автономия [12.1](../12-processy-organizaciya-lyudi/12-01-zakon-konveya.md), [12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md)). Не контроль-башня.
- [ ] **Встраивает стандарты** (безопасность [М7](../07-bezopasnost/README.md), наблюдаемость [8.2](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-02-logi-metriki-trasing.md)) — governance через платформу, не комитет.
- [ ] **По нужде, не преждевременно** (§2.4): оправдан при многих командах/сложной инфраструктуре (окупается, инвестиция [12.5](../12-processy-organizaciya-lyudi/12-05-build-vs-buy.md)/[13.2](../13-biznes-strategiya/13-02-tco-roi.md)); для немногих — over-engineering (managed [9.2](../09-cloud-native-infrastruktura-dostavka/09-02-konteynery-i-orkestraciya.md) достаточны).
- [ ] **Риски:** платформа-диктат (узкое место/башня), преждевременная платформа, платформа без DX. Продукт, обслуживающий, по нужде.
- [ ] Оформляет platform-команды и cloud-native ([М9](../09-cloud-native-infrastruktura-dostavka/README.md)) в дисциплину — эволюция фундаментальных принципов, не магия.

---

## 8. Упражнения и вопросы

1. Какую проблему решает platform engineering? Как IDP снижает когнитивную нагрузку команд ([12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md))?
2. Что значит «платформа как продукт»? Почему DX и self-service важны, и почему платформа должна обслуживать, не диктовать ([12.4](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md))?
3. Когда IDP оправдан, а когда преждевременен (over-engineering)? Почему платформа — инвестиция ([12.5](../12-processy-organizaciya-lyudi/12-05-build-vs-buy.md))?
4. Тонут ли команды в твоей организации в инфраструктурной сложности (K8s, облако, CI/CD)? Есть ли платформа/самообслуживание или каждая настраивает сама?
5. Если платформа есть — это продукт (DX, self-service, обслуживает) или диктат (тикеты, заставляет, узкое место)? Встроены ли стандарты?
6. Возьми пример из раздела §4: для своей организации продумай, что войдёт в IDP (что вынести в самообслуживание), какие стандарты встроить, как обеспечить DX и автономию.
7. Реши, нужна ли платформа для организации по выбору: сколько команд, сложна ли инфраструктура, тонут ли команды? Если да — как сделать её продуктом (не диктатом), по нужде (не преждевременно)?

## 9. Что почитать дальше

- **«Team Topologies» (Skelton, Pais), про platform teams.** Платформа как самообслуживание, X-as-a-Service — основа разделов §2.1–§2.3; связь с [12.2](../12-processy-organizaciya-lyudi/12-02-team-topologies.md).
- **«Platform Engineering» (материалы platformengineering.org, CNCF).** IDP, самообслуживание, платформа как продукт — все разделы.
- **«Team Topologies» + «Thinnest Viable Platform».** Минимальная достаточная платформа, по нужде — раздел §2.4.
- **Spotify / Netflix про internal developer platforms.** Платформа как продукт, DX — раздел §2.3.
- **Humanitec / Backstage (документация IDP).** Практика построения IDP, порталы разработчика — раздел §2.2.

---

*Следующая глава — [14.2](14-02-data-mesh.md) «Data Mesh»: применение идей децентрализации, владения и self-service (как в platform engineering) к *данным* — data mesh как подход к данным в масштабе организации: данные как продукт, доменное владение, self-service платформа данных.*

<!-- related -->

---

## Связанные главы

**Опирается на:**
- [12.2. Team Topologies](../12-processy-organizaciya-lyudi/12-02-team-topologies.md) — типы команд и режимы взаимодействия; когнитивная нагрузка.
- [12.4. Governance и стандарты](../12-processy-organizaciya-lyudi/12-04-governance-standarty.md) — лёгкое управление, guardrails, paved road.
- [9.2. Контейнеры и оркестрация](../09-cloud-native-infrastruktura-dostavka/09-02-konteynery-i-orkestraciya.md) — Kubernetes; операционная цена; по нужде.
- [12.1. Закон Конвея](../12-processy-organizaciya-lyudi/12-01-zakon-konveya.md) — структура системы повторяет структуру организации; обратный манёвр.
- [8.2. Логи, метрики, трейсинг](../08-nadezhnost-nablyudaemost-proizvoditelnost/08-02-logi-metriki-trasing.md) — три столпа наблюдаемости; золотые сигналы.

**Ведёт дальше:**
- [14.2. Data Mesh](14-02-data-mesh.md) — децентрализация данных; четыре принципа.
- [14.4. Real-time: доставка данных пользователю](14-04-realtime-streaming.md) — опрос vs push, SSE и WebSocket, fan-out, состояние соединений.
- [16.2. Глоссарий](../16-spravochnik/16-02-glossariy.md) — термины с английскими оригиналами и ссылками на главы.

<!-- nav -->

---

| Назад | Вверх | Вперёд |
|:---|:---:|---:|
| ← [13.4. Отраслевая специфика](../13-biznes-strategiya/13-04-otraslevaya-specifika.md) | [Модуль 14](README.md) · [Оглавление](../README.md) | [14.2. Data Mesh](14-02-data-mesh.md) → |

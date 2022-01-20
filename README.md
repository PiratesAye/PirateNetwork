# Пиратский Инетрнет Судного Дня

## Мотивация

В современном информационном обществе доступ в Интернет является одним из основных потребностей человека, но некоторые события последнего времени наводят на мысль что право на доступ к информации не является неотъемлемым, а сама информация может подвергаться цензуре. Возможен сценарий, когда в отдельно взятом городе или стране доступ к Интернету прекращается по независящим от пользователя причинам. Этот сценарий — **Интернет Судного Дня (Doomsday Internet)** становится все более реалистичным, и поэтому мы планируем проект Пиратского Интернета, который оставался бы в строю, даже когда доступ к большой сети прекращен.

В данном документе планируется ранняя версия Пиратского Интернета, обозначаются основные идеологические и технологические способы реализации Проекта.

## Сценарии Реализации Пиратского Интернета

### Физический Слой: 802.11s

Предположим, что наиболее полный контроль над создаваемой сетью возможен лишь с полным контролем над сетевой инфраструктурой. В случае активации Выключателя Судного Дня (выключения сетевой инфраструктуры, обеспечивающей функционирования Интернета), вновь создаваемая инфраструктура должна быть устойчива, а значит обслуживаемая ею Пиратская Сеть должна оставаться функционирующей.

Существует экономически реалистичный способ создания такой сети, путем построения беспроводной [WiFi Mesh сети (802.11s)](https://en.wikipedia.org/wiki/IEEE_802.11s). 
Предполагается использовать проект [OpenWRT](https://openwrt.org/), который для ряда потребительских роутеров позволяет полностью заменить ПО на открытое, и настроить роутер на участие в пиратской mesh-сети. 

Участник mesh-сети, таким образом, может пользоваться ресурсами mesh-сети, транспортом для других участников сети, или быть узлом через который происходит доступ во внешние сети.

### (Альтернатива) Физический Слой: LoRaWAN

В дополнение к WiFi так-же возможно применение недорогих трансиверов на основе LoRaWAN с открытой прошивкой [Meshtastic](https://meshtastic.org/).
Данная технология позволяет при прямой видимости передавать сообщения на большие расстояния - до 100км. Скорость передачи низкая, но достаточная для отправки текста. Питание данных устройств минимально, по-этому возможна их установка на крыши с питанием от солнечных панелей.

TODO: [Вставить физические ограничения сети, расстояние между узлами]

### Доступ во внешний Интернет минуя точки фильтрации трафика

Возможно путем созданяи выходных узлов Пиратской сети через спутниковый интернет, такой как Starlink.

TODO: [Вставить инструкцию по использованию Старлинка в РФ]

### Логический Слой: IPv6 Mesh Сеть Yggdrasil

Даже когда мы пользуемся публичной сетью интернет, возможно создание внутрнии нее своей, самоорганизующейся сетью, свободной от некоторых разновидностей Выключателя Судного Дня, связанных с ограничениями в функционировании тублиц роутинга. Это может быть достигнуто использованием сети [Yggdrassil](https://yggdrasil-network.github.io/) -- логической ipv6 mesh сети с полным шифрованием. Внутри Ygdrassil возможно создание Пиратских ресурсов, доступ к которым не может быть ограничен извне, из-за невозможности их филической локализации.

### Объединение

Объединение этих подходов позволит создать полностью независимую Пиратскую сеть, отвечающую идеалам свободного распостранения информации.

TODO: [Вставить положения манифеста Пиратов]

### Финансовая мотивация

Возможно использование таких проектов как Ethereum для справедливого распределения финансовых ресурсов между операторами Пиратской сети и ресурсов для поддержания должного уровня сети и ресурсов, как и полагается справедливым Пиратам.

TODO: [Вставить конкретное описание проекта, описание технологии цифровых контрактов и сетевой репутации]

#### Private Blockchain: Hyperledger Fabric

Hyperledger Fabric[1] позволяет создавать изолированный частный blockchain, необходимый для работы Пиратского Интернета.

1. **Permissioned** — участники сети обладают identity, а не анонимны.
2. Fabric — не криптовалюта, а распределенный ledger, в котором хранятся данные об участниках сети.
3. Fabric исполняет смарт-контракты, абстрагируясь от экономического определения blockchain.

Таким образом, fabric может быть основой внутреннего blockchain ledger, в котором хранятся данные, необходимые для справедливого функционирования сети для каждого пользователя Пиратской Сети (Пирата).

Предполагаемые метрики пользователя, хранимые в Fabric.

1. User UUID
2. Uptime
3. Traffic In
4. Traffic Out

#### Public Blockchain: Ethereum

Публичный blockchain необходим для реализации финансовой составляющей проекта. Предполагаемый сценарий использования

1. Пользователь генерирует пару private key / public key, которые могут быть использованы в public blockchain Ethereum 
2. Ethereum Public Key становится идентификатором пользователя в private blockchain Fabric
3. ПО на узлах Пиратской Сети (роутерах), взаимодействует с Fabric для хранения пользовательских метрик.

#### Открытые вопросы

1. **Как обеспечить достоверность данных об узлах в сети?** -> метрики в Fabric узел отправляет не о себе, а о своих соседях. При наличии у узла более 1 соседа, достоверность определяется путем сравнения данных.


## Ответственные за проект

TODO: [Кто занимается проектом, делаем конкертно или болтаем?]

## Ссылки

[1] [Hyperledger Fabric для Чайников, Николай Нефедов, Habrahabr, 22 марта 2019](https://habr.com/ru/company/ibm/blog/444874/)
[2] [CJDNS мертв, да здравствует Yggdrasil, shifttstas, 16 марта 2019](https://habr.com/ru/post/443934/)


---

## Ревизии документа

Так как этот Work-in-Progress, основные моменты планирования сети должны быть отражены в документе.

## 19 Января 2022

Основные технологии, которые необходимо принять во внимание

1. [Hyperledger Fabric](https://www.hyperledger.org/use/fabric)
2. [Yggdrasil](https://yggdrasil-network.github.io/)
3. [OpenWRT](https://openwrt.org/)
4. [Ethereum](https://ethereum.org/en/)
5. [Arti](https://gitlab.torproject.org/tpo/core/arti/)

### Открытые вопросы (Идеи)

1. Участники сети анонимны, но обладают identity (eth pubkey)
2. Анонимность внутри сети
3. Tor, луковичный роутинг
4. Каким образом должны поощеряться операторы узлов сети, исходя из статистики их оборудовния
5. High-Level Pirate Passport, на основе identity; Reputation / Credibility 
6. Pirate Network — мост в Yggdrasil или распределенная организация для поддержания оборудовния для доступа в Yggdrasil
7. Внутренние ресурсы, everyday usage

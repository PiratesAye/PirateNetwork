# Пиратская Сеть

## Мотивация

В случае Терминального События (ТС), доступ в Интернет прекращается по независящим от пользователя причинам -- сценарий Выключателя Судного Дня (Doomsday Switch). В данном документе предлагаются варианты создания Пиратского 
Интернета (ПИ) -- сети, функционирование которой зависит от участников, и защищенной от Doomsday Switch.

## Сценарии Реализации Пиратского Интернета

### Физический Слой: WiFi Mesh Сеть

Предположим, что наиболее полный контроль над создаваемой сетью возможен лишь с полным контролем над сетевой инфраструктурой. В случае активации Выключателя Судного Дня, такая инфраструктура устойчива, а значит обслуживаемая ею есть останется невредимой.

Существует экономически реалистичный способ создания такой сети, путем построения беспроводной [WiFi Mesh сети (802.11s)](https://en.wikipedia.org/wiki/IEEE_802.11s). 
Предлагается использовать проект [OpenWRT](https://openwrt.org/), который для ряда потребительских роутеров позволяет полностью заменить ПО на открытое, и настроить роутер на учатие в пиратской mesh-сети. Участник mesh-сети, таким образом, может пользоваться ресурсами mesh-сети, подсоединять новых участников сети, или быть узлом через который происходит доступ во внешние сети.

Простыми словами -- оператор mesh узла -- становится участником сети, Пиратом!

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

## Ответственные за проект

TODO: [Кто занимается проектом, делаем конкертно или болтаем?]

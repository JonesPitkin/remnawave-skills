# Subscription Settings And Response Rules

Источники:

- `https://docs.rw/docs/learn-en/quick-start/`
- `https://docs.rw/docs/learn-en/templates/`

## Subscription Settings

Официальный `Initial Setup` guide показывает, что в navigation menu существует раздел:

- `Subscription` -> `Settings`

Этот раздел управляет дополнительной metadata, которую поддерживаемые client apps получают вместе с subscription response.

Docs приводят пример `Subscription Name` как одной из таких настроек.

## Response Rules

Тот же official navigation layer показывает, что существует раздел:

- `Subscription` -> `Response Rules`

Официальный `Templates` guide также говорит, что multiple Templates можно маршрутизировать через:

- `External Squads`
- `Routing Rules`

Практический вывод:

- `Response Rules` и routing logic subscription layer нужно отличать от node-side `Server-Side Routing`;
- subscription generation и traffic forwarding — разные слои.

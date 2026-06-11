# External Squads

Источник:

- `https://docs.rw/docs/learn-en/squads/`

## Что подтверждено

- Since `2.2.0`, `External Squads` implemented.
- Они используются для переопределения:
  - `Templates`
  - headers/settings, заданных в `Subscription -> Settings`
- Docs прямо приводят пример group-specific override:
  - другой `Announce` message;
  - custom routing per user group.

## UI shape

- При создании External Squad есть как минимум две вкладки:
  - `Templates`
  - `Settings`

## Практический смысл

- External Squad является subscription-layer override mechanism.
- Это не то же самое, что `Internal Squad`, который определяет доступ пользователя к Inbounds.

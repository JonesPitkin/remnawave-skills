---
name: remnawave-users
description: Создавать и сопровождать Users в Remnawave по официальным learning materials, не придумывая скрытых UI-функций и полей.
---

# Remnawave Users

## Назначение

Этот skill отвечает за создание Users, лимиты трафика, expiration, привязку к Internal/External Squads и использование user management tools.

## Теория

По official learning docs пользователь в Remnawave получает subscription access и набор ограничений:

- `Data limit`
- `Traffic reset strategy`
- expiration date
- привязка к `Internal Squads`
- опционально привязка к `External Squads`

Первый зарегистрированный пользователь становится `super-admin`.

## Практика

1. Открыть `Users` и нажать `Create user`.
2. Задать username без пробелов.
3. В `Traffic & Limits` определить:
   - `Data limit`
   - `Traffic reset strategy`
4. В `Access Settings` определить:
   - дату окончания подписки;
   - один или несколько `Internal Squads`;
   - при необходимости `External Squads`.
5. Нажать `Create user`.
6. Для сопровождения пользователя открыть `Edit user` -> `More actions`.

## Типовые сценарии

- Создание тестового пользователя с `1 GB` и daily reset.
- Назначение пользователя в `Default-Squad`.
- Просмотр `Detailed Info`, `Show usage`, `HWIDs and Devices`.

## Ошибки

- Использовать пробелы в username.
- Создать пользователя без нужного `Internal Squad`, из-за чего доступ к Inbounds окажется неполным.
- Считать `Detailed Info` или `HWIDs and Devices` источником полей, которых нет в docs.

## Проверка результата

- Пользователь виден в user table.
- В таблице корректно отображаются `Total`, `Active`, `Expired` статусы.
- В `More actions` доступны:
  - `Detailed Info`
  - `Show usage`
  - `HWIDs and Devices`

## Ссылки

- [references/initial-setup.md](references/initial-setup.md)
- [references/users.md](references/users.md)
- [references/official-links.md](references/official-links.md)

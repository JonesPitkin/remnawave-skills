---
name: remnawave-happ-routing
description: Работать с Happ Routing в Remnawave только в пределах того, что прямо подтверждено официальной документацией, без выдумывания скрытых правил или форматов.
---

# Remnawave Happ Routing

## Назначение

Этот skill покрывает Happ Routing настолько, насколько он подтвержден в разрешенных официальных источниках Remnawave.

## Теория

В доступных официальных материалах подтверждено следующее:

- в `Utilities` существует инструмент `Happ Routing`;
- его назначение — создание и управление routing rules для Happ;
- в `Detailed Info` пользователя встречаются `Happ Crypto links`.

При этом в разрешенном наборе источников нет полноценной пошаговой страницы с полной схемой полей Happ Routing builder.

## Практика

1. Подтвердить, что задача действительно про `Happ Routing`, а не про:
   - `Server-Side Routing`
   - `Templates`
   - `Hosts`
2. В Panel открыть `Utilities`.
3. Найти раздел `Happ Routing`.
4. Если требуется точная форма полей, экспортный формат или внутренняя схема правил, сверить это с текущим runtime UI и отметить, что в локальных official materials детальный workflow отсутствует.

## Типовые сценарии

- Пользователь просит включить или проверить routing rules для Happ.
- Нужно понять, где в Panel находится Happ-specific utility.
- Нужно различить Happ Routing и обычный server-side routing bridge.

## Ошибки

- Приписывать Happ Routing те же шаги, что у `Server-Side Routing`.
- Выдумывать undocumented rule schema.
- Считать, что официальные docs из разрешенного набора уже содержат полную field-by-field инструкцию для Happ Routing.

## Проверка результата

- В ответе явно указано, какая часть подтверждена docs.
- Любые неподтвержденные детали помечены как отсутствующие в официальных источниках.
- Happ Routing не перепутан с `Server-Side Routing`.

## Ссылки

- [references/happ-routing.md](references/happ-routing.md)
- [references/users-and-happ.md](references/users-and-happ.md)
- [references/official-links.md](references/official-links.md)

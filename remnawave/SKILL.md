---
name: remnawave
description: Использовать как entrypoint skill для маршрутизации задач по Remnawave к нужному specialist module, опираясь только на официальные материалы docs.rw и github.com/remnawave.
---

# Remnawave Router

Используй этот skill, когда задача связана с Remnawave, но еще не ясно, какой specialist skill должен быть основным.

## Назначение

Этот skill не заменяет specialist guides. Его задача — быстро определить рабочий домен и перенаправить выполнение в правильный модуль:

- `remnawave-install`
- `remnawave-users`
- `remnawave-nodes`
- `remnawave-config-profiles`
- `remnawave-subscriptions`
- `remnawave-happ-routing`
- `remnawave-api`
- `remnawave-troubleshooting`

## Теория

По официальной документации Remnawave состоит как минимум из Panel, Backend, Frontend и Node. Panel — главный entry point, а Node — lightweight container с Xray-core. Часть задач относится к install layer, часть — к operational UI layer, часть — к Node/Xray integration, а часть — к subscription/API workflows.

## Практика

1. Определи класс задачи:
   - установка Panel или Node;
   - работа с Users;
   - создание Config Profiles;
   - Subscription URL, Templates или Subscription Page;
   - REST API или API Tokens;
   - troubleshooting.
2. Зафиксируй version-sensitive контекст:
   - какой Panel release используется;
   - где запущены Panel и Node;
   - есть ли reverse proxy;
   - включена ли документация API.
3. Перейди в specialist skill и не выполняй production mutation, пока нужный шаг не подтвержден официальной документацией.

## Типовые сценарии

- Нужно установить Panel с нуля: перейти в `remnawave-install`.
- Нужно добавить Node и связать его с Panel: перейти в `remnawave-nodes`.
- Нужно создать пользователя и проверить лимиты: перейти в `remnawave-users`.
- Нужно разобраться с subscription delivery и Templates: перейти в `remnawave-subscriptions`.
- Нужно работать с API tokens и docs: перейти в `remnawave-api`.

## Ошибки

- Смешивать install, API и subscription workflows в один неструктурированный ответ.
- Додумывать поведение UI, если оно не подтверждено docs.
- Путать Happ Routing и Server-Side Routing: официальные материалы различают эти вещи.

## Проверка результата

- Выбран ровно один основной specialist skill.
- Version-sensitive детали отмечены заранее.
- Все утверждения опираются только на локальные official references.

## Ссылки

- [references/overview.md](references/overview.md)
- [references/official-links.md](references/official-links.md)
- [references/github-repositories.md](references/github-repositories.md)

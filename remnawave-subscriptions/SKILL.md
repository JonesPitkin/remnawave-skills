---
name: remnawave-subscriptions
description: Работать с Subscription URL, Templates, Hosts и Subscription Page в Remnawave по официальным материалам без выдуманных client-specific функций.
---

# Remnawave Subscriptions

## Назначение

Этот skill покрывает delivery цепочку подписки: Subscription URL, Hosts, Templates, Subscription Page и привязку API token к subscription-page deployment.

## Теория

По официальной документации:

- у пользователя есть `Subscription URL`;
- browser и client app получают разный ответ на один и тот же URL;
- Panel автоматически определяет, кто обращается к URL;
- Hosts выступают как gateway к Nodes;
- Templates определяют, что получает клиент в зависимости от client/core family;
- Subscription Page нужен, чтобы скрыть Panel domain от end users.

## Практика

1. Создать пользователя и получить его subscription workflow.
2. Настроить `Hosts`:
   - создать host;
   - выбрать один inbound;
   - определить visibility.
3. Настроить `Templates`:
   - проверить нужную family: `Mihomo`, `Xray-json`, `Sing-box`, fallback `Base64`;
   - при необходимости создать несколько templates для одного core family.
4. При работе с публичной подпиской определить схему `Subscription Page`:
   - `Bundled`
   - `Separate server`
5. Для Subscription Page:
   - обновить `SUB_PUBLIC_DOMAIN`;
   - создать `REMNAWAVE_API_TOKEN` в dashboard;
   - задать `REMNAWAVE_PANEL_URL` и `REMNAWAVE_API_TOKEN` в `.env`.

## Типовые сценарии

- Пользователь открывает subscription URL в браузере и видит human-readable page.
- Пользователь добавляет тот же URL в client app и получает client-specific config.
- Хост `Finland` публикует только финские nodes.
- Subscription Page скрывает основной Panel domain от конечных пользователей.

## Ошибки

- Считать `Host` мульти-inbound контейнером: docs прямо говорят, что на один Host выбирается только один inbound.
- Путать `Templates` и `Hosts`: Host выбирает entry point, Template определяет format.
- Не пересоздать Panel containers после изменения `SUB_PUBLIC_DOMAIN`.
- Запустить Subscription Page без `REMNAWAVE_API_TOKEN`.

## Проверка результата

- Browser по subscription URL получает web page.
- Client app по тому же URL импортирует config.
- Нужный Host виден пользователю только если `Host visibility` включен.
- Subscription Page отдает данные по ожидаемому публичному домену.

## Ссылки

- [references/subscription-overview.md](references/subscription-overview.md)
- [references/hosts.md](references/hosts.md)
- [references/templates.md](references/templates.md)
- [references/subscription-page.md](references/subscription-page.md)
- [references/official-links.md](references/official-links.md)

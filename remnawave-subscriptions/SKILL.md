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
- `External Squads` могут переопределять Templates и subscription-side settings;
- `Subscription -> Settings` управляет дополнительной metadata, которую получают поддерживаемые clients;
- `Response Rules` определяют, как генерируется конфигурация для client apps;
- Subscription Page нужен, чтобы скрыть Panel domain от end users.

## Практика

1. Создать пользователя и получить его subscription workflow.
2. Настроить `Hosts`:
   - создать host;
   - выбрать один inbound;
   - определить visibility.
3. Настроить `Subscription -> Settings`:
   - subscription-side metadata, которую поддерживаемые client apps получают вместе с ответом;
   - помнить, что `External Squads` могут переопределять эти settings.
4. Настроить `Templates`:
   - проверить нужную family: `Mihomo`, `Xray-json`, `Sing-box`, fallback `Base64`;
   - при необходимости создать несколько templates для одного core family.
5. Настроить `Response Rules` как generation layer:
   - воспринимать их отдельно от `Templates`;
   - использовать для определения того, как именно клиенту выдается configuration;
   - не путать их с `Server-Side Routing` на Nodes.
6. При необходимости настроить `External Squads`:
   - override Templates;
   - override данные из `Subscription -> Settings`;
   - применять per-user-group variations.
7. При работе с публичной подпиской определить схему `Subscription Page`:
   - `Bundled`
   - `Separate server`
8. Для Subscription Page:
   - обновить `SUB_PUBLIC_DOMAIN`;
   - создать `REMNAWAVE_API_TOKEN` в dashboard;
   - задать `REMNAWAVE_PANEL_URL` и `REMNAWAVE_API_TOKEN` в `.env`.

## Subscription Pipeline

Официально подтвержденная delivery chain выглядит так:

1. User получает `Subscription URL`.
2. Browser или client app обращается к этому URL.
3. Remnawave определяет тип клиента.
4. `Hosts` задают entry point и node-side destination details.
5. `Templates` определяют family-specific config output.
6. `Response Rules` участвуют в generation logic.
7. `Subscription -> Settings` добавляет supported metadata.
8. `External Squads` могут переопределить Templates и subscription-side settings.
9. При публичной раздаче `Subscription Page` скрывает основной Panel domain.

## Типовые сценарии

- Пользователь открывает subscription URL в браузере и видит human-readable page.
- Пользователь добавляет тот же URL в client app и получает client-specific config.
- Хост `Finland` публикует только финские nodes.
- Subscription Page скрывает основной Panel domain от конечных пользователей.
- External Squad выдает другой Template или другой `Announce` группе пользователей.
- `Response Rules` меняют способ генерации client response отдельно от node-side Xray routing.

## Ошибки

- Считать `Host` мульти-inbound контейнером: docs прямо говорят, что на один Host выбирается только один inbound.
- Путать `Templates` и `Hosts`: Host выбирает entry point, Template определяет format.
- Путать `Response Rules` и `Server-Side Routing`: первое относится к subscription generation, второе к node-side traffic path.
- Игнорировать `External Squads`, хотя нужны group-specific overrides.
- Не пересоздать Panel containers после изменения `SUB_PUBLIC_DOMAIN`.
- Запустить Subscription Page без `REMNAWAVE_API_TOKEN`.

## Проверка результата

- Browser по subscription URL получает web page.
- Client app по тому же URL импортирует config.
- Нужный Host виден пользователю только если `Host visibility` включен.
- Subscription Page отдает данные по ожидаемому публичному домену.
- Если используются `External Squads`, override логика прослеживается в выдаваемой подписке.
- `Templates`, `Response Rules` и `Subscription -> Settings` не смешаны в одно понятие.

## Ссылки

- [references/subscription-overview.md](references/subscription-overview.md)
- [references/hosts.md](references/hosts.md)
- [references/templates.md](references/templates.md)
- [references/subscription-settings-and-rules.md](references/subscription-settings-and-rules.md)
- [references/external-squads.md](references/external-squads.md)
- [references/subscription-pipeline.md](references/subscription-pipeline.md)
- [references/subscription-page.md](references/subscription-page.md)
- [references/official-links.md](references/official-links.md)

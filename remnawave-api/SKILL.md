---
name: remnawave-api
description: Работать с официальным REST API Remnawave через API Tokens, docs.rw/api и panel-side Swagger/Scalar, не выдумывая неописанные endpoints.
---

# Remnawave API

## Назначение

Этот skill покрывает API Tokens, включение встроенной документации, базовые API workflows и безопасную работу с official interactive spec.

## Теория

Официальные источники подтверждают:

- существует official interactive API documentation на `docs.rw/api`;
- часть controllers в official spec защищена auth;
- official spec отдельно отмечает `Public Subscription Controller` как public/non-auth layer;
- в dashboard есть `API Tokens`;
- `API Tokens` находятся в `Remnawave Settings` начиная с `2.2.0`;
- panel docs поддерживают `Swagger UI` и `Scalar UI`;
- доступность встроенной docs регулируется `IS_DOCS_ENABLED`.

## Authentication Flow

Официально подтверждаемая минимальная auth-модель выглядит так:

1. Admin/operator включает docs при необходимости через env.
2. В `Remnawave Settings` создается `API Token`.
3. Interactive spec distinguishes:
   - protected controllers, которым нужен auth;
   - `Public Subscription Controller`, который не защищен auth и предназначен только для public requests.
4. Для automation и `subscription-page` используется `REMNAWAVE_API_TOKEN`.

## Практика

1. Включить docs при необходимости:
   - `IS_DOCS_ENABLED=true`
   - `SWAGGER_PATH=/docs`
   - `SCALAR_PATH=/scalar`
2. Пересоздать контейнеры после изменения `.env`:
   - `docker compose down && docker compose up -d`
3. Создать `API Token` в `Remnawave Settings`.
4. Использовать:
   - public spec на `https://docs.rw/api/`
   - локальный panel docs path, если он включен
5. Определить controller class:
   - public subscription operations;
   - admin/protected operations;
   - settings/tokens/tooling operations.
6. Для automation или subscription-page использовать `REMNAWAVE_API_TOKEN`.
7. Перед mutation проверять endpoint contract в official spec, а не в community SDK wrappers.

## Controller Structure

По official interactive spec snippets подтверждены как минимум такие controller groups:

- `API Tokens Controller`
- `Users Controller`
- `Hosts Controller`
- `Config Profiles Controller`
- `[Protected] Subscriptions Controller`
- `Public Subscription Controller`
- settings/system-related operations, включая `get /api/remnawave-settings`
- tooling/system operations вроде Happ encrypt, SRR matcher и recap stats

## Request/Response Examples

Без выдумывания schema можно опираться на минимально подтвержденные operation examples:

- `post /api/tokens`
- `get /api/tokens`
- `delete /api/tokens/{uuid}`
- `post /api/users`
- `patch /api/users`
- `get /api/hosts`
- `post /api/hosts`
- `get /api/config-profiles`

Если нужен точный request body, response DTO или auth header format, его нужно смотреть в official interactive spec на момент выполнения задачи.

## Operational Guidance

- Включать panel-side docs только когда это действительно нужно оператору.
- После env changes всегда делать recreate containers.
- Не фиксировать локально полный API contract вручную, если official spec уже интерактивен и может меняться.
- Для public subscription requests не применять assumptions от protected admin controllers.

## Типовые сценарии

- Нужно выдать токен для `subscription-page`.
- Нужно открыть official Swagger/Scalar на локальной панели.
- Нужно проверить, доступна ли interactive API documentation после изменения `.env`.
- Нужно понять, какой controller отвечает за Users, Hosts или Config Profiles.
- Нужно различить protected admin endpoint и public subscription endpoint.

## Ошибки

- Искать полный API only в неофициальных SDK.
- Забыть включить `IS_DOCS_ENABLED`.
- Менять `.env` без recreate containers.
- Придумывать endpoint names, если они не подтверждены official spec.
- Смешивать `Public Subscription Controller` и protected admin operations.
- Жестко прошивать request/response schema в локальную документацию без сверки с interactive spec.

## Проверка результата

- `IS_DOCS_ENABLED=true` реально применился после recreate.
- `SWAGGER_PATH` и `SCALAR_PATH` открываются на panel instance.
- `API Token` создан и используется в downstream flows.
- Ответ не содержит неофициальных endpoint claims.
- Controller group и auth layer определены до начала интеграции.

## Ссылки

- [references/api-docs.md](references/api-docs.md)
- [references/env-docs.md](references/env-docs.md)
- [references/initial-setup.md](references/initial-setup.md)
- [references/auth-and-controllers.md](references/auth-and-controllers.md)
- [references/operations-examples.md](references/operations-examples.md)
- [references/github-repositories.md](references/github-repositories.md)
- [references/official-links.md](references/official-links.md)

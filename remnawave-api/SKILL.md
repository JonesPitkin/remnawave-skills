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
- в dashboard есть `API Tokens`;
- `API Tokens` находятся в `Remnawave Settings` начиная с `2.2.0`;
- panel docs поддерживают `Swagger UI` и `Scalar UI`;
- доступность встроенной docs регулируется `IS_DOCS_ENABLED`.

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
5. Для automation или subscription-page использовать `REMNAWAVE_API_TOKEN`.

## Типовые сценарии

- Нужно выдать токен для `subscription-page`.
- Нужно открыть official Swagger/Scalar на локальной панели.
- Нужно проверить, доступна ли interactive API documentation после изменения `.env`.

## Ошибки

- Искать полный API only в неофициальных SDK.
- Забыть включить `IS_DOCS_ENABLED`.
- Менять `.env` без recreate containers.
- Придумывать endpoint names, если они не подтверждены official spec.

## Проверка результата

- `IS_DOCS_ENABLED=true` реально применился после recreate.
- `SWAGGER_PATH` и `SCALAR_PATH` открываются на panel instance.
- `API Token` создан и используется в downstream flows.
- Ответ не содержит неофициальных endpoint claims.

## Ссылки

- [references/api-docs.md](references/api-docs.md)
- [references/env-docs.md](references/env-docs.md)
- [references/initial-setup.md](references/initial-setup.md)
- [references/github-repositories.md](references/github-repositories.md)
- [references/official-links.md](references/official-links.md)

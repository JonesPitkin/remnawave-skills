---
name: remnawave-install
description: Устанавливать Remnawave Panel по официальной документации, готовить .env, reverse proxy и security baseline без использования неофициальных гайдов.
---

# Remnawave Install

## Назначение

Этот skill покрывает подготовку сервера, установку Remnawave Panel, базовую настройку `.env`, запуск контейнеров и обязательный reverse proxy/security baseline.

## Теория

Официальная документация описывает такую install-модель:

- Remnawave Panel является главным компонентом;
- для Panel и Node требуется `Docker` с `Docker Compose plugin`;
- Panel должен публиковаться через reverse proxy;
- сервисы Remnawave нельзя выставлять в интернет напрямую;
- Panel и компоненты не поддерживают обслуживание на sub-path.

## Практика

1. Проверить требования:
   - для Panel рекомендованы `Ubuntu` или `Debian`;
   - минимум `2 GB RAM`, рекомендовано `4 GB RAM`;
   - минимум `2 CPU cores`, рекомендовано `4 CPU cores`;
   - `20 GB` storage.
2. Установить Docker:
   - `sudo curl -fsSL https://get.docker.com | sh`
3. Подготовить каталог:
   - `mkdir /opt/remnawave && cd /opt/remnawave`
4. Скачать официальные файлы:
   - `curl -o docker-compose.yml https://raw.githubusercontent.com/remnawave/backend/refs/heads/main/docker-compose-prod.yml`
   - `curl -o .env https://raw.githubusercontent.com/remnawave/backend/refs/heads/main/.env.sample`
5. Сгенерировать секреты:
   - `JWT_AUTH_SECRET`
   - `JWT_API_TOKENS_SECRET`
   - `METRICS_PASS`
   - `WEBHOOK_SECRET_HEADER`
6. Сменить `POSTGRES_PASSWORD`.
7. Обновить как минимум:
   - `FRONT_END_DOMAIN`
   - `SUB_PUBLIC_DOMAIN`
8. Запустить контейнеры:
   - `docker compose up -d && docker compose logs -f -t`
9. Сразу после запуска поставить reverse proxy на root path домена или subdomain.
10. Не выставлять backend ports наружу напрямую; использовать loopback binding и reverse proxy.

## Типовые сценарии

- Первая установка Panel на новый VPS.
- Перенос старого стенда на официальный `docker-compose-prod.yml`.
- Исправление небезопасной установки, где Panel был опубликован без reverse proxy.

## Ошибки

- Оставить значения `change_me` в секретах.
- Не сменить пароль Postgres.
- Пытаться публиковать Panel на sub-path вроде `/remnawave`.
- Использовать SSH port forwarding как постоянную схему публикации.
- Менять `.env`, а затем просто рестартовать контейнеры без recreate.

## Проверка результата

- `docker compose ps` показывает рабочие контейнеры.
- `docker compose logs -f -t` не показывает постоянных crash-loop ошибок.
- Panel открывается по домену reverse proxy.
- `FRONT_END_DOMAIN` и `SUB_PUBLIC_DOMAIN` согласованы с фактическим доменом.
- Сервисы не торчат наружу напрямую, кроме контролируемой reverse proxy точки входа.

## Ссылки

- [references/requirements.md](references/requirements.md)
- [references/panel-install.md](references/panel-install.md)
- [references/env-security.md](references/env-security.md)
- [references/official-links.md](references/official-links.md)

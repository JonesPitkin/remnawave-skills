# Remnawave Panel Installation

Источник:

- `https://docs.rw/docs/install/remnawave-panel/`

## Подтвержденные шаги

1. Установить Docker.
2. Создать каталог:
   - `mkdir /opt/remnawave && cd /opt/remnawave`
3. Скачать:
   - `docker-compose-prod.yml` из `remnawave/backend`
   - `.env.sample` из `remnawave/backend`
4. Сгенерировать и заменить:
   - `JWT_AUTH_SECRET`
   - `JWT_API_TOKENS_SECRET`
   - `METRICS_PASS`
   - `WEBHOOK_SECRET_HEADER`
5. Сменить `POSTGRES_PASSWORD`.
6. Указать:
   - `FRONT_END_DOMAIN`
   - `SUB_PUBLIC_DOMAIN`
7. Запустить:
   - `docker compose up -d && docker compose logs -f -t`

## Важные замечания

- `SUB_PUBLIC_DOMAIN` на первом шаге можно задать как `panel.domain.com/api/sub`.
- После install docs требуют перейти к reverse proxy.
- Panel docs отдельно предупреждают: не выставлять сервисы напрямую в public internet и использовать только `127.0.0.1` для Remnawave services.

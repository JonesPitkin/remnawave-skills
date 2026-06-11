# Common Checks

Источники:

- `https://docs.rw/docs/install/remnawave-panel/`
- `https://docs.rw/docs/install/reverse-proxies/`
- `https://docs.rw/docs/install/environment-variables/`

## Подтвержденные проверки

- `docker compose up -d && docker compose logs -f -t`
- recreate after env change:
  - `docker compose down && docker compose up -d`
- reverse proxy должен работать на root path, не на sub-path
- services не должны быть прямо опубликованы в public internet

## Failure patterns

- env edited, but containers not recreated
- panel exposed without reverse proxy
- panel served on unsupported sub-path

# Subscription And API Trouble Points

Источники:

- `https://docs.rw/docs/install/subscription-page/bundled/`
- `https://docs.rw/docs/install/subscription-page/separate-server/`
- `https://docs.rw/docs/install/environment-variables/`
- `https://docs.rw/docs/learn-en/quick-start/`

## Подтвержденные точки сбоя

- `SUB_PUBLIC_DOMAIN` не обновлен или не совпадает с real public subscription URL.
- `REMNAWAVE_API_TOKEN` не создан или не задан.
- `IS_DOCS_ENABLED` выключен, поэтому built-in API docs не открывается.
- `SWAGGER_PATH` или `SCALAR_PATH` изменены, но контейнеры не recreated.

# Subscription Page

Источники:

- `https://docs.rw/docs/install/remnawave-subscription-page/`
- `https://docs.rw/docs/install/subscription-page/bundled/`
- `https://docs.rw/docs/install/subscription-page/separate-server/`

## Назначение

- Subscription Page скрывает domain Remnawave Panel от end users.
- Может быть установлен:
  - на том же сервере (`Bundled`)
  - на другом сервере (`Separate server`)

## Общие требования

- Нужно обновить `SUB_PUBLIC_DOMAIN`.
- Нужен `REMNAWAVE_API_TOKEN`, созданный в dashboard в разделе `API Tokens`.

## Bundled

- Docs показывают bundled-схему, где `REMNAWAVE_PANEL_URL` указывает на внутренний Panel service.
- Docs также показывают loopback publish для subscription page container на локальный host port `3010`.

## Separate server

- Docs показывают separate-server схему, где `REMNAWAVE_PANEL_URL` указывает на публичный Panel domain.
- Шаги выполняются на другом сервере.

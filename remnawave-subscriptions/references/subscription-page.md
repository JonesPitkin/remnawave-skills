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

- Использует `REMNAWAVE_PANEL_URL=http://remnawave:3000`.
- Порт по примеру docs: `127.0.0.1:3010:3010`.

## Separate server

- Использует публичный panel URL вроде `https://remnawave.panel.com`.
- Шаги выполняются на другом сервере.

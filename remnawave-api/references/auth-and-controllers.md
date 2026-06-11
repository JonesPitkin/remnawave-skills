# Auth And Controllers

Источники:

- `https://docs.rw/api/`
- `https://docs.rw/docs/learn-en/quick-start/`
- `https://docs.rw/docs/install/environment-variables/`

## Authentication Flow

Официальные материалы подтверждают:

- `API Tokens` находятся в `Remnawave Settings` начиная с `2.2.0`;
- часть controllers в interactive spec protected with auth;
- `Public Subscription Controller` не защищен auth и предназначен только для public requests.

## Controller Groups Confirmed By Official Spec Snippets

- `API Tokens Controller`
- `Users Controller`
- `Hosts Controller`
- `Config Profiles Controller`
- `[Protected] Subscriptions Controller`
- `Public Subscription Controller`
- settings/system layer, включая `get /api/remnawave-settings`

## Operational Rule

Перед интеграцией нужно сначала определить:

1. protected это endpoint или public;
2. нужен ли operator-created `API Token`;
3. открыта ли panel-side docs через `IS_DOCS_ENABLED`.

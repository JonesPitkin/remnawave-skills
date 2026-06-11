# Overview

Источник:

- `https://docs.rw/docs/overview/introduction/`
- `https://docs.rw/docs/overview/components/`
- `https://docs.rw/docs/overview/quick-start/`
- `https://docs.rw/docs/learn-en/quick-start/`

## Что подтверждено официальной документацией

- Remnawave описывает себя как proxy management tool, built on top of `Xray-core`, с фокусом на simplicity и ease of use.
- В overview docs перечислены компоненты:
  - Panel
  - Backend
  - Frontend
  - Node
  - XTLS-SDK
  - XTLS-SDK-NestJS
- В quick start installation chain указаны шаги:
  - Remnawave Panel
  - Reverse Proxy
  - Subscription Page (optional)
  - Remnawave Node
- `Initial Setup` guide написан для `Panel version 2.0 and newer`.
- После первой регистрации первый пользователь автоматически становится `super-admin`.

## Практический вывод для skill routing

- install-задачи идут в `remnawave-install`;
- node/Xray integration идет в `remnawave-nodes` и `remnawave-config-profiles`;
- user/subscription layer идет в `remnawave-users` и `remnawave-subscriptions`;
- API layer идет в `remnawave-api`;
- runtime failures идут в `remnawave-troubleshooting`.

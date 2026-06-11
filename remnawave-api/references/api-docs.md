# API Documentation

Источники:

- `https://docs.rw/api/`
- официальный search snippet этого же interactive spec

## Что подтверждено

- У Remnawave есть official interactive API documentation.
- Search snippet официального spec показывает как минимум:
  - `API Tokens Controller`
    - `post /api/tokens`
    - `get /api/tokens`
    - `delete /api/tokens/{uuid}`
  - `Public Subscription Controller`
    - public requests, не защищенные auth
  - system/tooling related endpoints вроде:
    - `post /api/system/tools/happ/encrypt`
    - `post /api/system/testers/srr-matcher`
    - `get /api/system/stats/recap`
- Additional official snippets also подтверждают:
  - `Users Controller` c operations для user management
  - `Hosts Controller` c operations для host management
  - `Config Profiles Controller`
  - `[Protected] Subscriptions Controller`
  - `get /api/remnawave-settings`

## Ограничение

Полный endpoint surface в этом репозитории не захардкожен вручную. Для точного contract-first использования нужно открывать official interactive spec на `docs.rw/api/` или на своей panel instance при включенной docs.

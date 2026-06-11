# Environment Variables For API Docs

Источник:

- `https://docs.rw/docs/install/environment-variables/`

## Documentation Switches

- `IS_DOCS_ENABLED` включает/выключает documentation.
- `SWAGGER_PATH` по умолчанию `/docs`.
- `SCALAR_PATH` по умолчанию `/scalar`.

## Важное замечание

- После изменения `.env` необходимо пересоздать контейнеры.

## Example

```env
IS_DOCS_ENABLED=true
SWAGGER_PATH=/docs
SCALAR_PATH=/scalar
```

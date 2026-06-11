---
name: remnawave-troubleshooting
description: Диагностировать install и runtime проблемы Remnawave по официальным предупреждениям и guides, не подменяя source-backed анализ догадками.
---

# Remnawave Troubleshooting

## Назначение

Этот skill покрывает типовые install/runtime проблемы Remnawave: неправильная публикация Panel, env changes without recreate, node/firewall issues, logs, missing docs, subscription-page miswiring.

## Теория

Официальные материалы заранее предупреждают о нескольких классах проблем:

- сервисы нельзя публиковать напрямую в интернет;
- reverse proxy обязателен;
- sub-path не поддерживается;
- env changes требуют recreate containers;
- `NODE_PORT` нужно ограничивать firewall;
- node logs без `logrotate` могут заполнить диск;
- docs/API routes могут быть выключены через `IS_DOCS_ENABLED`.

## Практика

1. Определить слой сбоя:
   - install
   - reverse proxy
   - env
   - API/docs
   - node connectivity
   - subscription delivery
2. Проверить базовые команды:
   - `docker compose ps`
   - `docker compose logs -f -t`
3. Если менялся `.env`, выполнить recreate:
   - `docker compose down && docker compose up -d`
4. Для Node:
   - проверить `docker compose logs -f -t`
   - проверить firewall для `NODE_PORT`
5. Для subscription:
   - проверить `SUB_PUBLIC_DOMAIN`
   - проверить `REMNAWAVE_API_TOKEN`
6. Для forgotten admin access:
   - использовать Rescue CLI:
     - `docker exec -it remnawave remnawave`

## Типовые сценарии

- Panel не открывается по домену.
- После правки `.env` изменения не применились.
- Node не появляется рабочим после добавления.
- Subscription Page не может связаться с Panel.
- Встроенная API docs не открывается.

## Ошибки

- Искать причину в UI, когда `.env` не был применен через recreate.
- Оставлять `NODE_PORT` open to world.
- Использовать sub-path routing в reverse proxy.
- Включить logs на node без rotation.

## Проверка результата

- Выявлен правильный failure domain.
- Устранение опирается на официальные docs warning/steps.
- После исправления сервис либо открывается, либо явно локализован следующий слой сбоя.

## Ссылки

- [references/common-checks.md](references/common-checks.md)
- [references/node-logs-and-firewall.md](references/node-logs-and-firewall.md)
- [references/subscription-and-api.md](references/subscription-and-api.md)
- [references/official-links.md](references/official-links.md)

# Nodes Guide

Источник:

- `https://docs.rw/docs/learn-en/nodes/`

## Ограничение guide

Официальный guide прямо предупреждает, что статья `Nodes` не покрывает install process и для этого нужно использовать install documentation.

## Что покрывает текущий guide

- `Nodes -> Management`
- hourly statistics cards
- `Actions` block:
  - `Update`
  - `Restart all nodes`
- `Node Vitals`
- `Consumption`
- `Core Configuration`
- `Tracking & Billing`
- `Node Management`
- node status indicators
- `More actions`

## Подтвержденные details

- `Consumption` использует multiplier/coefficient для учета user traffic.
- На один Node можно выбрать только один `Config Profile`.
- Внутри одного Profile можно активировать несколько `Inbounds`.
- `Tracking & Billing` включает optional node-side usage tracking:
  - `Infrastructure Provider`
  - `Track traffic usage`
  - `Traffic limit`
  - `Reset day`
  - `Notification %`
- `More actions` включает:
  - `Show usage`
  - `Copy Node UUID`
  - `Disable`
  - `Delete`

## Практический вывод

- install и docker steps брать из `Remnawave Node` install page;
- operational UI interpretation брать из learning materials;
- не смешивать install и dashboard semantics.

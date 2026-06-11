---
name: remnawave-nodes
description: Устанавливать Remnawave Node, подключать его к Panel и сопровождать node-side Xray workflows по официальной документации.
---

# Remnawave Nodes

## Назначение

Этот skill покрывает deployment и подключение Remnawave Node, node firewall, Config Profile assignment и официально описанные advanced node practices.

## Теория

Официальная документация определяет `Remnawave Node` как lightweight container, который включает `Xray-core`. Panel itself не включает `Xray-core`, поэтому полноценная эксплуатация Remnawave требует Node.

Текущий official `Nodes` guide покрывает не только создание Node, но и operational blocks:

- hourly statistics cards;
- `Actions` block;
- `Consumption`;
- `Tracking & Billing`;
- `More actions`;
- Node status indicators;
- `Copy Node UUID`.

## Практика

1. Убедиться, что на node server установлен Docker.
2. Создать каталог:
   - `mkdir /opt/remnanode && cd /opt/remnanode`
3. В Panel открыть `Nodes` -> `Management` и нажать `+`.
4. В форме добавить node и обратить внимание на `Node Port`.
5. Нажать `Copy docker-compose.yml`.
6. Создать локальный `docker-compose.yml` на node server и вставить туда содержимое.
7. Запустить:
   - `docker compose up -d && docker compose logs -f -t`
8. Вернуться в Panel, нажать `Next`, выбрать `Config Profile` и завершить создание.
9. Ограничить `NODE_PORT` firewall-правилом только для IP панели.
10. После создания Node проверить operational card:
   - hourly stats;
   - status icon/background;
   - Xray uptime;
   - traffic usage until refill.
11. Проверить `Actions` block:
   - `Update`
   - `Restart all nodes`
12. Проверить `Consumption`:
   - multiplier/коэффициент меняет способ учета user traffic;
   - `1.0` означает обычный учет;
   - `0.5` и `2.0` меняют биллинг-эквивалент трафика.
13. Проверить `Tracking & Billing`:
   - `Infrastructure Provider`
   - `Track traffic usage`
   - `Traffic limit`
   - `Reset day`
   - `Notification %`
14. В `More actions` проверить:
   - `Show usage`
   - `Copy Node UUID`
   - `Disable`
   - `Delete`

## Типовые сценарии

- Первое подключение одного Node к Panel.
- Назначение нового Config Profile на Node.
- Настройка traffic coefficient для billing semantics.
- Включение node-side limit tracking с monthly reset.
- Подключение geosite/geoip mount-ов к Node.
- Вынос node logs на host filesystem с `logrotate`.
- Передача TLS certificate files в Node через Panel workflow.

## Ошибки

- Открыть `NODE_PORT` во внешний интернет.
- Монтировать весь каталог `/usr/local/share/xray/`, перезаписывая дефолтные geosite/geoip files.
- Подключить logs без log rotation.
- Считать, что server-side routing влияет на клиентские `DIRECT` connections.
- Игнорировать `Consumption` multiplier и неверно интерпретировать фактический расход user traffic.
- Не использовать `Copy Node UUID`, когда нужен stable node identifier для API operations.

## Проверка результата

- Node отображается в `Nodes -> Management`.
- Для Node выбран нужный `Config Profile`.
- `docker compose logs -f -t` на node server не показывает постоянных ошибок.
- `NODE_PORT` доступен только с IP Panel.
- `Actions` block доступен и выполняет `Update`/`Restart all nodes`.
- `More actions` показывает как минимум `Show usage`, `Copy Node UUID`, `Disable`, `Delete`.
- При необходимости настроены `Consumption` и `Tracking & Billing`.

## Ссылки

- [references/components.md](references/components.md)
- [references/node-install.md](references/node-install.md)
- [references/nodes-guide.md](references/nodes-guide.md)
- [references/official-links.md](references/official-links.md)

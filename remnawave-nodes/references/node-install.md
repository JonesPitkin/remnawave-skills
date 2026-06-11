# Remnawave Node Installation

Источник:

- `https://docs.rw/docs/install/remnawave-node/`

## Подтвержденные шаги

- Node includes `Xray-core`.
- Panel does not include `Xray-core`.
- Создать каталог:
  - `mkdir /opt/remnanode && cd /opt/remnanode`
- В Panel добавить node через `Nodes -> Management`.
- Взять `docker-compose.yml` из кнопки `Copy docker-compose.yml`.
- Создать локальный `docker-compose.yml`.
- Запустить:
  - `docker compose up -d && docker compose logs -f -t`
- После этого завершить создание Node через выбор `Config Profile`.

## Важные замечания

- `Node Port` нужен для internal API requests от Panel.
- Docs просят закрыть `NODE_PORT` firewall-правилом, разрешив его только для IP Panel.
- Docs также отмечают, что после создания Node Panel в течение нескольких секунд подключается к нему и запускает `Xray-core`.

## Advanced Usage

Docs дополнительно описывают:

- mount отдельных `geoip/geosite` files;
- mount node logs на host и настройку `logrotate`;
- работу с Xray SSL certs через Panel volume path `/var/lib/remnawave/configs/xray/ssl/`.

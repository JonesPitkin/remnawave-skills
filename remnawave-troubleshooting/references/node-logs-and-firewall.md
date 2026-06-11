# Node Logs And Firewall

Источник:

- `https://docs.rw/docs/install/remnawave-node/`

## Подтвержденные проверки

- `NODE_PORT` должен быть открыт только для IP Panel.
- Node logs можно монтировать на host filesystem.
- Для logs требуется `logrotate`, иначе они заполнят диск.

## Полезные команды

- `docker compose logs -f -t`
- `mkdir -p /var/log/remnanode`
- `sudo apt update && sudo apt install logrotate`
- `logrotate -vf /etc/logrotate.d/remnanode`

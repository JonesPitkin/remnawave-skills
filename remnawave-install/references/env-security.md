# Environment And Security

Источники:

- `https://docs.rw/docs/install/environment-variables/`
- `https://docs.rw/docs/install/reverse-proxies/`
- `https://docs.rw/docs/install/panel-security/`

## Environment Variables

- При изменении environment variables нужно пересоздать контейнеры:
  - `docker compose down && docker compose up -d`
- Remnawave uses PostgreSQL URL in `DATABASE_URL`.
- Секреты должны быть сильными, длиной не менее `64` символов.

## Reverse Proxy

- Remnawave не поддерживает публикацию на sub-path.
- Нужно обслуживать сервис на root path домена или subdomain.
- SSH Port Forwarding не поддерживается как рекомендуемая схема.
- Для production docs предлагают reverse proxy варианты:
  - `Caddy`
  - `Nginx`
  - `Traefik`
  - `Angie`
- `Try Cloudflare` отмечен как development-only и не для production.

## Panel Security

Официальная security page подтверждает дополнительные способы защиты через:

- `Caddy with minimal setup`
- `Caddy with custom path`
- `Cloudflare ZeroTrust`
- `TinyAuth for Nginx`

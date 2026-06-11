# Subscription Overview

Источник:

- `https://docs.rw/docs/learn-en/templates/`

## Подтвержденное поведение

- Один и тот же `Subscription URL` может отдавать разные ответы.
- Browser получает human-readable page.
- Client application получает subscription в подходящем формате.
- Remnawave автоматически определяет тип клиента.

## Основные format families

- `Mihomo`
- `Xray-json`
- `Sing-box`
- `Base64`

`Base64` используется как fallback, если client app не совпал с более специфичной family.

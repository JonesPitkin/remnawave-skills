# Subscription Pipeline

Источники:

- `https://docs.rw/docs/learn-en/quick-start/`
- `https://docs.rw/docs/learn-en/users/`
- `https://docs.rw/docs/learn-en/hosts/`
- `https://docs.rw/docs/learn-en/templates/`
- `https://docs.rw/docs/learn-en/squads/`

## Официально подтвержденная цепочка

1. После создания user можно получить `Subscription URL`.
2. При открытии в browser пользователь видит `Subscription Page`.
3. При открытии из client app Remnawave определяет client type и выдает подходящий config format.
4. `Hosts` определяют gateway к Nodes и конкретный inbound binding.
5. `Templates` определяют family-specific config payload.
6. `Subscription -> Settings` добавляет supported metadata.
7. `External Squads` могут переопределять Templates и subscription-side settings.
8. `Response Rules` участвуют в том, как именно формируется ответ для client apps.

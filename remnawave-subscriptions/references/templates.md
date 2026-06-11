# Templates

Источник:

- `https://docs.rw/docs/learn-en/templates/`

## Подтвержденные факты

- `Templates` section определяет, что получает client app.
- Since `2.2.0`, можно создавать несколько templates для каждого core family.
- Для управления выдачей templates docs предлагают:
  - `External Squads`
  - `Routing Rules`

## Families

- `Mihomo`
- `Xray-json`
- `Sing-box`
- `Base64`

## Важное ограничение

Docs не дают здесь универсальной матрицы “какой именно client получает какой template по каждому user-agent”. Поэтому конкретное client matching behavior нужно проверять по официальной документации и самому Panel runtime.

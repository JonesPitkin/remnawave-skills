# Templates

Источник:

- `https://docs.rw/docs/learn-en/templates/`

## Подтвержденные факты

- `Templates` section определяет, что получает client app.
- Since `2.2.0`, можно создавать несколько templates для каждого core family.
- Для управления выдачей templates docs предлагают:
  - `External Squads`
  - `Routing Rules`

## Разграничение

- `Templates` отвечают за family-specific config output.
- `Routing Rules` в этом контексте относятся к subscription/template delivery logic.
- Это не то же самое, что `Server-Side Routing` для node-side traffic path.

## Families

- `Mihomo`
- `Xray-json`
- `Sing-box`
- `Base64`

## Важное ограничение

Docs не дают здесь универсальной матрицы “какой именно client получает какой template по каждому user-agent”. Поэтому конкретное client matching behavior нужно проверять по официальной документации и самому Panel runtime.

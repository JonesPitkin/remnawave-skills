# Activation Chain

Источники:

- `https://docs.rw/docs/learn-en/config-profiles/`
- `https://docs.rw/docs/learn-en/hosts/`

## Официально подтвержденная цепочка

Чтобы новый inbound реально дошел до пользователя, docs описывают такую последовательность:

1. Создать или изменить `Config Profile`.
2. Назначить профиль на `Node`.
3. Включить нужные `Inbounds` на этом Node.
4. На `Host` назначить конкретный inbound из профиля.
5. В `Internal Squad` включить этот inbound.

Если последний шаг пропущен, пользователь не получит доступ к новому inbound даже при корректных Node и Host настройках.

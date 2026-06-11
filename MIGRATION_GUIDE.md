# Migration Guide

## From the old baseline

Старая версия `remnawave-skills` содержала только один router skill и минимальные official links.

Теперь source of truth в этом репозитории включает полноценный skill tree:

- install
- users
- nodes
- config profiles
- subscriptions
- happ routing
- api
- troubleshooting

## Migration rule for downstream bundles

Если репозиторий встраивается в `nidox-vpn-skills` или иной meta-repository:

- синхронизировать весь каталог `remnawave-skills/` целиком;
- не вырезать `references/`;
- не подменять official-source policy неофициальными гидами.

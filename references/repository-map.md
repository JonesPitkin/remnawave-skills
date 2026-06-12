# Repository Map

Этот файл является внутренним служебным исключением. Он не является внешним источником знаний о Remnawave и используется только как локальная карта репозитория.

## Главный вход

- [../SKILL.md](../SKILL.md) - корневой standalone entrypoint
- [../README.md](../README.md) - обзор репозитория
- [../SKILL_INDEX.md](../SKILL_INDEX.md) - индекс модулей

## Router compatibility layer

- [../remnawave/SKILL.md](../remnawave/SKILL.md) - совместимый router skill, сохраненный для обратной совместимости и явной маршрутизации внутри семейства skills

## Specialist modules

- [../remnawave-install/SKILL.md](../remnawave-install/SKILL.md)
- [../remnawave-users/SKILL.md](../remnawave-users/SKILL.md)
- [../remnawave-subscriptions/SKILL.md](../remnawave-subscriptions/SKILL.md)
- [../remnawave-nodes/SKILL.md](../remnawave-nodes/SKILL.md)
- [../remnawave-api/SKILL.md](../remnawave-api/SKILL.md)
- [../remnawave-config-profiles/SKILL.md](../remnawave-config-profiles/SKILL.md)
- [../remnawave-happ-routing/SKILL.md](../remnawave-happ-routing/SKILL.md)
- [../remnawave-troubleshooting/SKILL.md](../remnawave-troubleshooting/SKILL.md)

## Что это дает

- корневой `SKILL.md` становится явным entrypoint standalone-репозитория;
- specialist skills остаются отдельными модулями;
- старый `remnawave/` router сохраняется без удаления и без потери совместимости.

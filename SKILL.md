---
name: remnawave-skills
description: "Главный entrypoint standalone-репозитория по Remnawave. Использовать для маршрутизации задач по установке Panel и Node, работе с Users, Subscriptions, Config Profiles, Happ Routing, REST API и troubleshooting только по официальной документации docs.rw и github.com/remnawave."
---

# remnawave-skills

Этот `SKILL.md` является главным entrypoint репозитория. Использовать его как общий вход в задачи по Remnawave, когда нужно быстро определить нужный specialist module и сохранить source-backed подход.

## Как работать с этим skill

1. Определить рабочий домен: install, users, nodes, subscriptions, config profiles, Happ Routing, API или troubleshooting.
2. Зафиксировать version-sensitive контекст:
   - какой release или generation Panel используется;
   - где размещены Panel и Node;
   - есть ли reverse proxy;
   - требуется ли UI workflow или REST API workflow.
3. Перейти в профильный skill и не додумывать неподтвержденные функции, параметры или шаги UI.
4. Если задача общая и еще не локализована, использовать [remnawave/SKILL.md](./remnawave/SKILL.md) как совместимый router skill внутри репозитория.

## Роль entrypoint

- быть главным корневым входом standalone-репозитория;
- маршрутизировать запрос в нужный тематический модуль;
- не дублировать полностью содержание specialist skills;
- удерживать единый стандарт работы только по официальным источникам Remnawave;
- учитывать обязательные и рекомендуемые skill dependencies;
- использовать [README.md](./README.md) и [SKILL_INDEX.md](./SKILL_INDEX.md) как карту репозитория.

## Быстрая навигация

- [README.md](./README.md) - обзор репозитория и карта модулей
- [SKILL_INDEX.md](./SKILL_INDEX.md) - индекс всех skills
- [SKILL_DEPENDENCIES.md](./SKILL_DEPENDENCIES.md) - required/recommended dependencies
- [VERSION_MATRIX.md](./VERSION_MATRIX.md) - version-sensitive policy
- [remnawave/SKILL.md](./remnawave/SKILL.md) - совместимый router skill
- [remnawave-install/SKILL.md](./remnawave-install/SKILL.md) - установка Panel, `.env`, reverse proxy, security baseline
- [remnawave-users/SKILL.md](./remnawave-users/SKILL.md) - Users, quotas, actions и access lifecycle
- [remnawave-nodes/SKILL.md](./remnawave-nodes/SKILL.md) - Node deployment, binding и node-side operation
- [remnawave-subscriptions/SKILL.md](./remnawave-subscriptions/SKILL.md) - subscriptions, templates, response rules, pipeline
- [remnawave-config-profiles/SKILL.md](./remnawave-config-profiles/SKILL.md) - Config Profiles, activation chain и Xray integration
- [remnawave-happ-routing/SKILL.md](./remnawave-happ-routing/SKILL.md) - Happ Routing в подтвержденных границах docs
- [remnawave-api/SKILL.md](./remnawave-api/SKILL.md) - API tokens, docs, controller workflow и examples
- [remnawave-troubleshooting/SKILL.md](./remnawave-troubleshooting/SKILL.md) - install/runtime diagnostics
- [references/sources.md](./references/sources.md) - корневой список официальных источников

## Разделы репозитория

- `remnawave-install` - установка и первичная подготовка Panel
- `remnawave-users` - жизненный цикл Users
- `remnawave-subscriptions` - subscription delivery и related controls
- `remnawave-nodes` - Node deployment и эксплуатация
- `remnawave-api` - REST API и operational guidance
- `remnawave-config-profiles` - Config Profiles и Xray-related activation logic
- `remnawave-happ-routing` - Happ Routing в официально описанном объеме
- `remnawave-troubleshooting` - диагностика install, runtime и exposure issues

## Зависимости

Required:

- [../network-fundamentals-skill/README.md](../network-fundamentals-skill/README.md)
  Обязательная базовая зависимость для DNS, routing, MTU, reverse proxy, firewall, TLS и Linux networking.

Recommended:

- [../nidox-vpn-detection-defense-skill/README.md](../nidox-vpn-detection-defense-skill/README.md)
  Рекомендуемый аудиторский слой для проверки detection surface, publication mistakes и VPN-hardening рисков.

## Рабочий порядок маршрутизации

```text
remnawave task
  -> classify scope
    -> confirm official source
      -> choose specialist module
        -> check version-sensitive behavior
          -> apply only documented workflow
```

## Правила качества

- Использовать только `docs.rw` и `github.com/remnawave` как источники фактов.
- Если функция, endpoint, UI control или operational behavior не подтверждены, явно отмечать отсутствие подтверждения.
- Не смешивать install, API и subscription workflows в один непроверенный ответ.
- Для production-sensitive задач учитывать reverse proxy, exposure model и release-specific behavior.

## Ссылки

- [README.md](./README.md)
- [SKILL_INDEX.md](./SKILL_INDEX.md)
- [SKILL_DEPENDENCIES.md](./SKILL_DEPENDENCIES.md)
- [references/repository-map.md](./references/repository-map.md)
- [references/standalone-compatibility.md](./references/standalone-compatibility.md)

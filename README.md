# remnawave-skills

![Remnawave logo](https://github.com/remnawave.png)

`remnawave-skills` — публичный репозиторий NIDOX Skills для source-backed работы с Remnawave только по официальным материалам `docs.rw` и `github.com/remnawave`.

Репозиторий нужен для того, чтобы Codex уверенно и без домыслов работал с:

- установкой Remnawave Panel;
- установкой и подключением Remnawave Node;
- управлением Users;
- управлением Subscription URL, Templates и Subscription Page;
- созданием и активацией Config Profiles;
- управлением Hosts;
- работой с Happ Routing в пределах того, что подтверждено официальной документацией;
- работой с REST API;
- диагностикой и безопасной эксплуатацией панели;
- интеграцией с Xray-core через Config Profiles и Node workflows.

## Важное предупреждение

Этот репозиторий использует только официальные источники:

- [docs.rw](https://docs.rw)
- [Introduction](https://docs.rw/docs/overview/introduction/)
- [Components](https://docs.rw/docs/overview/components/)
- [Quick Start](https://docs.rw/docs/overview/quick-start/)
- [Requirements](https://docs.rw/docs/install/requirements/)
- [Remnawave Panel](https://docs.rw/docs/install/remnawave-panel/)
- [Initial Setup](https://docs.rw/docs/learn-en/quick-start/)
- [API Documentation](https://docs.rw/api/)
- [GitHub Organization](https://github.com/remnawave)

Если в официальной документации нет подтверждения для конкретного поведения, поля, API-эндпоинта или шага UI, в skill-файлах это отмечается явно.

## Доступные skills

- [`remnawave`](remnawave/SKILL.md)
  Совместимый entrypoint/router для маршрутизации задачи к нужному specialist skill.
- [`remnawave-install`](remnawave-install/SKILL.md)
  Установка Panel, базовая подготовка `.env`, reverse proxy, security baseline.
- [`remnawave-users`](remnawave-users/SKILL.md)
  Создание и управление Users, лимиты, access settings, user actions.
- [`remnawave-nodes`](remnawave-nodes/SKILL.md)
  Установка Remnawave Node, привязка к Panel, Xray-related node practices.
- [`remnawave-config-profiles`](remnawave-config-profiles/SKILL.md)
  Создание Config Profiles и активация Inbounds на Nodes, Hosts и Squads.
- [`remnawave-subscriptions`](remnawave-subscriptions/SKILL.md)
  Subscription URL, Templates, Hosts, Subscription Page, API token flow.
- [`remnawave-happ-routing`](remnawave-happ-routing/SKILL.md)
  Работа с Happ Routing только в границах официально подтвержденных материалов.
- [`remnawave-api`](remnawave-api/SKILL.md)
  API Tokens, включение docs, Swagger/Scalar и source-backed API workflow.
- [`remnawave-troubleshooting`](remnawave-troubleshooting/SKILL.md)
  Диагностика install/runtime issues, Node logs, env changes, panel exposure.

## Структура проекта

```text
remnawave-skills/
├── README.md
├── LICENSE
├── CHANGELOG.md
├── CONTRIBUTING.md
├── GITHUB_REPOSITORY.md
├── MIGRATION_GUIDE.md
├── RELEASE_v1.0.0.md
├── SKILL_INDEX.md
├── VERSION_MATRIX.md
├── remnawave/
│   ├── SKILL.md
│   ├── agents/
│   └── references/
├── remnawave-install/
│   ├── SKILL.md
│   ├── agents/
│   └── references/
├── remnawave-users/
│   ├── SKILL.md
│   ├── agents/
│   └── references/
├── remnawave-nodes/
│   ├── SKILL.md
│   ├── agents/
│   └── references/
├── remnawave-config-profiles/
│   ├── SKILL.md
│   ├── agents/
│   └── references/
├── remnawave-subscriptions/
│   ├── SKILL.md
│   ├── agents/
│   └── references/
├── remnawave-happ-routing/
│   ├── SKILL.md
│   ├── agents/
│   └── references/
├── remnawave-api/
│   ├── SKILL.md
│   ├── agents/
│   └── references/
└── remnawave-troubleshooting/
    ├── SKILL.md
    ├── agents/
    └── references/
```

## Требования к версиям Remnawave

- Официальный `Initial Setup` guide прямо указывает, что он написан для `Panel version 2.0 and newer`.
- Этот репозиторий не фиксирует собственную “истину” по всем версиям Remnawave и требует перепроверки version-specific поведения по актуальным официальным источникам.
- По состоянию на `2026-06-11` официальный GitHub organization `remnawave` показывает активные публичные репозитории `panel`, `backend`, `frontend`, `node`, `subscription-page`, `xtls-sdk`, `migrate`, `python-sdk` и другие.

Практическое правило:

- если задача зависит от конкретного UI, поля в форме, API schema или runtime behavior, сверять текущие official docs и актуальный GitHub state перед production-изменениями;
- если нужная функция не описана явно, не считать её подтвержденной.

## Официальная документация

- [Remnawave Documentation](https://docs.rw)
- [Introduction](https://docs.rw/docs/overview/introduction/)
- [Components](https://docs.rw/docs/overview/components/)
- [Quick Start](https://docs.rw/docs/overview/quick-start/)
- [Requirements](https://docs.rw/docs/install/requirements/)
- [Remnawave Panel Installation](https://docs.rw/docs/install/remnawave-panel/)
- [Initial Setup](https://docs.rw/docs/learn-en/quick-start/)
- [API Documentation](https://docs.rw/api/)
- [GitHub Organization](https://github.com/remnawave)

## Политика источников

- Не использовать сторонние статьи, форумы и неофициальные гайды как источник фактов.
- Не придумывать API methods, panel controls, Xray integration steps или Happ behavior.
- Если в разрешенных официальных источниках не хватает деталей, skill должен прямо сказать об этом и остановиться на source-backed выводе.

## GitHub readiness

Репозиторий подготовлен к публикации:

- есть MIT License;
- есть skill tree и локальные `references/`;
- есть `agents/openai.yaml` для каждого skill;
- есть index/migration/release metadata;
- история коммитов структурирована под первый push в `origin`.

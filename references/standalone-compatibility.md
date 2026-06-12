# Standalone Compatibility

Этот файл является внутренним служебным исключением. Он не является внешним источником знаний о Remnawave и используется только для проверки структуры standalone-репозитория.

`remnawave-skills` приведен к publish-ready формату standalone skill repository по тому же принципу, который используется в `network-fundamentals-skill`.

## Проверяемые элементы

- корневой [../SKILL.md](../SKILL.md) как главный entrypoint;
- корневой [../agents/openai.yaml](../agents/openai.yaml);
- корневой каталог `references/`;
- корневые metadata-файлы `README.md`, `SKILL_INDEX.md`, `VERSION_MATRIX.md`, `CHANGELOG.md`, `CONTRIBUTING.md`, `RELEASE_v1.0.0.md`;
- отдельные тематические modules со своими `SKILL.md`, `agents/openai.yaml` и `references/`.

## Совместимость

- формат совместим с Codex Skill Format как standalone repository entry;
- specialist modules не удалены и не объединены;
- knowledge base остается source-backed и ограниченной официальными материалами Remnawave;
- внутренний router `remnawave/` сохранен как compatibility layer.

---
name: remnawave-config-profiles
description: Создавать Config Profiles в Remnawave, активировать Inbounds на Nodes и связывать их с Hosts и Squads только в рамках официальной документации.
---

# Remnawave Config Profiles

## Назначение

Этот skill покрывает создание Config Profiles, базовую работу с Inbounds и цепочку активации профиля на Node, Host и Squad.

## Теория

Официальная документация определяет `Config Profile` как полный Xray-core configuration template для Node. Профиль содержит Inbounds и общие настройки, которые Node должен использовать.

Docs одновременно предупреждают:

- статья не обучает самой настройке `Xray-core`;
- за syntax/behavior Xray нужно обращаться к official Xray docs.

## Практика

1. Открыть `Config Profiles` и нажать `Create Config Profile`.
2. Ввести имя профиля.
3. В открывшемся editor:
   - добавить или удалить `Inbounds`;
   - скорректировать остальные Xray settings.
4. При необходимости использовать `Load from GitHub` для шаблона.
5. Сохранить профиль и вернуться в список.
6. На Node открыть `Change Profile`, выбрать новый профиль и включить нужные `Inbounds`.
7. На `Hosts` назначить конкретные `Inbounds` из этого профиля.
8. На `Internal Squads` включить эти же `Inbounds`, иначе Users не получат доступ.

## Типовые сценарии

- Создать profile `Sample` и добавить второй `VLESS` inbound.
- Активировать новый профиль на существующем Node.
- Расширить доступ пользователей к новым inbound через `Default-Squad`.

## Ошибки

- Считать Config Profile самодостаточным без назначения на Node.
- Назначить inbound на Host, но забыть включить его в `Internal Squad`.
- Использовать guide как замену полной документации `Xray-core`.

## Проверка результата

- Новый профиль появился в списке `Config Profiles`.
- У профиля корректно отображается число `Inbounds`.
- На Node активирован нужный профиль.
- На Host доступен нужный inbound.
- В `Internal Squad` inbound тоже включен.

## Ссылки

- [references/config-profiles.md](references/config-profiles.md)
- [references/activation-chain.md](references/activation-chain.md)
- [references/official-links.md](references/official-links.md)

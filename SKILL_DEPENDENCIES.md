# Skill Dependencies

## Required

- [`network-fundamentals-skill`](../network-fundamentals-skill/README.md)
  Базовая обязательная зависимость для сетевых концепций, DNS, routing, MTU, reverse proxy, TLS, firewall и Linux networking, без которых нельзя качественно проектировать и диагностировать Remnawave deployment.

## Recommended

- [`nidox-vpn-detection-defense-skill`](../nidox-vpn-detection-defense-skill/README.md)
  Рекомендуемый аудиторский слой для дополнительной проверки следов VPN detection, поведенческих рисков, ошибок публикации и operational hardening вокруг VPN-инфраструктуры.

## Dependency Policy

- `network-fundamentals-skill` считать обязательным базовым слоем перед сложной диагностикой сети, reverse proxy, exposure, routing и Node connectivity.
- `nidox-vpn-detection-defense-skill` подключать как рекомендованный аудит-слой перед production publication, security review и post-incident assessment.
- Эти зависимости не заменяют официальную документацию Remnawave и не являются источниками фактов о самом продукте.

# Politique de sécurité

## Versions prises en charge

Seule la dernière version publiée sur la page [Releases](https://github.com/r97sgkjtdh-ops/constellation/releases/latest) reçoit des correctifs. L'app propose elle-même chaque nouvelle version : garde-la à jour.

## Signaler une faille

**Ne publie pas de faille dans une issue publique.**

Utilise le signalement privé de GitHub : onglet **Security**, puis **Report a vulnerability**. Le signalement n'est visible que par le mainteneur.

Indique si possible :

- la version de Constellation (Réglages › À propos) et celle de macOS ;
- ce que la faille permet de faire, et dans quelles conditions ;
- les étapes pour la reproduire.

Tu recevras une première réponse sous 7 jours. Une fois la faille corrigée et la nouvelle version publiée, le signalement pourra être rendu public, avec ton accord, en te créditant si tu le souhaites.

## Ce qui protège déjà l'app

- Les mises à jour ne sont installées que si leur **signature Ed25519** correspond à la clé intégrée à l'application, et seulement depuis les serveurs de GitHub.
- L'app ne conserve aucun identifiant : les comptes restent gérés par Claude Code et les autres outils.
- Aucune donnée n'est envoyée à un serveur de Constellation : il n'en existe pas.

# Donner des ordres aux consoles

*[English version](orders.md)*

La barre de commande (⌘K) envoie un ordre à une ou plusieurs consoles du tableau. Une carte orchestrateur fait de même, mais seulement pour les consoles et les groupes qui lui sont reliés.

## Les quatre façons d'écrire un ordre

| Tu écris | Ce qui se passe |
|---|---|
| `Claude 2, ajoute des tests au parseur` | Le nom d'une console, puis une virgule : le texte part tel quel à cette console. |
| `@Claude 2 ajoute des tests` | La même chose avec `@`, à n'importe quel endroit de la phrase. |
| `@Équipe A tous : relis ton dernier commit` | `tous :` envoie le même texte à chaque console du groupe ou des consoles nommées. |
| `Ajoute une page de connexion et ses tests` | Sans nom : le planificateur répartit le travail entre les consoles, et te montre un plan avant d'envoyer quoi que ce soit. |

Si deux consoles ou groupes portent le même nom, l'ordre est refusé : précise le nom exact avec `@`.

## Commandes du tableau

Ces phrases sont traitées par Constellation, sans planificateur :

- `crée 4 agents Codex` (ou `lance`, `ouvre`, `ajoute`) : crée des consoles, 12 au plus ;
- `ouvre l'espace 2` : affiche un autre espace ;
- `passe cette tâche à codex` : la console sélectionnée résume son travail, et une nouvelle console du CLI choisi le reprend.

## Le plan

Sans nom de console, le planificateur (un appel à Claude Code, sans outils) propose des étapes : une consigne par console. **Rien n'est envoyé avant que tu cliques sur « Envoyer ce plan ».** D'ici là, tu peux :

- changer la console d'une étape, ou sa consigne ;
- retirer une étape, ou en ajouter une ;
- choisir ce qu'une étape attend (« Après … ») : elle part quand ces étapes sont finies, avec leurs comptes rendus ;
- cocher « Compte rendu final, après les autres » sur une seule étape.

Un plan dont les attentes forment une boucle est refusé. Une console lancée sans permissions est signalée en orange : elle agira sur ce qu'elle reçoit sans rien te demander.

## L'étape finale

L'étape finale attend toutes les autres. Elle reçoit leurs comptes rendus complets, dans un fichier `.constellation/comptes-rendus-….md` du dossier de sa console. Ce fichier reste hors de Git et disparaît au bout de 7 jours. Les autres consoles sont prévenues que leur compte rendu sera transmis.

Si une étape n'a pas abouti (échec, délai dépassé, console arrêtée), l'étape finale attend ton accord : « Lancer l'étape finale quand même », ou annuler.

Les comptes rendus transmis sont présentés à la console comme des données à résumer, pas des instructions, et les secrets reconnus y sont masqués.

## Les états d'une étape

| État | Sens |
|---|---|
| en file, attend le démarrage | Pas encore envoyée. |
| attend la fin des autres consoles | Une étape finale, ou une étape qui en attend d'autres. |
| attend que la console finisse un autre ordre | La console travaille déjà sur un autre ordre : celle-ci passe après. |
| attend ton intervention | La console demande une permission ou pose une question. |
| envoyé, en cours | L'agent travaille. |
| terminé | L'agent a fini son tour ; son compte rendu est joint. |
| délai dépassé, console arrêtée, interrompu | Fini sans compte rendu complet : ce qui a été lu est gardé, et marqué partiel. |
| échec | Erreur de l'API (limite, surcharge, réseau) : la console affiche TOUR ÉCHOUÉ. |
| non envoyé | La console n'était pas prête (en pause, shell, permission en attente…). |

Une étape finie, en échec ou non envoyée se **relance** : sur la même console ou une autre. **Annuler** un ordre arrête aussi les agents qui travaillent dessus, comme Échap, et garde leur compte rendu partiel.

Les ordres restent après un redémarrage de l'app. Ce qui tournait à la fermeture est marqué interrompu, et se relance. « Effacer » les retire du fil sans les supprimer.

## Limites

- Le délai d'une étape est de 30 minutes, sans compter le temps passé à attendre ta réponse à une permission.
- Pour les CLI autres que Claude Code, la fin d'un tour est devinée après 6 secondes sans sortie, et le compte rendu est la fin de l'écran.
- Le planificateur a besoin de Claude Code, et met jusqu'à 3 minutes.

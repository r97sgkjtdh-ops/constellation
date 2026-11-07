<p align="center">Français · <a href="README.en.md">English</a></p>

<p align="center">
  <img src="docs/images/icon.png" width="128" alt="Icône de Constellation">
</p>

<h1 align="center">Constellation</h1>

<p align="center">
  <strong>Un espace de travail pour macOS qui réunit tes agents IA sur un même tableau,<br>
  pour coder, chercher, écrire ou analyser, et confie une demande à un coordinateur qui la répartit et en contrôle le résultat.</strong>
</p>

<p align="center">
  <img alt="macOS 14 ou plus récent" src="https://img.shields.io/badge/macOS-14%2B-black?logo=apple">
  <img alt="Apple Silicon et Intel" src="https://img.shields.io/badge/Mac-Apple%20Silicon%20%7C%20Intel-555">
  <img alt="Licence propriétaire, usage gratuit" src="https://img.shields.io/badge/licence-propri%C3%A9taire%2C%20gratuite-lightgrey">
  <a href="https://github.com/r97sgkjtdh-ops/constellation/releases/latest"><img alt="Dernière version" src="https://img.shields.io/github/v/release/r97sgkjtdh-ops/constellation?label=version"></a>
</p>

<p align="center">
  <img src="docs/images/home.png" alt="L'accueil : plusieurs projets, le bouton Nouvelle mission et le fond en réseau">
</p>

<p align="center">
  <img src="docs/images/board-mission.png" alt="Une mission sur le tableau : la carte du coordinateur, des sous-agents sur plusieurs niveaux et les jauges de chaque carte">
</p>

<p align="center"><sub>Captures de l'app, avec des données d'exemple.</sub></p>

> **Nouveau dans les 0.3.31 et 0.3.32** : une fenêtre de consommation refaite (quota en jauges) ; des Réglages refaits (barre latérale avec recherche, notifications par type, tableau, données, crédits) ; des rôles qui changent vraiment le comportement des consoles Claude Code ; six modèles de mission ; l'historique des ordres ; l'alerte quand deux consoles modifient le même fichier ; des notifications signées Constellation. [Toutes les nouveautés](CHANGELOG.md)

---

## Sommaire

- [Présentation](#présentation)
- [Fonctionnalités](#fonctionnalités)
- [Configuration requise](#configuration-requise)
- [Installation](#installation)
- [Premier lancement et compte Claude](#premier-lancement-et-compte-claude)
- [Abonnement, quotas et coûts](#abonnement-quotas-et-coûts)
- [Prise en main](#prise-en-main)
- [Les missions en détail](#les-missions-en-détail)
- [Raccourcis clavier](#raccourcis-clavier)
- [Mises à jour](#mises-à-jour)
- [Données et confidentialité](#données-et-confidentialité)
- [Désinstallation](#désinstallation)
- [Dépannage](#dépannage)
- [Guides](#guides)
- [Questions fréquentes](#questions-fréquentes)
- [État du projet et limites connues](#état-du-projet-et-limites-connues)
- [Signaler un problème](#signaler-un-problème)
- [Licence](#licence)

## Présentation

Les agents IA en ligne de commande (Claude Code, Codex, Gemini CLI, OpenCode…) sont puissants et ne servent pas qu'à programmer : chercher sur le web et citer ses sources, rédiger ou relire un texte, traduire, analyser des données, organiser un plan. Mais on les utilise chacun dans un terminal, sans vue d'ensemble. Constellation les pose sur un **tableau infini**, à côté de tes notes, de tes fichiers, de ton navigateur et de ton dépôt Git, et te permet de les faire travailler ensemble.

Sa fonction centrale est la **mission**, pour tous les sujets. Tu écris une demande, un coordinateur la découpe en tâches, des sous-agents les réalisent, et le résultat est contrôlé avant d'être déclaré réussi. Les agents peuvent chercher sur le web (case cochée par défaut pour un nouveau dossier, décochée pour un projet existant) et écrire des fichiers (texte, tableur, page, code) dans le dossier de travail. Cette version ne génère pas d'images ni de vidéos. Tu peux confier des connecteurs à tes agents, à ton choix (voir [Connecteurs](#connecteurs)).

La preuve a trois niveaux, affichés tels quels :
- **Vérifiée par commandes** : Constellation a exécuté elle-même des commandes de contrôle, et leur résultat prouve le travail. C'est le niveau le plus solide.
- **Validée par relecture** : quand aucune commande ne peut prouver le résultat (un texte, une recherche), une session séparée juge chaque critère.
- **Vérifiée par commandes et relue** : les commandes ont réussi et la revue indépendante, activée par défaut (tu peux la décocher à la création d'une mission), a aussi approuvé le travail.

Une relecture réduit les erreurs, mais ne garantit rien : relis toi-même ce qui compte. Elle consomme aussi plus de quota, car elle ajoute des sessions.

Constellation est une application native (Swift et SwiftUI). Elle n'a pas de serveur ni de compte à elle : elle pilote les outils installés sur ton Mac, avec **tes propres comptes**.

## Fonctionnalités

### Tableau et espaces
- Tableau infini avec zoom de 20 à 300 % (paliers de ×1,25 jusqu'à 100 %), sélection multiple, repères d'alignement, copier-coller et annulation sur 80 étapes.
- Projets reliés à un dossier, et espaces en onglets : les consoles continuent de tourner en arrière-plan.
- Sauvegarde automatique, version précédente, instantanés horaires et archive.
- Notes colorées, checklists, kanbans, calendrier, formes et flèches au rendu dessiné à la main, stylo et gomme.
- Images annotables, et fichiers ou dossiers déposés depuis le Finder.
- **Se déplacer sur le tableau** : deux doigts ou la molette le font glisser dans tous les sens, et une carte ne défile qu'après un clic dans la carte. Le pincement et ⌘ + molette zooment autour du pointeur ; le glisser au clic droit déplace aussi le tableau, et un léger rebond marque les bords. Les boutons + et − zooment par paliers.
- **Fond vivant** : un réseau animé en arrière-plan donne vie à l'accueil et au tableau. « Réduire les animations » le fige.
- **Tâches de mission déplaçables** : sur le tableau, glisse les tâches d'une mission (et leurs sous-agents) pour les ranger comme tu veux. Elles suivent la carte du coordinateur, et un clic droit les remet en place automatiquement.
- **Barres de progression** pour l'agent de chaque console Claude Code et pour chacun de ses sous-agents : la liste de tâches de l'agent (2/5 tâches et la tâche en cours) quand il en tient une, sinon le nombre d'étapes (chaque outil utilisé) et le temps passé. Sans liste de tâches, la barre est une estimation : elle n'arrive au bout qu'une fois le travail fini.

### Consoles et agents
- Vrais terminaux (PTY) : Ctrl-C, interfaces en plein écran, couleurs 256 et truecolor, 10 000 lignes d'historique.
- Catalogue d'environ 25 CLI détectés automatiquement (Claude Code, Codex, Gemini, OpenCode…), plus tes agents personnalisés.
- Pause, reprise, redémarrage, duplication et changement de CLI. La conversation précédente est reprise quand le CLI le permet.
- État de chaque console (au travail, en attente d'autorisation, tour échoué, terminé…), précis pour Claude Code grâce à ses hooks. Une console au travail sans aucun signe depuis 10 minutes est signalée « Bloquée ? ».
- Notifications macOS quand l'app est en arrière-plan, et nombre de consoles qui t'attendent sur l'icône du Dock. Un clic sur le compteur de consoles les liste toutes ; ⌘P va à une carte.
- Profils séparés pour Claude Code (`CLAUDE_CONFIG_DIR`) et Codex (`CODEX_HOME`).

### Coordination
- **Groupes** nommés et colorés, avec des rôles (frontend, backend, tests, revue, documentation, sécurité…). Pour Claude Code, un rôle donne une consigne de départ, et Revue et Sécurité travaillent en lecture seule.
- **Barre de commande** (⌘K) : mentions `@console` et `@groupe`, ordres en langage naturel (« crée 4 agents Codex ») et plan modifiable, validé avant l'envoi, avec étapes qui s'attendent et compte rendu final. Guides : [donner des ordres](docs/ordres.md), [rôles et équipes](docs/roles-et-equipes.md), [exemples](docs/exemples.md).
- **Relais** : handoff vers une nouvelle console avec un résumé, et transfert de réponses d'une console à d'autres.
- **Boucles** : une consigne relancée à intervalle régulier ou à chaque fin de tour, jusqu'à un objectif vérifié (code de sortie ou verdict).
- **Mémoire** partagée du projet, construite par une lecture du code en lecture seule et transmise aux consoles.

<p align="center">
  <img src="docs/images/orders.png" width="640" alt="Un ordre à quatre consoles : le plan modifiable, une étape qui attend Claude 1, l'étape finale ; en dessous, un ordre en cours avec une étape terminée, une en échec et l'étape finale qui attend ton accord">
</p>
<p align="center">
  <img src="docs/images/consoles.png" width="440" alt="La liste des consoles : besoin de toi, tour échoué, au travail, prête">
</p>

### Missions
- Un coordinateur en lecture seule propose un plan, validé avant toute exécution.
- Des sous-agents travaillent dans ton dossier ou chacun dans un **worktree Git** isolé.
- Des contrôles exécutés par Constellation, des corrections rédigées par le coordinateur et une revue indépendante, activée par défaut.
- Une intégration tout ou rien, puis le contrôle de l'ensemble.
- Une délégation en cascade, dans des budgets que tu fixes.
- **Nouvelle mission** se lance depuis l'accueil : Constellation crée alors un dossier dans `~/Documents/Constellation` (avec un suffixe numérique si le nom est pris). Git reste discret : le choix de branche et d'isolation n'apparaît que dans un dépôt Git.
- Des **livrables** : un clic ouvre seulement un fichier ordinaire, non exécutable, d'un type de document ; sinon il est montré dans le Finder.
- **Missions robustes** : un agent qui plante, renvoie une erreur ou dépasse son temps est relancé tout seul (2 essais automatiques, dans sa conversation quand elle est connue) pendant que les autres terminent leur travail. « Reprendre » relance les tâches interrompues par la fermeture de Constellation, et une tâche bloquée repart dès que la tâche dont elle dépend a réussi.
- **Historique** : le bouton **Missions** de l'accueil retrouve toutes les missions, avec une recherche. Tu peux en rouvrir une, la refaire, copier son résultat ou l'enregistrer (les clés sont masquées).
- Détails dans [Les missions en détail](#les-missions-en-détail).

### Carte de mission
- Une vue unique des consoles, des missions, des tâches et des sous-tâches, et de ce qui les relie (confie, délègue, attend, handoff, transfert).
- Recherche et filtres, fiche de chaque tâche, explication de chaque relation.

### Studios
- **Code** : arborescence, éditeur avec coloration, recherche et alerte quand un agent modifie le fichier ouvert.
- **Markdown** : coffre de notes, sauvegarde automatique, graphe des liens et mémoire Claude du projet.
- **Documents** : génération de documents longs, bibliothèque par projet, export PDF (couverture, sommaire, signets).
- **Diagrammes** : génération en formes modifiables sur le tableau, export PNG et Excalidraw.

### Git et navigateur
- Panneau Git : branche, modifications, historique, commit des fichiers choisis, push et pull. Les changements annulés sont d'abord copiés de côté.
- Carte des branches, et connexion à GitHub via `gh`.
- Navigateur intégré (WebKit) : 12 onglets, tailles ordinateur et mobile, ports locaux usuels détectés.

### Consommation
- Tokens par jour, par modèle et par projet, lus dans les journaux locaux de Claude Code et de Codex, en graphique ou en tableau.
- **Quota de l'abonnement Claude** dans la barre du haut : part utilisée de la session de 5 h et de la semaine, avec l'heure de réinitialisation ; au survol ou dans la page Consommation, la part restante. Les chiffres viennent de Claude Code lui-même et s'actualisent quand une console Claude Code du tableau reçoit une réponse.

<p align="center">
  <img src="docs/images/usage.png" width="720" alt="Page Consommation : tokens par jour, par modèle et par projet">
</p>

### Voix
- Commande vocale (barre d'espace maintenue) et dictée dans les consoles (touche Fn).
- La transcription se fait **sur le Mac** : le son n'est envoyé nulle part.

### Personnalisation
- Interface en français ou en anglais, et langue des réponses des agents.
- Thèmes clair et sombre, couleur d'accent, fonds, tailles et animations réduites.

## Configuration requise

| | |
|---|---|
| **Système** | macOS 14 Sonoma ou plus récent |
| **Processeur** | Apple Silicon ou Intel : les versions publiées sont universelles. |
| **Pour les missions** | [Claude Code](https://docs.anthropic.com/claude-code), connecté à un abonnement Claude (Pro ou Max) ou à un compte Anthropic Console |
| **Facultatif** | Git (missions isolées, panneau Git), [`gh`](https://cli.github.com) (GitHub), les autres CLI que tu veux utiliser comme consoles |

Au tout début du lancement, Constellation vérifie que le système est bien macOS 14 ou plus récent. Sinon, elle explique pourquoi et se ferme, sans lire ni modifier aucune donnée.

## Installation

1. Ouvre la page [**Releases**](https://github.com/r97sgkjtdh-ops/constellation/releases/latest) et télécharge `Constellation-<version>.zip`.
2. Ouvre l'archive, puis glisse **Constellation.app** dans le dossier **Applications**.
3. Lance Constellation depuis le dossier Applications ou le Launchpad.

> [!IMPORTANT]
> **Premier lancement.** Constellation n'est pas encore signée avec un certificat de développeur Apple ni notarisée. Au premier lancement, macOS affiche donc « Apple n'a pas pu vérifier… » et refuse de l'ouvrir. Pour l'autoriser, une seule fois :
>
> 1. Ouvre **Réglages Système › Confidentialité et sécurité**.
> 2. En bas, à la ligne qui mentionne Constellation, clique sur **Ouvrir quand même**, puis confirme.
>
> Tu peux aussi, dans le Terminal :
>
> ```bash
> xattr -dr com.apple.quarantine /Applications/Constellation.app
> ```
>
> Ne le fais que pour une archive téléchargée depuis la page Releases officielle de ce dépôt.

Les versions suivantes s'installent depuis l'application elle-même, après vérification de leur signature (voir [Mises à jour](#mises-à-jour)).

### Installer Claude Code

Si Claude Code n'est pas encore sur ton Mac, Constellation te le dit au lancement et affiche la commande d'installation :

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

Si `claude` est installé à un endroit inhabituel, indique son chemin dans **Réglages › Agents**.

## Premier lancement et compte Claude

<p align="center">
  <img src="docs/images/signin.png" alt="Page de connexion de Constellation" width="820">
</p>

Constellation utilise **le compte Claude de la personne qui l'utilise**, jamais celui d'un autre. Au premier lancement, la page de connexion propose trois choix :

| Choix | Pour qui |
|---|---|
| **Se connecter avec Claude** | Un abonnement Claude Pro ou Max |
| **Utiliser un compte Anthropic Console** | Une facturation à l'usage, par clé d'API |
| **Continuer sans compte Claude** | Utiliser seulement les consoles shell et les autres CLI. Les missions demandent Claude Code. |

- La connexion passe par `claude auth login` et se fait **dans ton navigateur**. Si la page affiche un code, colle-le dans Constellation.
- Constellation ne voit ni ton mot de passe ni tes jetons : ils restent gérés par Claude Code.
- Si tu es déjà connecté à Claude Code dans le terminal, Constellation le reconnaît et ouvre directement le tableau.
- **Pour te déconnecter**, clique sur l'icône de compte en haut à droite, à côté des réglages, puis **Se déconnecter de Claude…**. Tu peux aussi passer par **Réglages › Comptes** ou par le menu **Constellation › Se déconnecter de Claude…**. Cela déconnecte aussi Claude Code dans le terminal ; tes tableaux et tes missions sont conservés.
- **Pour changer de compte**, déconnecte-toi, puis reconnecte-toi.

Un assistant te propose ensuite l'apparence, un premier projet et ton agent par défaut.

## Abonnement, quotas et coûts

**Constellation ne vend pas de crédits et ne facture pas les appels aux modèles.** Elle lance les CLI avec la connexion configurée pour chacun d'eux. L'utilisation du modèle dépend donc de ton compte auprès du fournisseur.

| Connexion utilisée par Claude Code | Ce que consomme une mission |
|---|---|
| Abonnement **Claude Pro ou Max** | Les quotas inclus dans ton abonnement. Un montant estimé en dollars dans un journal ne correspond pas automatiquement à une somme débitée en plus. |
| Compte **Anthropic Console / clé API** | Une utilisation facturée sur le compte API associé, selon sa tarification et ses crédits. |
| Usage supplémentaire payant activé | Des frais supplémentaires peuvent s'appliquer selon les réglages et limites de ton compte. |

Le coordinateur, les sous-agents, les revues et les corrections utilisent tous le modèle. Plusieurs agents ne donnent pas plusieurs abonnements : ils peuvent consommer les limites du même compte.

**Lire les montants correctement.** Claude Code peut calculer une estimation monétaire à partir des tokens utilisés. Ce montant est une estimation remontée par le CLI : ce n'est ni un débit bancaire ni un prix garanti par mission. Pour un abonnement, surveille les limites d'usage ; pour l'API, consulte la facturation du fournisseur.

Une clé `ANTHROPIC_API_KEY` configurée peut faire utiliser la facturation API plutôt que l'abonnement. Avoir Pro ne suffit donc pas à identifier la connexion effectivement utilisée. Vérifie le compte dans Claude Code et les options d'usage supplémentaire de ton abonnement. Les limites de tâches, de durée et de parallélisme de Constellation ne sont pas un plafond garanti de facturation.

Références : [Claude Code avec Pro ou Max](https://support.claude.com/en/articles/11145838-use-claude-code-with-your-pro-or-max-plan) · [Comprendre les estimations de coût](https://code.claude.com/docs/en/costs).

## Prise en main

1. **Ouvre un projet** : ⌘O, ou glisse un dossier sur l'accueil. Un projet correspond à un dossier de ton disque.
2. **Ajoute une console** : clic droit sur le tableau, ou ⌘K puis « crée 2 agents Claude ». Chaque console est un vrai terminal dans le dossier du projet.
3. **Parle à tes agents** : ⌘K ouvre la barre de commande. `@nom consigne` envoie un message à une console, `@groupe consigne` à toute une équipe.
4. **Confie une mission** : bouton **Nouvelle mission** de l'accueil (sans projet, dans un nouveau dossier), bouton **Mission** (la cible) dans la barre de gauche, ou « Confier une mission » sur un tableau vide. Décris le résultat attendu et les commandes de contrôle (par exemple `swift test` ou `npm test`), choisis le mode, puis lance.
5. **Suis l'avancement** : la carte du coordinateur et ses tâches s'affichent sur le tableau. La **carte de mission** (touche X) montre l'ensemble.

Le tutoriel intégré (⌘?) explique chaque bouton.

### Exemple de demande pour une première mission

Commence avec un petit projet jetable et le mode **assisté**, pour relire le plan avant l'exécution. Voici un exemple à adapter aux fichiers et aux commandes réellement présents dans ton projet :

```text
Objectif : corriger les fonctions addition et multiplication de ce projet Python.

Périmètre : addition.py et multiplication.py.
Résultat attendu : les opérations fonctionnent aussi avec zéro et les nombres négatifs.
Contraintes : ne supprime aucun test existant et ne change pas les résultats attendus
pour masquer un défaut. N'ajoute aucune dépendance.

Répartis les corrections en tâches distinctes. Chaque tâche doit avoir son contrôle.
Après intégration, exécute python3 -m unittest -v sur l'ensemble du projet.
Dans la synthèse, liste les fichiers modifiés, les contrôles exécutés et leurs résultats.
Si une information manque, pose une question au lieu de l'inventer.
```

Lis le plan proposé : les tâches, leur périmètre, leurs dépendances et leurs commandes de contrôle doivent correspondre à ta demande. La revue indépendante est active par défaut : décoche-la seulement pour une petite mission bien couverte par ses tests. Une fois la mission terminée, examine le diff Git et les sorties des contrôles avant de conserver le résultat.

Une mission « Réussie et vérifiée » signifie que ses contrôles ont réussi sur l'état testé. Cela ne garantit pas l'absence de bugs non couverts par ces contrôles.

## Les missions en détail

<p align="center">
  <img src="docs/images/new-mission.png" width="560" alt="Fenêtre Nouvelle mission">
</p>

```mermaid
flowchart LR
    D[Ta demande] --> C[Coordinateur<br>lecture seule]
    C -->|plan validé| T1[Sous-agent A]
    C -->|plan validé| T2[Sous-agent B]
    T1 --> V1{Contrôles<br>exécutés par Constellation}
    T2 --> V2{Contrôles<br>exécutés par Constellation}
    V1 -->|échec| F1[Correction rédigée<br>par le coordinateur] --> T1
    V2 -->|échec| F2[Correction] --> T2
    V1 -->|réussite| R1[Revue indépendante]
    V2 -->|réussite| R2[Revue indépendante]
    R1 -->|problème relevé| F1
    R2 -->|problème relevé| F2
    R1 --> I[Intégration]
    R2 --> I
    I --> FC{"Contrôles de l'ensemble"}
    FC -->|échec| FX[Tâche de correction] --> I
    FC -->|réussite| S[Synthèse et<br>résultat vérifié]
```

### Déroulement
1. **Plan.** Un coordinateur Claude Code, en lecture seule, étudie le projet et propose des tâches, avec leurs dépendances, leurs fichiers et leurs contrôles. Constellation valide ce plan (clés, dépendances, absence de cycles, nombre de tâches) avant toute exécution.
2. **Exécution.** Chaque tâche est confiée à une session Claude Code séparée, qui reçoit la demande d'origine, ses instructions, ses fichiers, les résultats de ses prérequis et les contrôles qui la jugeront.
3. **Contrôles.** Constellation exécute elle-même les commandes de contrôle. En cas d'échec, le coordinateur rédige une correction à partir de la sortie réelle, et la tâche la reçoit dans la même conversation.
4. **Revue (activée par défaut).** Une session indépendante, sans mémoire du travail, relit chaque changement dont les contrôles ont réussi.
5. **Intégration et contrôle final.** Les contributions vérifiées sont intégrées, puis les contrôles de l'ensemble sont lancés. S'ils échouent, une tâche de correction est créée.
6. **Synthèse.** Elle dit exactement ce qui a été prouvé, et ce qui ne l'a pas été.

### Modes
- **Assisté** : tu relis et modifies le plan, puis tu le valides. Les sous-agents et les corrections partent ensuite seuls, dans les limites fixées. Seuls t'attendent les questions des agents, les conflits, ce qui ne peut pas être prouvé et les commandes inconnues ; avec le web, toute commande hors de ton plan.
- **Délégué** : tout part automatiquement, dans les limites que tu fixes.

Par défaut, une mission est limitée à 3 sessions simultanées, 12 tâches, 3 corrections par tâche, 20 minutes par session et 80 appels à Claude (sessions, relectures, corrections rédigées, plan et synthèse). Dans les réglages avancés, tu peux aussi fixer une dépense maximale : à ce montant, plus aucune session ne démarre, et celles en cours finissent, donc le montant peut être dépassé. À la limite d'appels, elle se suspend : ce qui tourne finit, puis rien ne repart tant que tu n'as pas décoché « Suspendre », ce qui lui accorde 40 appels de plus. Ces limites se règlent dans Nouvelle mission › Réglages avancés, où l'on choisit aussi les modèles du coordinateur et des tâches. Par défaut (« Selon la tâche »), le coordinateur choisit pour chaque tâche Haiku, Sonnet ou Opus, le moins cher qui suffit ; ce choix reste indicatif et tu peux imposer un modèle. Fable n'est utilisé que si tu le choisis et que ton accès est vérifié ; sinon Opus le remplace. Tu peux y choisir un modèle pour le coordinateur (Sonnet par défaut), pour les tâches et pour la relecture, qui suit par défaut celui du coordinateur.

Le coût affiché est un minimum (« au moins 1,20 $ ») : une session interrompue ne rapporte pas le sien.

Avec le web, une page piégée peut tromper un agent : il pourrait modifier des fichiers, envoyer leur contenu vers un site, ou glisser du code dans une commande que tu as approuvée. Seules les commandes de ton plan s'exécutent alors sans te demander.

### Isolation
- **Dossier partagé** : les tâches travaillent dans ton dossier. Celles qui déclarent les mêmes fichiers passent l'une après l'autre.
- **Un worktree par tâche** (si le projet est un dépôt Git) : chaque tâche travaille dans un worktree séparé, créé depuis l'état actuel de ton dossier. Ton dossier n'est pas modifié pendant la mission. Chaque contribution vérifiée devient un patch appliqué **en entier ou pas du tout**. En cas de conflit, ton dossier reste intact, et le patch et le worktree sont gardés pour que tu décides.
- Constellation **ne fait jamais de commit sur ta branche et ne pousse jamais**.

### Garanties
- **Des preuves liées à l'état testé.** Chaque preuve est liée au contenu exact des fichiers contrôlés : révision, modifications et fichiers non suivis. Si ce contenu change avant l'intégration, les contrôles sont rejoués.
- **Des autorisations exactes.** Les commandes de test et de build connues s'exécutent seules, sauf avec le web ou un connecteur : seules les commandes de ton plan validé et les simples lectures du dossier passent alors sans te demander (en mode délégué, seules ces lectures, à moins d'avoir coché l'autorisation). Sans web ni connecteur, et avec le bac à sable, cette case est cochée par défaut : le code du projet, même cloné, peut alors tourner sans te demander, dans le bac à sable, réseau ouvert. Les autres attendent ton accord, et une commande modifiée n'est plus approuvée.
- **Des états honnêtes.** « Réussie et vérifiée » exige que chaque tâche ait passé ses contrôles et que l'ensemble ait passé les siens. Une mission jugée par une relecture est affichée « Réussie, validée par relecture », jamais « vérifiée » ; commandes et relecture ensemble donnent « Réussie, vérifiée et relue ». Une tâche que tu acceptes toi-même est affichée « Acceptée par toi », jamais « vérifiée ».
- **Une annulation fiable.** Annuler arrête les sessions, les contrôles, les revues et l'intégration, avec toute l'arborescence de leurs processus.
- **Aucun relancement caché.** Après une fermeture de l'app, les tâches en cours passent « à récupérer » et attendent une relance explicite.
- **Des sessions allégées.** Les sessions d'une mission démarrent sans charger tes serveurs MCP ni tes skills, afin de limiter le contexte envoyé au modèle. Seuls les connecteurs que tu coches font exception (voir [Connecteurs](#connecteurs)) ; sans connecteur coché, rien ne change. Cela peut réduire la consommation de tokens ; le gain dépend de la tâche, du modèle et des corrections nécessaires. Les montants estimés par le CLI ne constituent pas une preuve de facturation : voir [Abonnement, quotas et coûts](#abonnement-quotas-et-coûts).

### Connecteurs
Dans Nouvelle mission, la section **Connecteurs** liste ceux que Claude Code connaît pour ce dossier. Tu peux en confier à tes agents, à ton choix.

- **Rien n'est coché par défaut**, et ton choix n'est pas repris d'une mission à l'autre. La case **Skills** est à part, décochée aussi.
- **Seuls les agents et leurs sous-agents** reçoivent les connecteurs cochés. Le coordinateur et le relecteur n'en ont aucun.
- **Tout connecteur compte comme pouvant écrire.** Constellation ne peut pas savoir quels outils d'un connecteur modifient des données : une phrase le rappelle dès qu'un connecteur est coché, et chaque session d'agent consomme un peu plus.
- **Un connecteur non connecté est grisé**, avec son état. Constellation ne l'authentifie pas : fais-le dans Claude Code.
- **Un accord explicite** est demandé au lancement quand un connecteur est combiné au web, ou quand la mission est en mode délégué. Il n'est pas mémorisé. En mode assisté sans web, valider le plan vaut accord.
- **Un connecteur est une source non fiable**, comme le web : un e-mail ou une page peut contenir des instructions piégées. En mode assisté, avec un connecteur, seules les commandes de ton plan validé passent sans te demander.
- **Les actions faites par un connecteur sont marquées « non vérifiées »** et listées dans la mission : Constellation ne peut pas les contrôler.

### Délégation en cascade
Un agent qui a besoin d'aide crée un sous-agent, qui peut créer le sien : chacun apparaît sur le tableau. Constellation les valide dans un budget de niveaux (4 par défaut dans Nouvelle mission, 6 au plus) et de nombre de tâches, les fait réaliser et contrôler, puis rend la main au parent avec leurs résultats pour qu'il consolide. En mode assisté, tu valides le plan de départ ; les sous-agents et les corrections suivent sans nouvelle question, et l'outil de sous-agents natif de Claude Code est désactivé dans les missions pour que rien ne se passe hors du tableau.

### Carte de mission

<p align="center">
  <img src="docs/images/mission-map.png" alt="Carte de mission : consoles, missions, tâches et relations">
</p>

Clique sur une carte pour l'inspecter, ou sur le point au milieu d'une relation pour savoir à quoi elle sert et où elle en est. Les traits pleins signalent qu'une tâche est confiée ou déléguée, les pointillés qu'elle attend un prérequis, et les tirets orange un transfert entre consoles.

## Raccourcis clavier

| Raccourci | Action |
|---|---|
| ⌘K | Barre de commande |
| ⌘P | Aller à une carte |
| ⌘O | Ouvrir un dossier comme projet |
| ⇧⌘T | Nouvel espace |
| ⌘1 … ⌘9 | Aller à l'espace 1 à 9 |
| ⇧⌘H | Retour à l'accueil |
| ⌘+ / ⌘− / ⌘0 | Zoomer, dézoomer, taille réelle |
| ⌘G / ⇧⌘G | Grouper, dégrouper |
| ⌘D | Dupliquer la sélection |
| V | Outil de sélection |
| T | Nouvelle console à l'endroit du pointeur |
| N | Aller à l'agent qui demande une intervention |
| P · E | Stylo · gomme |
| X | Carte de mission |
| G | Panneau Git |
| M · S · L | Mémoire · skills · boucles |
| D | Studio Markdown |
| ⇧1 | Tout cadrer |
| Flèches (⇧ : 10 pt) | Déplacer la sélection |
| Tab · ⇧Tab · ⌥ Flèches · Retour | Passer d'une carte à l'autre · ouvrir la carte |
| Dans un kanban : ↑ puis flèches · Retour · Échap · ⌥ ← → | Parcourir les tickets · modifier · fermer l'éditeur · changer de colonne |
| Dans un calendrier : flèches · Retour · Échap · ⇧ Retour | Parcourir les jours · ouvrir (de nouveau : l'événement suivant) · fermer l'éditeur · ajouter un événement |
| ⌫ · Échap | Supprimer la sélection · revenir à la sélection, puis tout désélectionner |
| Espace maintenu | Commande vocale (quand le tableau a le clavier) |
| Fn maintenue | Dictée dans la console ou le champ actif |
| ⌘? | Tutoriel |
| ⌘, | Réglages |

Les raccourcis d'une seule touche agissent quand le tableau a le clavier, et se changent dans **Réglages › Raccourcis**.

## Mises à jour

Constellation cherche une mise à jour au lancement, puis toutes les 6 heures (réglable). Une version trouvée est signalée par une pastille rouge sur le bouton Réglages ; l'installation reste ton choix. Tu peux aussi passer par **Réglages › Mises à jour** ou par le menu **Constellation › Rechercher les mises à jour…**. Quand une version est disponible, une pastille apparaît dans la barre du haut.

L'archive n'est installée que si sa **signature Ed25519** correspond à la clé intégrée à l'application. Le téléchargement est limité aux serveurs de GitHub, et l'identifiant, la version et la signature de code de l'app sont vérifiés.

L'ancienne version est gardée dans `~/Library/Application Support/Constellation-sauvegardes/`. Une mise à jour est refusée tant que des sessions de mission tournent.

## Données et confidentialité

- **Aucun serveur Constellation.** L'application n'envoie ni statistiques ni télémétrie. Ses seules connexions sont la recherche de mises à jour sur GitHub (l'API et la liste signée des versions retirées, désactivable), les pages que tu ouvres dans le navigateur intégré, et ce que font les CLI que tu lances, qui suivent leurs propres conditions.
- **Aucun identifiant conservé.** Les comptes restent gérés par Claude Code, Codex, `gh`, etc.
- **Où sont tes données :**

| Emplacement | Contenu |
|---|---|
| `~/Library/Application Support/Constellation/` | Tableaux, missions, ordres, patchs, transferts, journaux de mise à jour |
| `~/Library/Preferences/com.vel.constellation.plist` | Réglages |
| `<ton projet>/.constellation/` | Résumés de handoff, comptes rendus transmis entre consoles (effacés après 7 jours), copies des changements annulés |
| `~/Library/Application Support/Constellation-sauvegardes/` | Anciennes versions de l'app et copies de tes données, faites à chaque installation |

## Désinstallation

1. Quitte Constellation (⌘Q). Si tu le souhaites, déconnecte-toi de Claude avant (Réglages › Comptes).
2. Mets `/Applications/Constellation.app` à la corbeille.
3. Pour effacer aussi tes données et tes réglages (c'est **définitif**) :

```bash
rm -rf ~/Library/Application\ Support/Constellation
rm -rf ~/Library/Application\ Support/Constellation-sauvegardes
defaults delete com.vel.constellation
```

Claude Code et les autres CLI ne sont pas touchés : ils se désinstallent séparément.

## Dépannage

<details>
<summary><strong>« Apple n'a pas pu vérifier que Constellation ne contient pas de logiciel malveillant »</strong></summary>

L'app n'est pas encore notarisée. Va dans **Réglages Système › Confidentialité et sécurité** et clique sur **Ouvrir quand même**, ou lance `xattr -dr com.apple.quarantine /Applications/Constellation.app` (voir [Installation](#installation)).
</details>

<details>
<summary><strong>« Claude Code n'est pas installé » alors qu'il l'est</strong></summary>

Constellation cherche `claude` avec le `PATH` de ton shell de connexion. Si ton installation est ailleurs, indique le chemin complet dans **Réglages › Agents**, puis clique sur **Vérifier à nouveau**. Tu peux contrôler ton installation avec `claude --version` et `claude auth status --text`.
</details>

<details>
<summary><strong>La connexion n'aboutit pas</strong></summary>

- Si le navigateur ne s'est pas ouvert, clique sur **Rouvrir la page** ou **Copier le lien**.
- Si la page affiche un code, colle-le dans le champ prévu, puis clique sur **Valider**.
- Si rien ne fonctionne, connecte-toi dans le Terminal avec `claude auth login`, puis reviens dans Constellation : la connexion est reconnue automatiquement.
</details>

<details>
<summary><strong>Une mission échoue avec une limite d'usage (erreur 429)</strong></summary>

La limite de ton abonnement Claude est atteinte. Le motif exact est affiché dans la tâche. Une tâche d'agent s'arrête alors sans échouer et reprend la même conversation toute seule à l'heure annoncée. Si le plan ou une relecture est touché, attends la réinitialisation puis relance-le.
</details>

<details>
<summary><strong>La commande vocale ou la dictée ne marche pas</strong></summary>

Autorise le micro et la reconnaissance vocale dans **Réglages Système › Confidentialité et sécurité**. Si la touche Fn ouvre le sélecteur d'emoji, change son rôle dans Réglages Système › Clavier, ou choisis une autre touche dans **Réglages › Voix**.
</details>

<details>
<summary><strong>Joindre un diagnostic à un signalement</strong></summary>

Menu **Aide › Exporter un diagnostic…** : Constellation crée une archive `.zip` à l'endroit que tu choisis. Elle contient la version de l'app et de macOS, le modèle du Mac, les réglages de l'app (les clés et jetons sont masqués), le journal de la session en cours, la liste des fichiers de données (sans leur contenu) et les journaux de mise à jour. Le chemin de ton dossier personnel et ton nom d'utilisateur sont remplacés. **Rien n'est envoyé** : relis l'archive, puis joins-la à ton issue si tu le souhaites.
</details>

<details>
<summary><strong>Revenir à la version précédente</strong></summary>

Ouvre le dossier daté le plus récent dans `~/Library/Application Support/Constellation-sauvegardes/` et suis son fichier `RESTAURER.txt`.
</details>

## Guides

| Guide | Pour quoi |
|---|---|
| [Donner des ordres](docs/ordres.md) | La barre de commande : écrire un ordre, modifier le plan, étapes qui s'attendent, compte rendu final. |
| [Rôles et équipes](docs/roles-et-equipes.md) | Groupes, rôles et les 18 dispositions prêtes à l'emploi. |
| [Exemples](docs/exemples.md) | Dix ordres prêts à copier. |
| [Journal des versions](CHANGELOG.md) | Ce que chaque version a apporté. |

## Questions fréquentes

**Ordre, mission ou boucle : lequel choisir ?**
Un **ordre** (⌘K) envoie des consignes à des consoles déjà ouvertes, et tu suis leur travail toi-même. Une **mission** confie une demande entière à un coordinateur : il la découpe en tâches, les fait faire en parallèle et contrôle le résultat avant de dire « réussi ». Une **boucle** relance la même consigne à intervalle régulier ou à chaque fin de tour, jusqu'à un objectif vérifié.

**Est-ce que Constellation coûte quelque chose ?**
L'app est gratuite. Les agents utilisent ton propre compte (abonnement Claude ou clé API) : voir [Abonnement, quotas et coûts](#abonnement-quotas-et-coûts).

**Mes fichiers partent-ils quelque part ?**
Constellation n'a pas de serveur et n'envoie aucune statistique. Ce que lisent les agents part chez leur fournisseur, comme quand tu les utilises dans un terminal. Détails dans [Données et confidentialité](#données-et-confidentialité).

**Faut-il Claude Code ?**
Pour les missions et le planificateur des ordres, oui. Les consoles acceptent aussi Codex, Gemini CLI, OpenCode et d'autres CLI.

**Comment revenir en arrière après une mise à jour ?**
Chaque installation garde la version précédente : Réglages › Mises à jour › « Revenir à une version précédente ».

## État du projet et limites connues

Constellation est en développement actif. Les principales limites :

- **Pas encore de génération d'images ni de vidéos.** Aucune date n'est promise.
- **Les missions ne fonctionnent qu'avec Claude Code.** Les autres CLI s'utilisent comme consoles, mais n'ont pas encore d'adaptateur pour les missions.
- **L'app n'est ni signée par un développeur Apple ni notarisée.** Il faut l'autoriser au premier lancement.
- **Certaines fonctions sont encore peu éprouvées en conditions réelles** : la délégation en cascade, les corrections et l'annulation. Les tests automatisés ne couvrent ni le parcours complet de l'interface ni les vrais gestes sur le tableau (trackpad, molette, pincement).
- **Le résultat des agents reste à vérifier par toi.** Une mission « vérifiée » l'est sur l'état testé, pas au-delà.
- **L'isolation des worktrees ne couvre pas tout.** Les dépendances ignorées par Git (`node_modules`, `.venv`) sont partagées par lien symbolique, et les bases de données, ports et services ne sont pas isolés.
- **Les contrôles tournent dans un bac à sable macOS.** Ils écrivent dans le dossier de travail, les dossiers temporaires et les caches de paquets, ne lisent pas les clés et secrets les plus courants (`~/.ssh`, `~/.aws`, le trousseau…) et n'ont pas de réseau si la mission utilise le web ou un connecteur. Une case dans les réglages avancés le désactive. Les données Git, la configuration de Claude et les préférences sont protégées, et un contrôle ne peut pas lancer d'apps. Les variables de type clé ou mot de passe exportées par ton profil de shell sont retirées, et ce qu'un contrôle laisse tourner en arrière-plan est arrêté à sa fin (depuis la 0.3.17, un processus dans sa propre session aussi, dans le worktree d'une tâche et s'il reste dans ce dossier). Il ne couvre pas les sessions des agents, qui ont leurs propres règles. Depuis la 0.3.29, tes dossiers personnels (Documents, Bureau, Téléchargements, Photos, Mail, Messages, iCloud) sont fermés, sauf le projet lui-même ; d'autres fichiers du Mac restent lisibles, et ce qu'un contrôle écrit dans le dossier ou un cache peut s'exécuter plus tard. Depuis la 0.3.17, un sous-dossier qui contient un `.git` ou un `CLAUDE.md` ne peut plus être déplacé pendant un contrôle ; un dossier créé ailleurs peut encore y arriver avec son propre `.git`. C'est une barrière de plus, pas une garantie.
- **Les noms d'exécutables de certains CLI du catalogue n'ont pas été vérifiés.** Pour ceux qui manquent, crée un agent personnalisé.

**Ce qui marche et comment c'est vérifié** : les missions sont couvertes par 870 tests automatiques et de vraies missions réussies ; le bac à sable par des tests avec le vrai `sandbox-exec` ; le clavier dans les cartes (depuis la 0.3.17) avec de vraies touches et de vrais clics envoyés par macOS ; la mise à jour par un vrai passage de la 0.3.15 à la 0.3.17 depuis l'app.

**Encore à vérifier en conditions réelles** : VoiceOver, les fenêtres de confirmation ajoutées en 0.3.19, l'arrêt forcé pendant l'intégration, l'alerte de deuxième instance, le shell fish.

**À venir, sans date** : la signature et la notarisation Apple, la génération d'images et de vidéos, les autres CLI dans les missions.

## Signaler un problème

- **Un bug ou une idée** : ouvre une [issue](https://github.com/r97sgkjtdh-ops/constellation/issues) avec ta version de macOS, la version de Constellation (Réglages › À propos), les étapes pour reproduire, et ce que tu attendais. Pour un bug, joins si possible un diagnostic (menu **Aide › Exporter un diagnostic…**).
- **Une faille de sécurité** : ne la publie pas dans une issue publique. Utilise le signalement privé de GitHub (onglet **Security › Report a vulnerability**), comme l’explique la [politique de sécurité](SECURITY.md).

Ce dépôt ne contient que la documentation et les versions publiées : le code source n'y est pas.

## Licence

Constellation est créée par **Vel**. C'est un logiciel propriétaire, gratuit à l'usage. Son code source n'est pas publié. Les conditions complètes sont dans [LICENSE](LICENSE) : tu peux l'installer et l'utiliser librement, à titre personnel ou professionnel, mais pas la redistribuer, la modifier ni la décompiler.

Constellation est un projet indépendant, sans lien avec Anthropic, OpenAI ou Google. Claude et Claude Code sont des marques d'Anthropic ; les autres noms cités appartiennent à leurs propriétaires.

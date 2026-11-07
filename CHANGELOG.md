# Journal des versions

*[English version](CHANGELOG.en.md)*

Les nouveautés et corrections de chaque version publiée, de la plus récente à la plus ancienne. Avant la 0.3.0, les versions n'étaient pas publiées.

## 0.3.31 (2026-11-07)

### Nouveautés
- **Des rôles qui changent vraiment le comportement** (Claude Code) : chaque rôle donne une consigne de départ, et **Revue** et **Sécurité** travaillent en lecture seule, sans outil qui modifie un fichier. Le planificateur des ordres lit la description du rôle.
- **Modèles de mission** : six modèles prêts à compléter (corriger un bug, nouvelle fonctionnalité, audit, documentation, recherche sur le web, restructuration), et tes propres modèles. Un modèle n'emporte jamais les connecteurs, ni ton accord pour les sources externes, ni l'autorisation des contrôles.
- **« Refaire » une mission** reprend aussi son mode, ses limites, son isolement et le web.
- **Historique des ordres** : tous les ordres, même effacés du fil, avec recherche, détail et export en Markdown sans secrets.
- **Même fichier modifié** : deux consoles Claude qui modifient le même fichier dans la même demi-heure sont signalées.
- **Journal gardé sur le disque** (7 jours, sans secrets), et un arrêt brusque est signalé au lancement suivant, avec un diagnostic qui joint le rapport de plantage de macOS.
- **Des notifications signées Constellation** : un tour terminé est signalé par Constellation. Dans les consoles et les missions qu'elle lance, la notification « Claude Code » du module ECC est coupée ; elle reste active dans ton Terminal.
- **Barre du haut allégée** : le quota et la consommation ne font plus qu'un bouton.
- **Réglages refaits** : une barre latérale avec recherche, comme les Réglages de macOS, et de nouvelles rubriques. **Tableau** : taille des nouvelles consoles, fond animé, fixe ou sans réseau. **Notifications** : chaque type d'événement se règle à part, avec ou sans son, et le badge du Dock. **Confirmations** : on peut ne plus être interrogé avant d'arrêter une console ou de quitter. **Données** : exporter, importer ou réinitialiser les réglages, créer un diagnostic, ouvrir le journal. **À propos** : les crédits (Vel, avec le lien GitHub) et les logiciels libres utilisés.

### Corrections
- **Compteur de consoles** : il pouvait compter des consoles de projets de test, laissés dans les données par les captures automatiques. Les captures gardent maintenant tout dans leur dossier jetable.
- **Réglages › Mises à jour** : « Depuis le code de ce Mac » n'apparaît plus dans une app publiée, qui ne pouvait pas s'en servir.

### À savoir
- **Vérifié** : la suite de tests sur ce Mac (870 tests, 16 ignorés, aucun échec) ; les options des rôles avec le vrai Claude Code ; l'alerte « même fichier » avec le vrai script, qui ne garde que le chemin du fichier. GitHub n'a pas lancé ses vérifications (minutes du mois épuisées).
- **Vérifié par captures** : chaque rubrique des nouveaux Réglages, en français et en anglais.
- **Non vérifié à l'écran** : les modèles de mission, l'historique des ordres, l'alerte « même fichier » et les nouvelles notifications. Si quelque chose coince, ouvre une issue.
- **Changer le rôle d'une console** s'applique à son prochain démarrage. Pour Codex et Gemini, le rôle reste une étiquette.

## 0.3.30 (2026-11-06)

### Corrections
- **Plan d'un ordre** : la case « Compte rendu final » et le menu « Après … » sont à la même taille que le reste de l'éditeur. Ils étaient plus gros.
- **Liste des consoles** : le temps s'affiche « il y a 3 min », au lieu de « depuis il y a 3 min ».

### À savoir
- **Présentation** : captures du plan d'un ordre et de la liste des consoles, guides, questions fréquentes et journal des versions sur la page du projet.
- **Vérifié** : la suite de tests (851 tests, 16 ignorés, aucun échec), sur ce Mac et sur GitHub.

## 0.3.29 (2026-11-06)

### Ordres à plusieurs consoles
- **Le plan se modifie avant l'envoi** : console, consigne, ajout ou retrait d'une étape, étape finale.
- **Une étape peut en attendre d'autres** (« Après … ») et reçoit leurs comptes rendus : par exemple, écrire puis faire relire.
- **Une étape finie ou en échec se relance**, sur la même console ou une autre.
- **Les comptes rendus disent comment l'étape a fini** : délai dépassé, console arrêtée, interrompue ou erreur de l'API, en orange, au lieu de « terminé ». L'étape finale attend ton accord si une étape n'a pas abouti.
- **Annuler arrête les agents** qui travaillent sur l'ordre. Deux ordres sur la même console passent l'un après l'autre.
- **Les ordres restent après un redémarrage** ; « Effacer » les masque sans les supprimer.

### Consoles et tableau
- **TOUR ÉCHOUÉ** au lieu de PRÊT après une erreur de l'API ; une console arrêtée sur un code d'erreur est en rouge.
- **« Bloquée ? »** sur une console au travail sans aucun signe depuis 10 minutes, avec Interrompre et Redémarrer.
- **Redémarrer en reprenant la conversation**, au lieu de toujours repartir de zéro.
- **Notifications macOS** en arrière-plan et nombre de consoles qui t'attendent sur l'icône du Dock (Réglages › Apparence).
- **⌘P « Aller à une carte »**, **liste de toutes les consoles** au clic sur leur compteur, et **« Annuler »** après une suppression.

### Sécurité
- Les agents de mission ne reçoivent plus tes jetons (GitHub, cloud). Les contrôles ne lisent plus tes dossiers personnels. Le mode sans permissions s'arrête avec l'app. Une carte Web n'ouvre que des pages web.
- Le plan d'un ordre signale une console sans permissions, et les comptes rendus transmis sont présentés comme des données, secrets masqués.
- L'en-tête d'une mission signale les autorisations de tes réglages Claude Code, qui s'ajoutent à celles de la mission.

### Mises à jour
- La mise à jour montre les notes de **toutes les versions sautées**.
- **Revenir à une version précédente** depuis Réglages › Mises à jour.
- Une version retirée n'est plus proposée.

### À savoir
- **Vérifié** : la suite de tests (851 tests, 16 ignorés, aucun échec), sur ce Mac et sur GitHub, de nouveau verte ; les vrais essais avec Claude Code sur `.git`, `.Claude` et la lecture hors du projet.
- **Non vérifié à l'écran** : l'éditeur du plan, les notifications, ⌘P, la liste des consoles et le retour à une version précédente. Si quelque chose coince, ouvre une issue.
- **Un projet rangé dans Documents** dont les tests lisent un dossier voisin : ces tests échouent maintenant dans le bac à sable.
- Nouveaux guides : donner des ordres, rôles et équipes, et dix exemples.

## 0.3.28 (2026-11-06)

### Correction
- **Mises à jour qui n'arrivaient plus** : en 0.3.23, on pouvait encore écrire dans la case « Dépôt GitHub » de la page de mise à jour. Un nom tapé là restait enregistré et passait avant le dépôt officiel. L'app cherchait alors ses mises à jour dans un dépôt qui n'existe pas, sans moyen de corriger, puisque la case est en lecture seule depuis la 0.3.24. Une app publiée cherche maintenant toujours dans son propre dépôt.

### À savoir
- **Si ton app ne te propose plus de mise à jour depuis la 0.3.24**, cette version ne peut pas t'arriver seule, car c'est l'ancienne version qui cherche. Installe-la une fois à la main depuis cette page : les suivantes arriveront d'elles-mêmes.
- **Vérifié** : la suite de tests (816 tests, 16 ignorés, aucun échec).
- **Rappel de la 0.3.27** : un ordre à plusieurs consoles peut finir par un compte rendu commun, qui attend les autres et reçoit leurs comptes rendus complets. Essayé aussi avec le vrai planificateur sur quatre escouades de quatre consoles.

## 0.3.27 (2026-11-06)

### Correction
- **Compte rendu commun de plusieurs équipes** : quand tu donnais un ordre à plusieurs consoles, toutes les étapes partaient en même temps et les consoles ne se voyaient pas. Le compte rendu final partait donc sans le travail des autres équipes. Maintenant, l'orchestrateur ajoute une étape finale quand ta demande prévoit un compte rendu, une synthèse ou un bilan commun. Elle est marquée « après les autres » dans le plan et part seulement quand toutes les autres consoles ont fini.
- **Comptes rendus complets** : la console finale reçoit le compte rendu entier de chaque console, dans un fichier `.constellation/comptes-rendus-….md` du projet, gardé hors de Git. Pour une console Claude Code, c'est sa dernière réponse complète. Pour les autres outils, c'est la fin de l'écran. Chaque équipe sait à qui son compte rendu est transmis.

### À savoir
- **Vérifié** : la suite de tests (815 tests, 16 ignorés, aucun échec), dont un compte rendu de 500 lignes retrouvé entier, et un essai avec le vrai planificateur : deux équipes de trois consoles, puis un compte rendu commun.
- **Non vérifié** : le parcours complet avec de vraies consoles sur le tableau. Si quelque chose coince, ouvre une issue.

## 0.3.26 (2026-11-06)

### Corrections
Une analyse complète de l'app, menée par une mission Constellation de 13 agents, a trouvé 10 défauts sérieux. Ils sont tous corrigés.

**Sécurité**
- **Réglages d'un projet téléchargé** : les missions n'appliquent plus les réglages Claude Code rangés dans le projet (`.claude/settings.json`). Un projet piégé pouvait lancer des commandes sur ton Mac dès le début d'une mission. Le fichier `CLAUDE.md` du projet reste transmis aux agents.
- **Tests du projet** : quand le bac à sable est actif, les agents ne lancent plus eux-mêmes les tests du projet. Seule Constellation les lance, dans le bac à sable. Avant, un agent pouvait écrire un test puis le lancer hors du bac à sable, avec accès à tes clés.

**Ne rien perdre**
- **Mise à jour qui plante** : si la nouvelle version ne reste pas ouverte, la version précédente est remise en place et rouverte d'elle-même. La nouvelle est gardée dans la sauvegarde.
- **Historique des missions abîmé** : sa copie de secours est remise en place, avec un message. Le projet n'est plus bloqué.
- **Dépôt Git rangé dans le projet** : le travail fait dedans est maintenant livré. Avant, la tâche était annoncée réussie sans rien livrer.

**Confort et accessibilité**
- **Contrôles du plan** : ce que tu tapes reste tel quel. Les espaces et les retours à la ligne disparaissaient pendant la frappe.
- **Moins de travail au repos** : les consoles ne font plus redessiner toutes les cartes deux fois par seconde, et une carte Dossier lit 2 000 éléments au plus, sans rien relire quand l'app est en arrière-plan.
- **VoiceOver** annonce une console qui a besoin de toi ou en erreur, une mission qui attend une décision et une mission terminée.
- **Langue des agents** : tant que tu n'en as pas choisi une, c'est celle de l'interface. Sur un Mac en anglais, les agents répondaient en français.

### À savoir
- **Vérifié** : la suite de tests (809 tests, 16 ignorés, aucun échec), deux vraies missions courtes réussies, et le blocage des réglages du projet essayé avec le vrai Claude Code.
- **Non vérifié** : à l'écran, l'éditeur des contrôles, les annonces VoiceOver et la carte Dossier. Le retour à la version précédente n'a été essayé qu'avec une fausse app. Si quelque chose coince, ouvre une issue.
- **Les agents ne lancent plus les tests eux-mêmes** quand le bac à sable est actif : si un test échoue, Constellation leur renvoie une correction à faire.
- Il reste 148 défauts moyens ou petits, à traiter dans les prochaines versions.

## 0.3.25 (2026-11-05)

### Correction
- **Missions plus légères** : pour partir de ton état actuel, chaque tâche d'une mission reçoit une copie des fichiers que Git ne suit pas. Cette copie prenait aussi les copies de travail du même projet rangées à l'intérieur, comme celles que Claude Code range dans `.claude/worktrees`, en entier, compilations comprises. Elle prenait même leur fichier `.git`, qui renvoie à ton vrai dépôt. Sur un projet, chaque tâche pesait ainsi 2,6 Go. Ces copies du projet sont maintenant laissées de côté. Les autres fichiers non suivis, et un autre dépôt rangé dans le projet, sont toujours copiés.

### À savoir
- **Vérifié** : la suite de tests (796 tests, 14 ignorés, aucun échec), dont un essai avec un vrai worktree du même dépôt et un autre dépôt imbriqué.
- **Non vérifié** : une vraie mission avec cette correction. Si quelque chose coince, ouvre une issue.
- **Les worktrees déjà créés** ne changent pas : « Nettoyer les worktrees », dans une mission finie, les retire.

## 0.3.24 (2026-11-05)

### Correction
- **Mise à jour qui semblait ne pas rouvrir l'app** : avant d'installer, l'app recopiait tout son dossier de données, y compris les copies de travail des missions (worktrees), qui peuvent peser des gigaoctets. L'app restait fermée de longues minutes sans rien afficher. La sauvegarde laisse maintenant les worktrees en place, car l'installation n'y touche pas, et clone le reste : elle prend moins d'une seconde et presque aucune place sur le disque.
- **Page de mise à jour** : le dépôt GitHub s'affiche en simple texte au lieu d'un champ où l'on pouvait écrire.

### À savoir
- **La sauvegarde est faite par la version déjà installée** : passer de la 0.3.23 à la 0.3.24 peut donc encore être lent, une dernière fois. Attends que l'app revienne. Les mises à jour suivantes seront rapides.
- **Vérifié** : la suite de tests (795 tests, 14 ignorés, aucun échec). Sur un vrai dossier de 16 Go, la sauvegarde est passée d'environ 1 min 30 à 0,2 s, et de 16 Go à 10 Mo.
- **Non vérifié** : le parcours complet depuis le bouton de l'app jusqu'à la réouverture avec la nouvelle sauvegarde. Si quelque chose coince, ouvre une issue.
- **Les anciennes sauvegardes** (`~/Library/Application Support/Constellation-sauvegardes`) peuvent peser lourd : celles des versions précédentes contiennent une copie complète des worktrees. Tu peux supprimer les plus anciennes.

## 0.3.23 (2026-11-05)

### Corrections importantes
Cette version corrige 18 bugs signalés par une deuxième analyse du code de Constellation. Plusieurs touchent à la sécurité : la mise à jour est conseillée.

**Sécurité**
- Cloner un dépôt : une adresse collée qui commence par `-` est refusée. Elle pouvait lancer une commande sur ton Mac.
- Les contrôles lancés dans le bac à sable ne lisent plus tes profils de shell (`~/.zshrc` et les autres), ni les `.env` des autres projets, ni les comptes Vercel, Stripe, Hugging Face et quelques autres. Ton `PATH` est lu une fois hors du bac à sable : `git`, `swift`, `node` ou `python3` marchent toujours.
- L'agent SSH défini par un profil de shell (1Password, Secretive) est maintenant fermé aux contrôles.
- Un double-clic sur un fichier ou un lien qui ouvre une app demande confirmation.

**Missions**
- « Interrompre » ne touche plus une tâche déjà finie.
- Une tâche arrivée au plafond de dépense attend vraiment ta décision.
- « Relancer » rend les corrections possibles.
- Quand l'agent dit ne pas avoir fini, une relecture favorable ne valide plus la tâche.
- Une tâche au bout de ses essais passe « Échouée ».
- Le nettoyage d'un worktree garde les fichiers ignorés par Git que personne n'a déclarés.

**Le reste**
- Un brouillon repris ne peut plus écraser un fichier modifié entre-temps.
- Les boucles décomptent leurs pauses, ne perdent plus une occurrence et affichent leur vraie durée.
- La dictée ne perd plus une phrase.
- Panneau Git : un double-clic sur Commit n'affiche plus de faux échec, et un fetch raté n'est plus noté comme fait.
- Un dépôt comme `moi.github.io` garde son nom au clonage.

### À savoir
- **Vérifié** : la suite de tests (794 tests, 14 ignorés, aucun échec) ; 15 des 18 bugs ont d'abord été reproduits par un test qui échouait. Une vraie mission a fini « Réussie et vérifiée » avec ses contrôles dans le nouveau bac à sable. Les règles du bac à sable ont été essayées sur de vrais chemins.
- **Non vérifié à l'écran** : la dictée, la confirmation à l'ouverture d'une carte et les brouillons. Si quelque chose coince, ouvre une issue.
- **Connu et non corrigé** : le bac à sable refuse une liste de fichiers sensibles, il n'autorise pas une liste fermée ; un fichier ordinaire d'un autre projet reste lisible. Un contrôle qui utilise une fonction du profil (`nvm use`, `conda activate`) ne la trouve plus. Un worktree gardé n'a pas de bouton « Supprimer quand même ».

## 0.3.22 (2026-11-05)

### Corrections importantes
Cette version corrige les 15 bugs signalés par une analyse du code de Constellation. Plusieurs touchent à la sécurité : la mise à jour est conseillée.

**Sécurité**
- Les contrôles lancés dans le bac à sable ne peuvent plus toucher aux fichiers d'une mise à jour en préparation : ces fichiers ont changé de dossier.
- Ils ne peuvent plus joindre l'agent SSH fourni par macOS ni celui que l'app connaît.
- Ils ne peuvent plus lire les comptes Codex et Gemini, ni les données de l'app. Le dossier du projet reste lisible.
- Un `CLAUDE.md`, `AGENTS.md` ou `GEMINI.md` écrit par un agent passe par ta validation avant d'entrer dans le projet. Avec le web ou un connecteur, l'agent ne peut pas les modifier avec ses outils d'édition.

**Missions**
- Des tâches qui dépassent leur durée limite en même temps gardent chacune leurs 3 essais, au lieu de 3, 2 et 1.
- Une clé de tâche contenant `/` ne bloque plus l'intégration.
- Une relance ou une acceptation pendant le contrôle final n'est plus perdue.

**Panneau Git**
- Un commit refusé garde ton message et ta sélection.
- Un fichier disparu de la liste ne fait plus échouer le commit.
- « Annuler les changements » garde aussi la version indexée.

**Le reste**
- Les brouillons de réponse restent attachés à leur tâche.
- Un export raté le dit.
- Un plan en attente n'est plus effacé avec les ordres terminés.
- Un champ `skills:` ambigu n'est plus réécrit.

### À savoir
- **Vérifié** : la suite de tests (759 tests, 14 ignorés, aucun échec). Le code de cette version a aussi téléchargé la vraie 0.3.21 sur GitHub, vérifié sa signature dans le nouveau dossier, puis l'a installée dans un dossier d'essai avec sauvegarde, et le dossier de travail s'est vidé. Les accès refusés du bac à sable ont été essayés sur de vrais chemins.
- **Non vérifié** : ce parcours lancé depuis le bouton de l'app, avec le contrôle du certificat et la réouverture ; le remplacement réel d'un script pendant une installation (seule l'écriture a été prouvée, puis refusée) ; les brouillons par tâche et la sélection du panneau Git à l'écran. Quatre des 15 bugs n'ont été confirmés qu'en lisant le code, sans reproduction. Si quelque chose coince, ouvre une issue.
- **Connu et non corrigé** : un agent SSH défini par un profil de shell (1Password, Secretive) reste joignable depuis le bac à sable. Cinq pistes écartées par l'analyse restent à vérifier : elles sont dans la feuille de route.

## 0.3.21 (2026-11-05)

### Nouveauté
- **Plan du coordinateur plus rapide** : il repère la structure du projet et lit seulement les fichiers utiles au découpage, au lieu de faire l'analyse à la place des agents. Sur un même projet, le plan est passé de 4 min 51 et 1,02 $ à 33 s et 0,11 $, avec une seule mesure de chaque.
- **Sonnet proposé par défaut pour le coordinateur** : si tu n'as jamais changé ce réglage, les nouvelles missions l'utilisent. Si tu as choisi un modèle, ton choix reste. Tu peux en changer dans **Nouvelle mission › Avancé** et dans les Réglages.

### Correction
- **Installation** : deux installations lancées en même temps pouvaient laisser une app vide dans Applications. Il ne peut plus y en avoir qu'une à la fois, et chacune a son propre dossier temporaire.

### À savoir
- **Revue et synthèse** : elles passent aussi sur Sonnet, car elles suivent le coordinateur tant que tu ne choisis pas un autre modèle pour la relecture. Ça coûte moins cher, mais une relecture plus légère peut laisser passer plus d'erreurs.
- **Vérifié** : la suite de tests (733 tests, 14 ignorés) ; un seul test de chronométrage a échoué, de très peu (0,62 s pour 0,6 s), alors que le Mac était chargé, et il a réussi 3 fois sur 3 lancé seul. Le plan avec les deux réglages a été mesuré sur un vrai projet. L'installation double a été testée avec le script, pas depuis l'app.
- **Non vérifié** : un plan de Sonnet exécuté jusqu'au bout d'une grosse mission, et le parcours complet depuis le bouton « Mise à jour » du tableau jusqu'à la réouverture. Si quelque chose coince, ouvre une issue.
- **Connu et non corrigé** : une analyse du code a signalé 15 bugs possibles, sur les missions, le bac à sable et le panneau Git. Aucun n'a encore été reproduit ni corrigé.

## 0.3.20 (2026-11-04)

### Nouveautés
- **Recherche automatique des mises à jour** : au lancement, puis toutes les 6 heures, et au retour sur l'app si ce délai est passé. Tu peux la désactiver dans Réglages › À propos. L'installation reste ton choix, car elle ferme l'app.
- **Pastille rouge sur Réglages** : elle signale qu'une mise à jour attend, à l'accueil comme sur le tableau. Un clic ouvre les Réglages sur « À propos ».

### Correction
- **Bouton « Mise à jour » du tableau** : il affichait « Constellation va se fermer et se rouvrir » sans jamais rien installer. L'app ferme maintenant sa fenêtre avant de quitter. Si tu refuses de quitter, par exemple à cause d'une console active, l'installation s'annule et un message te le dit.
- Une recherche ne peut plus démarrer pendant une installation.

### À savoir
- **Depuis une version plus ancienne que la 0.3.20** : installe depuis **Réglages › À propos**. Le bouton « Mise à jour » du tableau de ces versions reste bloqué.
- **Vérifié** : une app en version ancienne a trouvé la vraie dernière version sur GitHub et affiché la pastille sur le tableau ; la fermeture, l'annulation et « Quitter » ont été essayés sur une copie de l'app.
- **Non vérifié** : la pastille à l'accueil, l'ouverture sur « À propos », la recherche au bout de 6 heures en conditions réelles, et le parcours complet depuis le bouton du tableau jusqu'à la réouverture. Si quelque chose coince, ouvre une issue.

## 0.3.19 (2026-11-04)

### Corrections importantes
Cette version corrige une quarantaine de bugs, dont plusieurs pouvaient faire perdre du travail. La mise à jour est conseillée.

**Missions qui finissaient « non vérifiées »**
- En mode délégué, sans web ni connecteur, et avec le bac à sable actif, la case d'autorisation des contrôles est maintenant cochée par défaut. Tu peux la décocher.
- Les simples lectures du dossier (`test`, `grep`, `wc`…) tournent seules dans le bac à sable, même avec le web.
- Si une tâche a besoin du web et que la mission ne l'a pas, le plan le signale et l'app te dit que relancer ne changera rien.

**Pertes de travail**
- Studio Code : `⌘Z` après un changement de fichier ne touche plus l'autre fichier, et les brouillons vont au bon fichier.
- Studio Markdown : fermer juste après avoir tapé ne perd plus le texte, et la sauvegarde n'écrase plus un fichier modifié par un agent.
- Panneau Git : « Annuler » ne perd plus de travail avec les noms contenant un guillemet ou un `*`.
- « Fermer l'espace » demande confirmation, et un espace fermé peut être rétabli. Un projet retiré retrouve son tableau et son historique quand tu rouvres son dossier.
- Un fichier illisible ou écrit par une version plus récente n'est plus écrasé.
- Éditeurs de skills et de sous-agents : « Annuler » garde tes modifications, et enregistrer ne retire plus de réglages.
- Enregistrer suit les liens symboliques, et garde les fins de ligne mixtes et le BOM.
- `⌘Z` rend les groupes et les boucles, et demande confirmation avant d'arrêter une console active.

**Ce qui ne marchait pas**
- Une console inactive depuis 60 s n'est plus marquée « a besoin de toi ».
- Un nom de fichier avec accent ne fait plus échouer le commit. Le premier commit d'un dépôt, un projet dans un sous-dossier d'un dépôt et les suppressions déjà indexées fonctionnent.
- « Arrêter » arrête vraiment une console.
- Une boucle ne s'arrête plus si l'agent répond en moins de 2 minutes.
- Une transmission reste dans son projet et ne répond plus à une question de confiance à ta place.
- La page Consommation ne compte plus environ trois fois trop de tokens en sortie. Tes totaux vont donc baisser.
- Coller une console dans un autre projet ne garde plus l'ancien dossier ni le mode sans permissions.
- Les shells fish et tcsh ne cassent plus les commandes de l'app.
- Le micro ne reste plus allumé après la dictée, et fermer un studio pendant une génération ne perd plus le résultat.

### À savoir
- **Décision de sécurité** : avec la case cochée par défaut, le code d'un projet que tu as cloné peut tourner seul dans le bac à sable, avec le réseau ouvert. Tes secrets courants restent illisibles. Décoche la case si tu ne fais pas confiance au projet.
- **Vérifié en conditions réelles** : une mission avec le web et la case décochée, finie « Réussie et vérifiée » ; le clavier et le clic dans les cartes, sur une copie de l'app. Le filtre des simples lectures a passé 111 commandes pièges dans zsh, bash et sh, mais pas de test d'attaque complet.
- **Non vu à l'écran** : les nouvelles fenêtres de confirmation, le menu « Rétablir un espace fermé… », le bouton « Relier à un dossier… » et le panneau Git à la souris. Leur logique est testée. Le nouveau réglage « a besoin de toi » n'a pas tourné dans une vraie console, ni fish avec le vrai shell. Si quelque chose coince, ouvre une issue.
- **Connu et non corrigé** : après « Relier à un dossier… », une mission finie garde son ancien chemin. Un dossier créé ailleurs peut encore arriver dans le projet avec son propre `.git`.

## 0.3.18 (2026-11-04)

### Nouveauté
- **Modèle de la relecture** : dans **Nouvelle mission › Avancé** et dans les Réglages, tu peux choisir le modèle de la revue indépendante : « Comme le coordinateur » (par défaut), Sonnet, Haiku ou Opus. Un modèle plus léger coûte moins cher mais peut laisser passer plus d'erreurs. Si tu ne touches à rien, rien ne change.

### À savoir
- Si tu décoches la revue indépendante, les relectures qui tournent quand même, comme celle de fin de mission, utilisent le modèle du coordinateur.
- Essayé avec le faux CLI des tests, pas encore dans une vraie mission. Si quelque chose coince, ouvre une issue.

## 0.3.17 (2026-11-04)

### Corrections importantes
- **Éditeur de ticket et d'événement au clavier** : `Retour` l'ouvrait, mais le clavier restait sur le tableau. On ne pouvait rien y taper et `Échap` ne le fermait pas. Le clavier y entre maintenant, ce que tu tapes s'ajoute à la fin du titre, `Échap` ferme et le clavier revient au ticket ou au jour.
- **Calendrier** : `Retour` de nouveau sur un jour ouvre l'événement suivant. Supprimer un événement ferme son éditeur.

### Sécurité
- **Sous-dossiers protégés** : pendant un contrôle, un sous-dossier qui contient un `.git`, un `.claude` ou un `CLAUDE.md` ne peut plus être déplacé ni supprimé. Il ne peut donc plus sortir du projet et y revenir modifié. Ce qu'il contient reste modifiable normalement.
- **Processus en session propre** : dans le worktree d'une tâche, ce qu'un contrôle ou une session d'agent a lancé avec `setsid` est arrêté à sa fin, et aussi à la fermeture de l'app.
- **Secrets du profil sous fish** : les variables sont retirées une par une, une écriture plus sûre selon la version de fish.

### Autres corrections
- Une note de mission suivie d'une autre reste traduite dans l'app en anglais.

### À savoir
- **Limites des sous-dossiers** : un dossier créé ailleurs peut encore arriver dans le projet avec son propre `.git`. Les dossiers que les outils reconstruisent (`node_modules`, `.venv`, `venv`, `.build`…) ne sont pas fixés. Au-delà d'un très grand nombre de sous-dossiers protégés, certains ne le sont pas non plus, et le contrôle le signale.
- **Processus non arrêtés, volontairement** : dans un dossier sans worktree, un processus en session propre peut appartenir à un autre contrôle ou à un autre agent. Un daemon qui change de dossier ou se relance y échappe aussi.
- **Clavier** : testé avec de vraies touches et de vrais clics envoyés par macOS, pas avec VoiceOver.
- **Mise à jour** : essayée pour de vrai de la 0.3.15 à la 0.3.17 depuis l'app.
- **Non essayé** : l'écriture pour fish n'a pas tourné dans un vrai fish. Si quelque chose coince, ouvre une issue.

## 0.3.16 (2026-11-04)

### Corrections importantes
Ces défauts existaient dans la 0.3.15. La mise à jour est conseillée.
- **Livrable perdu** : une tâche dont le seul résultat était un fichier ignoré par Git, dans un dossier, était déclarée réussie et le fichier n'arrivait pas dans le projet. Ce cas est maintenant signalé, et le worktree qui contient le fichier est gardé.
- **Acceptation qui restait** : après une acceptation manuelle puis un conflit, une nouvelle tentative pouvait passer pour acceptée sans contrôle.
- **Erreur d'écriture pendant l'intégration** : le message poussait à accepter sans preuve. Il propose maintenant « Réessayer l'intégration ».
- **Caches** : un simple `__pycache__` ou `node_modules` n'empêche plus de supprimer un worktree.
- **Contrôle final** : une tâche sans contrôle ne fait plus sauter la relecture finale quand le plan répète un contrôle.

### Nouveautés
- **Clavier dans les cartes** : dans un kanban, ↑ entre dans les tickets, les flèches les parcourent, Retour en modifie un et ⌥ ← → change sa colonne. Dans un calendrier, les flèches parcourent les jours, Retour ouvre le premier événement du jour et ⇧ Retour en ajoute un. Un contour montre où tu es.
- **Lisibilité** : les couleurs d'état et de groupe atteignent un contraste de 4,5:1 en clair et en sombre. Les plus petits textes passent à 11 pt. Sur la page Consommation, « Cache écrit » devient violet pour mieux se distinguer de « Cache lu ».
- **Réduire les animations** s'applique aussi à la bordure des cartes. Il manquait des traductions anglaises dans les menus du tableau.

### Sécurité
- **Plus de restes après un contrôle** : ce qu'un contrôle laisse tourner en arrière-plan, par exemple avec `(cmd &)`, est arrêté à sa fin.
- **Secrets du profil de shell** : les variables reconnues comme des clés ou des mots de passe, exportées par ton profil, sont retirées des contrôles en bac à sable. Si le profil est illisible, le contrôle le signale dans sa note.

### Moins de tours perdus
- Les agents savent maintenant quelles commandes Bash leur sont permises. Sur 6 vraies missions, toutes réussies, aucun Bash n'a été refusé, contre 2 ou 3 par mission avant.

### À savoir
- **Non essayé en conditions réelles** : le vrai clavier (testé avec des touches simulées), VoiceOver, et `Échap` pour fermer l'éditeur d'un ticket ou d'un événement, qui n'a pas réagi aux touches simulées. Si quelque chose coince, ouvre une issue.
- **Connu et non corrigé** : un processus lancé avec `setsid` survit quand même à son contrôle. Le filtre des secrets se base sur les noms et les valeurs des variables : il peut en manquer, et il n'a pas été essayé avec le shell fish.
- **Choix prudent** : un dossier `dist`, `build` ou `target` ignoré par Git, dans le périmètre d'une tâche, garde son worktree pour ne pas perdre un livrable. Tu devras parfois le nettoyer à la main.

## 0.3.15 (2026-11-04)

### Nouveautés
- **Historique des missions** : le bouton **Missions** de l'accueil les retrouve toutes, avec une recherche. Tu peux en rouvrir une, la refaire, copier son résultat ou l'enregistrer, clés masquées.
- **Modifier la demande** : après un plan refusé, tu reprends ta demande sans tout réécrire.
- **Clavier et VoiceOver** : Tab, ⇧Tab et ⌥ Flèches passent d'une carte à l'autre, Retour l'ouvre. Chaque carte s'annonce à VoiceOver. Un fichier qui n'est pas un document demande confirmation avant de s'ouvrir.

### Sécurité
- **Contrôles en bac à sable** : les contrôles ne peuvent plus modifier les données Git ni la configuration de Claude, à aucune profondeur du dossier, ni lancer d'apps, ni changer les préférences, ni lire le presse-papiers.

### Fiabilité
- **Arrêt brutal pendant l'intégration** : au retour, la mission signale le doute au lieu de réappliquer le patch. Tu choisis entre « Déjà dans mes fichiers » et « Appliquer ».
- **Projet dans un sous-dossier d'un dépôt** : les worktrees et l'intégration le prennent en compte.
- **Une seule instance de l'app à la fois** : deux instances ne peuvent plus écraser les données l'une de l'autre.
- **Suppressions plus sûres** : supprimer une mission garde les worktrees qui contiennent encore du travail et les nomme.
- **Consignes des agents** : un contrôle que l'agent n'a pas pu lancer ne fait plus passer son travail pour partiel, ce qui bloquait parfois une mission.
- **Limites d'usage** : elles sont mieux reconnues, ainsi que leur heure de fin.

### Moins de tokens, plus de vitesse
- Le diff envoyé en relecture est plafonné. Les appels hors mission passent par Sonnet, sans connecteurs ni skills.
- La sauvegarde quitte le fil principal, et la page Consommation se rouvre beaucoup plus vite.

### À savoir
- **Bac à sable** : c'est une barrière de plus, pas une garantie. Ce qu'un contrôle écrit dans le dossier ou un cache peut s'exécuter plus tard. Dans un dossier sans worktree, `git add` et `git commit` échouent pendant un contrôle.
- **Non essayé en conditions réelles** : le vrai clavier et VoiceOver, les boutons « Déjà dans mes fichiers » et « Appliquer », un arrêt forcé pendant l'intégration, l'alerte de deuxième instance. Ces points ne sont couverts que par des tests automatiques. Si quelque chose coince, ouvre une issue.
- **Connu et non corrigé** : un processus lancé en arrière-plan par `(cmd &)` survit à la fermeture de l'app.

## 0.3.14 (2026-11-03)

### Corrections
- **Fichiers qui ne sont pas en UTF-8** : une tâche isolée dans un worktree pouvait les corrompre à l'intégration. Le patch garde maintenant les octets exacts.
- **Documents générés** : la fin du texte pouvait se perdre. Ils sont lus jusqu'au bout, sans couper les accents.
- **Stockage plus sûr** : une mission illisible n'emporte plus les autres et le fichier est mis de côté, avec un message. Une écriture ratée est réessayée. Les petits fichiers illisibles (profils, mémoire, préréglages) sont mis de côté au lieu d'être écrasés.
- **Suppressions moins risquées** : rien n'est supprimé si l'archive échoue. Les cartes contenant du travail et les documents demandent confirmation. Un fichier déposé n'en écrase plus un autre.
- **Notes et code** : une note illisible n'est plus ouverte comme une note vide. Une écriture ratée est signalée et le texte reste à l'écran. Un fichier Latin-1 reste en Latin-1.
- **Mises à jour** : si l'installation échoue, l'ancienne app est remise en place.
- **Dépense maximale mieux tenue** : chaque session reçoit sa part et s'arrête à cette limite, en gardant sa conversation. Décocher « Suspendre » à la limite accorde la moitié de plus, pas un compte ouvert. Une mission arrêtée par la dépense te le signale.
- **Modèle** : une tâche sans modèle prévu tourne sur Sonnet, plus sur le défaut du compte.
- **Limite d'usage** : le plan et les relectures attendent aussi la fin de la limite. Une erreur de compte n'est plus relancée en boucle.
- **Sans Claude Code ni compte** : la fenêtre de mission le dit et ne lance rien.
- **Secrets** : les jetons les plus courants sont masqués dans le journal et le diagnostic.

### À savoir
- **Dépense maximale** : elle reste dépassable. Le plan, les relectures et la synthèse n'ont pas de part réservée, et une session peut dépasser un peu au sein d'un tour. L'arrêt à la limite n'a pas encore été vécu dans une vraie mission.
- **Contrôles** : ils s'exécutent toujours sans bac à sable, avec tes droits. La protection des scripts est partielle.
- **Non vérifié à l'écran** : plusieurs de ces corrections sont couvertes par des tests sans avoir été essayées dans l'interface. Si quelque chose coince, ouvre une issue.

## 0.3.13 (2026-11-03)

### Nouveautés
- **Les missions consomment moins** : le modèle choisi par le plan s'applique enfin à chaque tâche, Sonnet par défaut. Avant, un ancien réglage pouvait tout faire tourner sur le modèle par défaut du CLI, même quand le plan avait choisi autre chose. **Ton réglage de modèle des tâches revient une fois à « Selon la tâche »** : remets-le si tu l'avais choisi exprès. Les sessions d'agents chargent aussi moins d'outils et lisent de façon plus ciblée.
- **La limite d'usage ne fait plus échouer les tâches d'agents** : elles attendent l'heure annoncée, puis reprennent la même conversation, sans essais inutiles.
- **Dépense maximale** par mission, dans les réglages avancés. Elle est facultative et peut être dépassée, car les sessions en cours finissent.
- **Plus de textes en anglais** : les messages du moteur avec des valeurs suivent maintenant la langue de l'interface.

### Corrections
- **Le coût affiché était trop haut** : les relances d'une même conversation étaient additionnées. Les anciennes missions affichent aussi le bon montant.
- **Moins de fausses réussites** : un agent qui déclare un échec ou un travail partiel passe en « à vérifier », même si ses contrôles réussissent. Une mission sans tâche requise n'est plus jamais « vérifiée », et un livrable ignoré par Git bloque la réussite.
- **Moins de risques de perte** : un fichier de missions illisible n'est plus pris pour un historique vide. « Annuler les changements » ne supprime rien sans copie de sécurité. Une console dont le dossier a disparu ne démarre plus dans ton dossier personnel.
- **Sécurité** : les agents n'ont plus que des commandes de lecture exactes. Avec le web ou un connecteur, seule Constellation lance les contrôles, et une commande approuvée attend ton accord si un agent a modifié `package.json`, un `Makefile` ou un script.
- **Accessibilité** : les principales zones cliquables sont visibles par VoiceOver.

### À savoir
- La protection des scripts est partielle : la liste des fichiers surveillés n'est pas complète, et la case qui autorise toutes les commandes passe outre.
- Une mission qui se terminait seule peut maintenant s'arrêter pour te demander de juger une tâche.
- La pause à la limite d'usage et VoiceOver n'ont pas été essayés en conditions réelles. Si quelque chose coince, ouvre une issue.

## 0.3.12 (2026-11-03)

### Nouveautés
- **Des connecteurs dans les missions** : Notion, Gmail, Vercel… Tu coches, mission par mission, ceux que les agents peuvent utiliser. Rien n'est coché par défaut, et seuls les connecteurs cochés sont chargés. Le coordinateur et le relecteur n'y ont pas accès.
- **L'interface est maintenant disponible en anglais presque partout** : tutoriel, Réglages, bibliothèque de skills, missions, carte des missions, fenêtres d'outils et messages.

### À savoir
- **Un connecteur peut agir hors de ton Mac.** Constellation ne sait pas quels outils écrivent, et les agents ne te demandent pas de confirmer chaque action. Web + connecteur et mode délégué + connecteur exigent donc une case d'accord pour la mission.
- **Les actions externes ne sont pas vérifiées.** Constellation ne voit pas l'état réel du service : chaque appel apparaît dans l'activité, avec la mention « Actions externes non vérifiées ».
- **Une relance ou une correction peut répéter une action.** L'agent est prévenu des appels déjà faits, mais rien ne le garantit : vérifie le résultat dans le service concerné.
- Les connecteurs s'installent et s'authentifient dans Claude Code, pas dans l'app. Chaque session d'agent consomme un peu plus quand un connecteur est coché.
- Restent en français : les consignes envoyées aux agents, le contenu des modèles de skills, les mots reconnus par les commandes vocales et la barre de commande, et quelques messages techniques du moteur.

## 0.3.11 (2026-11-02)

### Nouveautés
- **Se déplacer et zoomer devient simple** : deux doigts ou la molette déplacent le tableau partout, même au-dessus d'une carte. Le pincement et ⌘ + molette zooment autour du pointeur. Tu peux dépasser les bords pour sortir une carte de sous les barres d'outils. À la souris, maintiens le clic droit et glisse pour te déplacer ; un simple clic droit ouvre toujours le menu. Les boutons + et − avancent par paliers réguliers.
- **Un fond vivant** : un réseau de points lumineux à l'accueil, et une version plus discrète derrière les cartes du tableau. Il s'anime quand un agent travaille. Il suit ta couleur d'accent.
- **Des missions plus lisibles** : la carte du coordinateur montre l'avancement, la durée, le coût (« au moins X $ »), le plafond d'appels et les dernières actions. Les tâches ont une pastille d'état et un badge de modèle.
- **Des animations** : halo sur les tâches en cours et signaux sur les liens actifs. « Réduire les animations » coupe tout mouvement.

### Ce qui change à l'usage
Une console ou une page web ne défile que si tu as **cliqué dedans**. Clique sur le tableau vide pour lui rendre le défilement.

### Corrections
- **Moins de consommation au repos** : la pastille d'une console inactive pulsait 30 fois par seconde, même fenêtre cachée. Sur une version de test, la consommation au repos passe d'environ 22 % à 3 % de processeur.
- Une carte ne peut plus rester coincée sous la barre d'outils.

### À savoir
Pendant qu'une mission travaille, le fond et les animations consomment davantage de processeur : environ 30 % sur une version de test. Si l'app te semble lourde, active « Réduire les animations ». Les gestes réels au trackpad et à la souris, ainsi que le clic droit sur une page web, n'ont pas été couverts par les tests automatiques : si quelque chose ne va pas, ouvre une issue.

## 0.3.10 (2026-11-02)

### Nouveautés
- **Des missions sur tous les sujets** : recherche, rédaction, analyse, organisation ou code. Depuis l'accueil, **Nouvelle mission** crée toute seule un dossier de travail dans `~/Documents/Constellation`. Git reste discret quand il n'y a pas de dépôt.
- **Une relecture indépendante, activée par défaut** : une session séparée juge chaque tâche selon ses critères et peut demander une correction. L'app dit toujours ce qui a été fait : « Vérifiée par commandes », « Vérifiée par commandes et relue » ou « Validée par relecture ». Une relecture réduit les erreurs, sans rien garantir.
- **Des sous-agents visibles sur plusieurs niveaux** : un agent peut créer un sous-agent, qui peut en créer un autre (4 niveaux par défaut, jusqu'à 6). Chacun apparaît sur le tableau.
- **Un modèle selon la tâche** : Haiku, Sonnet ou Opus sont choisis tâche par tâche. Tu peux aussi imposer un modèle à toute la mission.
- **Fable au choix** : si tu le sélectionnes, Constellation vérifie ton accès. Sans accès ni crédits, la tâche passe sur Opus et l'app te le signale.
- **La recherche sur le web** : activée par défaut dans un nouveau dossier, désactivée par défaut dans un projet existant.
- **Les livrables** : les fichiers produits s'ouvrent d'un clic. Les fichiers exécutables s'affichent seulement dans le Finder.
- **Moins d'interruptions en mode assisté** : tu valides le plan, puis les sous-agents et les corrections avancent seuls. Les commandes inconnues, les questions et les conflits t'attendent toujours.

### Consommation
La relecture par défaut consomme nettement plus de quota : lors d'un essai, une recherche sur le web en deux tâches a coûté environ 2,50 $ selon la CLI, sans aller jusqu'au bout. Tu peux la décocher pour une petite mission de code bien testée. Une mission se suspend au bout de 80 appels à Claude, et tu peux lui en accorder 40 de plus. Le coût s'affiche sous la forme « au moins X $ ».

### Sécurité
- Avec le web activé, seules les commandes de ton plan s'exécutent sans te demander. Les commandes des sous-agents attendent ton accord.
- **Une limite demeure** : une page web piégée pourrait tromper un agent. Il pourrait alors modifier des fichiers, envoyer leur contenu vers un site, ou glisser du code dans une commande que tu as approuvée, qui tournerait avec tes droits. Laisse le web désactivé sur les projets sensibles.

### Corrections
- Une mission ne reste plus bloquée quand deux agents créent des sous-agents sur les mêmes fichiers, ni quand l'app est fermée pendant la rédaction d'une correction.
- Une correction en attente reprend après une fermeture de l'app.

### À savoir
Le parcours complet dans l'interface n'a pas encore été essayé en conditions réelles : les essais réels ont été faits sur la CLI. Si quelque chose ne va pas, ouvre une issue.

## 0.3.9 (2026-11-01)

### Nouveautés
- **Nouvelle icône** : une constellation en forme de C, avec une étoile corail qui brille sur un ciel de nuit. Elle reste reconnaissable dans le Dock comme dans les listes du Finder.

Le Dock peut garder l'ancienne icône un moment après la mise à jour : elle se met à jour au prochain redémarrage du Dock ou du Mac.

## 0.3.8 (2026-11-01)

### Corrections
- **Tes projets ne peuvent plus disparaître** : si la liste des projets est abîmée, Constellation la reconstruit à partir de ses fichiers et garde une copie de l'ancienne. Un projet illisible reste dans la liste au lieu d'être oublié, et un bandeau te prévient.
- **Enregistrement surveillé** : si le disque refuse un enregistrement (disque plein, droits), un bandeau le dit et Constellation réessaie toutes les 10 secondes, au lieu de faire comme si tout était enregistré.
- **Plus d'appels bloqués** : les boucles d'automatisation et le planificateur d'ordres ne peuvent plus rester figés sur un appel à Claude Code. Le délai s'applique toujours et arrête aussi les programmes lancés par l'appel.
- **Missions plus fiables** : la dernière ligne d'une session est toujours lue avant sa fin, ce qui évitait parfois une relance inutile.
- **Messages aux consoles** : deux messages envoyés coup sur coup à la même console ne se mélangent plus.
- **Mises à jour** : les fichiers temporaires sont supprimés après chaque essai.

### Sécurité
- **Contrôles automatiques plus stricts** : une commande de contrôle n'est lancée sans ton accord que si elle ne contient que des options sûres. Les options qui lancent un autre programme (`go test -exec`, `pytest -p`, `make -f`…) demandent ta validation.
- **État des consoles protégé** : chaque console a ses propres hooks, signés par un jeton secret. Un programme lancé dans la console ne peut plus faire croire que l'agent attend ou a fini.
- **Mises à jour liées à ton certificat** : une mise à jour n'est acceptée que si elle est signée avec le même certificat que l'app installée.

### Confort
- **Tableau plus fluide** avec plusieurs missions et consoles actives : seules les zones qui changent sont redessinées, et l'animation s'arrête quand la fenêtre est cachée.
- **Moins d'énergie au repos** : l'état des consoles n'est relu que lorsqu'il change, et moins souvent quand l'app est en arrière-plan.

### Accessibilité
- **VoiceOver lit le tableau** : tâches de mission, sous-agents et groupes sont annoncés en mots, et une tâche s'ouvre en l'activant.
- **Textes plus lisibles** : aucun texte de l'interface ne descend sous 11 points, et les barres d'outils ne coupent plus leurs libellés.
- **Boutons nommés** : les boutons faits d'une seule icône ont un nom pour VoiceOver et une bulle d'aide.
- **Interface anglaise complétée** : les derniers textes en français seulement sont traduits.

## 0.3.7 (2026-10-29)

### Nouveautés
- **Missions expliquées en clair** : chaque tâche a un encadré « En clair » qui dit ce qui s'est passé, pourquoi et quoi faire, avec le nom des boutons. Le détail technique reste disponible dessous. Les contrôles sont écrits en phrases (« le fichier rapport.md contient « Gravité » »), et la carte du coordinateur résume la mission en une phrase.
- **Essais automatiques** : un agent qui plante, renvoie une erreur ou dépasse son temps est relancé tout seul, deux fois, dans sa conversation. Pendant ce temps, les autres agents terminent leur travail.
- **Missions plus rapides** : une tâche terminée laisse la main tout de suite à la suivante (0,07 s au lieu d'environ 1 s entre deux tâches qui se suivent).

### Corrections
- **« Reprendre » relance vraiment les sous-agents** après une fermeture de Constellation en pleine mission. Ils repartent là où ils s'étaient arrêtés quand leur conversation est connue. Avant, le bouton rouvrait la mission sans rien relancer, puis disparaissait.
- **Tâches bloquées** : une tâche bloquée par une autre repart dès que celle-ci a réussi ou que tu l'as acceptée.
- **Un agent arrêté ne peut plus faire quitter Constellation**, ce qui arrêtait tous les autres agents.
- **Dossier partagé** : une tâche réussie ne finit plus « Non vérifiée » parce que d'autres agents écrivaient en même temps. Sa vérification attend qu'ils aient fini.

## 0.3.6 (2026-10-29)

### Nouveautés
- **Tâches de mission déplaçables** : sur le tableau, glisse les tâches d'une mission lancée, et donc leurs sous-agents, pour les ranger comme tu veux. Leurs liens suivent. Elles restent à leur place par rapport au coordinateur : si tu déplaces sa carte, toute la mission suit. Un clic ouvre toujours la tâche, et ⌘Z annule un déplacement.
- **Clic droit sur une tâche** : « Remettre à sa place » ou « Ranger la mission automatiquement ».

### Corrections
- **Contrôles de mission avec des accents** : un contrôle comme `grep -q 'Gravité' rapport.md` échouait toujours, même quand le fichier contenait le mot. macOS transmettait les accents sous une autre forme (« é » devenait « e » + accent). Les tâches échouaient alors après plusieurs tentatives, ou posaient des questions sans issue. Le texte arrive maintenant intact : contrôles et sessions des missions, automatisations, générateurs, commandes du panneau Git et messages de commit.

## 0.3.5 (2026-10-29)

### Nouveautés
- **Barres de progression** pour l'agent de chaque console Claude Code (sous son titre) et pour chacun de ses sous-agents (dans leur bulle). Quand l'agent tient une liste de tâches, la barre affiche les tâches faites et la tâche en cours. Sinon, elle avance avec ses étapes (chaque outil utilisé) et le temps passé. C'est alors une estimation, qui n'arrive au bout qu'une fois le travail fini.
- **Skill find-skills** dans la bibliothèque : les agents et sous-agents cherchent un skill utile, d'abord parmi ceux installés, puis sur skills.sh. Ils proposent ce qu'ils trouvent et n'installent rien sans ton accord.
- **Réglages › À propos** : liens vers la page GitHub de Constellation et vers la page pour signaler un problème.

### Corrections
- **Déconnexion** : la fenêtre Réglages se ferme et ne peut pas être rouverte tant que tu n'es pas reconnecté. Avant, elle restait ouverte et modifiable.

## 0.3.4 (2026-10-29)

### Nouveautés
- **Plein écran au lancement** : la fenêtre s'ouvre en plein écran, puis comme tu l'as laissée la dernière fois.

### Corrections
- **Accès aux Documents demandé à chaque lancement** : l'app est maintenant signée avec un certificat qui ne change pas d'une version à l'autre, et macOS se souvient de tes autorisations (Documents, micro). Il peut les redemander une dernière fois après cette mise à jour.
- **Déconnexion** : les fenêtres ouvertes (Réglages, À propos, Mises à jour…) se ferment et ne recouvrent plus la page de connexion.
- **Barres de défilement** : elles n'apparaissent plus que pendant le défilement et n'encadrent plus le tableau, même en plein écran.

## 0.3.3 (2026-10-29)

### Nouveautés
- **Quota de ton abonnement Claude dans la barre du haut** : la part utilisée de la session de 5 h et de la semaine, avec l'heure de réinitialisation. Au survol ou dans la page Consommation, tu vois aussi la part restante. Les chiffres viennent de Claude Code et s'actualisent quand une console Claude Code du tableau reçoit une réponse.
- **Bouton de compte** en haut à droite, à côté des réglages : il affiche le compte connecté et son offre, et permet de se déconnecter, ou de se connecter si tu utilises Constellation sans compte.

### Corrections
- **Claude Code introuvable** : si Claude Code était installé avec sa commande officielle, Constellation pouvait rester bloquée sur la page « Installer Claude Code ». Elle le trouve maintenant dans ses dossiers d'installation habituels. La même correction s'applique aux missions, aux automatisations et aux générateurs.

## 0.3.2 (2026-10-29)

### Nouveautés
- **Mac Intel pris en charge** : l'app est désormais universelle (Apple Silicon et Intel), toujours à partir de macOS 14.
- **Exporter un diagnostic** (menu Aide) : une archive à joindre à un signalement, avec la version, le système, les réglages de l'app sans clés ni jetons, et le journal de la session. Ton dossier personnel et ton nom d'utilisateur sont masqués, et rien n'est envoyé automatiquement.
- **VoiceOver** : les boutons qui n'affichent qu'une icône ont maintenant un nom.

### Corrections
- **Récupération des projets** : si le fichier d'un projet manque ou a été coupé (par exemple après un plantage pendant une sauvegarde), sa copie précédente est maintenant bien rechargée. Avant, le projet disparaissait du tableau.
- **Détection des CLI** : elle ne peut plus rester bloquée si ton fichier de démarrage du shell attend une saisie.

## 0.3.1 (2026-10-29)

### Nouveautés
- **Vérification du système au lancement** : Constellation s'assure d'abord qu'elle tourne sur macOS 14 ou plus récent. Sinon, elle explique pourquoi et se ferme, sans toucher à aucune donnée.
- **Nom unifié** : l'app, ses réglages et ses données s'appellent désormais tous Constellation. Les réglages et données des versions précédentes sont repris automatiquement au premier lancement.

## 0.3.0 (2026-10-29)

### Nouveautés
- **Compte Claude** : page de connexion au premier lancement (abonnement Claude ou compte Anthropic Console), état du compte dans Réglages, déconnexion depuis le menu.
- **Mises à jour** depuis ce dépôt, vérifiées par signature Ed25519.

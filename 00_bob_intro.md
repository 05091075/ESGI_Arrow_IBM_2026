# C'est quoi Bob ?
> Fiche 00 · Mode opératoire · Bob IDE (vérifié octobre 2025)

📚 **Doc officielle** : [bob.ibm.com](https://bob.ibm.com) · [IBM Bob — Welcome](https://bob.ibm.com/docs/ide)

---

## En une phrase

> **IBM Bob est un assistant IA de développement logiciel qui agit directement dans votre projet** : il lit vos fichiers, écrit du code, exécute des commandes, et peut utiliser des outils externes — tout ça depuis une interface de chat.

Ce n'est pas un chatbot. C'est un **agent** capable d'agir sur votre codebase.

---

## Les fonctions utiles pour un challenge

Plutôt qu'un comparatif concurrentiel (les outils évoluent vite et les périmètres sont difficiles à comparer équitablement), voici ce qui compte pour un challenge court :

- **Travailler dans le projet** : Bob lit l'ensemble de votre codebase, modifie les fichiers et exécute des commandes — tout depuis le chat.
- **Garder les consignes du projet** : le fichier `AGENTS.md` (et, en option, le dossier `.bob/rules/`) mémorise le contexte pour toutes vos conversations dans ce dossier.
- **Passer de la compréhension à l'implémentation** : Ask pour explorer, Plan pour structurer, Agent pour réaliser — dans la séquence qui convient à la situation.

---

## Les 3 modes essentiels

> 📚 Doc : [Modes — IBM Bob](https://bob.ibm.com/docs/ide/features/modes)

Bob a trois modes built-in. Choisir le mode adapté à la tâche en cours est la première décision à prendre.

### 💬 Mode Ask — *"Explique-moi"*
- Répond à des questions, explique du code, donne des conseils
- Consomme le moins car ne fait pas d'actions
- → À utiliser pour : comprendre un concept, analyser un énoncé, explorer une question

### 🗺️ Mode Plan — *"On réfléchit ensemble"*
- Analyse le besoin et prépare les étapes de réalisation
- → À utiliser pour : choisir une stack, concevoir un schéma de données, planifier l'implémentation

### 🤖 Mode Agent — *"Fais-le"*
- Lit, écrit et modifie vos fichiers, exécute des commandes, appelle des MCPs
- **Modifie réellement votre projet** — demande confirmation avant chaque action (sauf si auto-approuvé)
- → À utiliser pour : générer du code, corriger un bug, créer des fichiers, exécuter des tests

> **Parcours pédagogique** : Ask → Plan → Agent est un enchaînement utile pour les tâches incertaines. Pour une correction simple et bien définie, commencer directement en Agent est tout à fait cohérent.
>
> 📚 Doc : [Modes IBM Bob](https://bob.ibm.com/docs/ide/features/modes) · Voir fiche `01_bob_bobcoin.md` pour la consommation selon les usages.

---

## Ce que Bob peut faire concrètement

Basé sur la [documentation officielle](https://bob.ibm.com/docs/ide) :

### Outils natifs
- **Lire des fichiers** : Bob lit votre codebase entier si nécessaire
- **Écrire et modifier des fichiers** : outils de modification ciblée (diffs) et réécriture complète selon le besoin
- **Exécuter des commandes** : `npm install`, `python script.py`, `git commit`…
- **Rechercher dans le code** : grep, recherche de symboles, références croisées

### Via MCP (Model Context Protocol)
- **Récupération de page web** : `mcp-server-fetch` permet de lire le contenu d'une URL ; pour une recherche web, un serveur dédié comme Tavily est nécessaire
- **APIs externes** : n'importe quelle API peut être connectée via MCP
- **Outils custom** : vous pouvez écrire votre propre serveur MCP

> 📚 Doc MCP : [Using MCP in Bob](https://bob.ibm.com/docs/ide/features/mcp/using-mcp-in-bob)

### Via Skills
- Des instructions spécialisées activables à la demande (ex : "carbon-builder", "terraform"…)
- Les skills doivent être disponibles dans l'environnement (`~/.bob/skills/` ou `.bob/skills/` dans le projet)

> 📚 Doc Skills : [Skills — IBM Bob](https://bob.ibm.com/docs/ide/features/skills)

---

## L'interface en 30 secondes

```
┌─────────────────────────────────────────────────┐
│  Explorateur de fichiers     │  Éditeur de code  │
│  (votre projet)              │                   │
│                              │                   │
├──────────────────────────────┤                   │
│  Chat Bob                    │                   │
│  > Votre message ici...      │                   │
│  [Ask] [Plan] [Agent]  ←─────── sélecteur de mode│
│  (à gauche du champ de saisie)                   │
└─────────────────────────────────────────────────┘
```

> ⚠️ La position exacte des contrôles dépend de la version de Bob installée. Référez-vous à la [documentation interface](https://bob.ibm.com/docs/ide/features/chat-interface) ou à une capture de la version que vous utilisez.

- Le **bouton `+`** ouvre une nouvelle conversation

---

## Les premières actions sur un nouveau dossier de travail

```
1. Ouvrir le dossier de travail dans Bob
2. Passer en mode Agent
3. (Optionnel) Taper /init  →  Bob génère AGENTS.md et .bob/ automatiquement
4. Vérifier AGENTS.md  →  corriger si Bob a mal compris le contexte
```

> 📚 Doc : [Start a project with /init](https://bob.ibm.com/docs/ide/getting-started/tutorials/start-a-project)

---

## Ce que Bob ne fait pas

- ❌ **Il ne conserve pas l'historique de la conversation précédente** — chaque nouvelle conversation repart sans cet historique, mais avec le contexte persistant du projet (`AGENTS.md`, `.bob/rules/`) déjà présent dans les fichiers
- ❌ **Il n'a pas accès à internet par défaut** — `mcp-server-fetch` permet de récupérer une URL ; une recherche web nécessite un serveur MCP dédié (voir fiche `03_bob_mcp_web.md`)
- ❌ **Il ne garantit pas que le code fonctionne** — Bob peut exécuter des tests et des builds, mais c'est à vous de vérifier leur pertinence et le résultat obtenu
- ❌ **Il ne remplace pas votre réflexion** — il accélère l'exécution d'une décision déjà prise

---


---

## Lexique — les mots qui reviennent

**Agent**
Un programme qui peut prendre des décisions et agir de façon autonome : lire des fichiers, écrire du code, exécuter des commandes. Bob en mode Agent est un agent IA.

**AGENTS.md**
Un fichier texte placé à la racine du projet. Bob le lit au début de chaque conversation pour comprendre le contexte : stack technique, règles de travail, structure du dossier. C'est la mémoire persistante du projet.

**BobCoin**
L'unité de budget allouée à chaque participant pendant les challenges. Chaque interaction avec Bob consomme des BobCoins en fonction des ressources utilisées (modèle, outils appelés, volume de texte traité).

**Codebase**
L'ensemble des fichiers source d'un projet logiciel — le code, les fichiers de configuration, les ressources. Quand Bob « lit votre codebase », il parcourt ces fichiers.

**Clone** (Git)
Télécharger une copie complète d'un dépôt Git depuis GitHub sur votre machine. `git clone https://github.com/05091075/ESGI_Arrow_IBM_2026.git` copie tout le dépôt — code, historique, configuration — dans un dossier local. À faire une seule fois, au démarrage (utile seulement si vous récupérez les fiches ou un exercice depuis GitHub).

**Commit** (Git)
Une photo datée et nommée de l'état du projet à un instant précis. `git commit -m "description"` prend cette photo. Sans commit, une modification existe sur votre machine mais n'est pas enregistrée dans l'historique — et ne peut pas être partagée. Un commit ne quitte pas votre machine tant que vous n'avez pas fait `git push`.

**Commande terminal / shell**
Une instruction textuelle envoyée directement au système d'exploitation : `npm install` pour installer des dépendances, `git commit` pour enregistrer des modifications, `python script.py` pour lancer un programme. Bob peut exécuter ces commandes à votre place.

**Conflit Git**
Situation où deux personnes ont modifié la même zone du même fichier, et Git ne sait pas quelle version garder. Git marque les deux versions dans le fichier et demande de choisir manuellement. Rare en solo ; pour l'éviter en binôme, une seule personne modifie les fichiers à la fois (voir fiche `02_bob_projet_equipe.md`).

**Contexte de conversation**
La quantité d'information qu'un modèle IA peut « tenir en tête » pendant un échange. Plus la conversation est longue, plus le contexte se remplit. Ouvrir une nouvelle conversation (`+`) repart avec un contexte vide.

**Diff**
Représentation des modifications entre deux versions d'un fichier : les lignes supprimées et les lignes ajoutées. Bob utilise des diffs pour modifier un fichier de façon ciblée plutôt que de le réécrire entièrement.

**Git**
Un outil de gestion de versions : il enregistre l'historique des modifications d'un projet sous forme de **commits** (photos datées) et permet à plusieurs personnes de travailler sur les mêmes fichiers sans se marcher dessus. Pour un challenge court, Git est facultatif ; les commandes utiles à connaître sont `git clone`, `git pull`, `git add`, `git commit`, `git push` — expliquées dans ce glossaire.

**GitHub**
Un site web qui héberge des projets Git en ligne. Il permet de partager des fichiers, de voir les modifications de chacun et de les fusionner. Concrètement : le dépôt vit sur GitHub, vous le « clonez » (téléchargez) sur votre machine, travaillez dessus, puis « poussez » (envoyez) vos modifications. À ne pas confondre avec Git lui-même : Git est l'outil, GitHub est le service en ligne qui le rend accessible à tous.

**Merge** (Git)
Fusion de deux versions d'un même fichier (ou de deux branches). Git tente de fusionner automatiquement. Si deux personnes ont modifié la même zone, Git déclare un conflit (voir **Conflit Git**) et demande une intervention manuelle.

**Pull** (Git)
Récupérer depuis GitHub les modifications déposées par d'autres personnes. `git pull` met à jour votre copie locale. À faire avant de commencer à travailler, et avant d'envoyer vos propres modifications.

**Push** (Git)
Envoyer vos commits locaux sur GitHub pour que les autres puissent les voir et les récupérer. `git push` ne fonctionne que si vous avez d'abord fait `git commit`. Sans push, votre travail reste invisible pour les autres.

**Grep**
Outil de recherche dans le contenu de fichiers. Bob l'utilise pour retrouver une chaîne de texte ou un motif dans tout votre projet en quelques secondes.

**IDE**
*Integrated Development Environment* — environnement de développement intégré. C'est le logiciel dans lequel on écrit du code (éditeur, explorateur de fichiers, terminal…). Bob est conçu pour fonctionner à l'intérieur d'un IDE.

**MCP (Model Context Protocol)**
Un protocole standard qui permet à un modèle IA de se connecter à des outils externes : récupérer une page web, interroger une base de données, appeler une API. Un « serveur MCP » est le programme qui fait le lien entre Bob et l'outil en question.

**Skill**
Un ensemble d'instructions spécialisées qu'on active pour donner à Bob des connaissances supplémentaires sur un domaine précis (ex : Carbon Design System, Terraform…). Un skill doit être installé dans l'environnement avant de pouvoir être activé.

**Stack technique**
L'ensemble des technologies utilisées dans un projet : langage de programmation, framework, base de données, outils de déploiement… Exemple : « React + Node.js + PostgreSQL ».

**URL**
L'adresse d'une ressource sur internet, comme `https://bob.ibm.com/docs`. `mcp-server-fetch` permet à Bob de récupérer le contenu d'une URL donnée.

**`/init`**
Une commande spéciale tapée dans le chat Bob. Elle demande à Bob d'analyser le projet ouvert et de générer automatiquement `AGENTS.md` et le dossier `.bob/` avec une configuration de départ adaptée à la stack détectée.


*Voir aussi : `01_bob_bobcoin.md` — gérer son budget · `02_bob_projet_equipe.md` — organiser son dossier de travail*

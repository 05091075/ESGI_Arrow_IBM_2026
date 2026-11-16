# Ouvrir Bob et organiser son travail (seul ou en binôme)
> Fiche 02 · Mode opératoire

📚 **Documentation Bob** : [Quickstart — Set up your workspace](https://bob.ibm.com/docs/ide/getting-started/quickstart) · [Start a project with `/init`](https://bob.ibm.com/docs/ide/getting-started/tutorials/start-a-project) · [Règles projet](https://bob.ibm.com/docs/ide/configuration/rules) · [Configuration MCP](https://bob.ibm.com/docs/ide/configuration/mcp/mcp-in-bob)

---

## Vocabulaire de base (à lire une fois)

| Terme | Ce que c'est |
|---|---|
| **IBMid** | Compte personnel IBM. Un par personne. Ne se partage pas. Sert à s'identifier sur Bob. |
| **Bob** | L'application installée sur votre ordinateur. Chacun l'installe sur sa propre machine. |
| **Workspace Bob** | Le dossier ouvert dans Bob. Bob travaille dans le périmètre de ce dossier : c'est là qu'il lit les fichiers et applique les règles. Ouvrir le bon dossier est indispensable. |
| **`AGENTS.md`** | Fichier de contexte à la racine du dossier, chargé automatiquement par Bob. Coût faible si concis — voir fiche [`01_bob_bobcoin.md`](01_bob_bobcoin.md). |
| **`.bob/`** | Sous-dossier de configuration de Bob (règles, MCP). **Optionnel** pour un challenge court. |

> 💡 Les termes Git (commit, push, pull, clone…) sont définis dans le lexique de la [fiche `00_bob_intro.md`](00_bob_intro.md). Git est facultatif pour un challenge de 30 min à 1 h.

---

## Créer son accès Bob (à faire avant le premier challenge)

Avant de pouvoir utiliser Bob, il faut un **IBMid** — le compte qui permet de s'identifier sur les services IBM.

1. Aller sur **[bob.ibm.com](https://bob.ibm.com)** et cliquer sur **Get free trial**.
2. Sur la page de connexion, deux cas :
   - **Vous avez déjà un IBMid** (compte IBM Cloud, IBM Marketplace, etc.) → utilisez-le directement.
   - **Vous n'en avez pas** → l'email saisi lors de l'inscription deviendra votre IBMid. L'accès effectif dépend des abonnements et autorisations associés à votre compte.
3. Télécharger et installer l'application Bob (macOS ou Windows).
4. Se connecter avec l'IBMid créé ou existant.

> **Conseil** : faites-le la veille. L'activation peut prendre quelques minutes.

---

## 1. Préparer son dossier de travail

### Où ranger les fichiers ?

Créez un dossier `BobIA` dans votre dossier personnel, puis un sous-dossier par exercice :

```
Mac/Linux :   ~/Documents/BobIA/
Windows :     C:\Users\votre-prenom\Documents\BobIA\
```

```bash
# Mac/Linux — dans n'importe quel terminal :
mkdir -p ~/Documents/BobIA

# Windows PowerShell :
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\Documents\BobIA"
```

Organisation conseillée :

```
~/Documents/BobIA/
├── ESGI_Arrow_IBM_2026/    ← les fiches (ce dépôt)
└── mon-exercice/           ← le dossier de travail du challenge en cours
```

Un dossier par exercice évite de mélanger les fichiers d'un challenge à l'autre.

### Quel terminal utiliser ?

**Le terminal intégré à Bob** : il s'ouvre directement dans le dossier ouvert. Menu **Terminal → New Terminal**.

> Avec un terminal externe, placez-vous dans le bon dossier avec `cd` avant de lancer des commandes.

---

## 2. Ouvrir un dossier dans Bob

Bob travaille dans le dossier ouvert sur votre machine. Il n'existe pas de « projet Bob en ligne ».

Raccourci pour ouvrir le chat Bob : `Option + Cmd + B` sur Mac, `Ctrl + Alt + B` sur Windows. 📚 [Quickstart Bob](https://bob.ibm.com/docs/ide/getting-started/quickstart)

### Situation A — Consulter les fiches

1. Lancer Bob et se connecter avec son IBMid.
2. **File → Open Folder** → `~/Documents/BobIA/ESGI_Arrow_IBM_2026` → sélectionner ce dossier.
3. Ouvrir le chat Bob → tester une question en mode Ask.

### Situation B — Démarrer un challenge

1. Créer le dossier de l'exercice, par exemple `BobIA/mon-exercice` (ou utiliser celui indiqué par l'animateur).
2. **File → Open Folder** → sélectionner ce dossier.
3. Si Bob demande *"Do you trust the authors ?"* → **Yes, I trust the authors**.
4. Placer dans ce dossier l'énoncé et les fichiers fournis, dans leur format d'origine, avec un nom explicite.

> ⚠️ Ouvrir le bon dossier est critique. Si vous ouvrez `BobIA/` au lieu de `BobIA/mon-exercice/`, Bob ne chargera pas `AGENTS.md` et ne verra pas les bons fichiers.

---

## 3. Donner du contexte à Bob avec `/init` (optionnel)

Sur un dossier qui contient déjà quelques fichiers, `/init` génère un `AGENTS.md` qui décrit le contexte. Utile si le challenge dépasse 30 minutes.

1. Ouvrir Bob en mode **Agent**.
2. Taper `/init` dans le chat.
3. Relire `AGENTS.md` et corriger ce que Bob a mal compris.

> Sur un dossier vide, `/init` n'a rien à analyser : créez d'abord les premiers fichiers, ou rédigez `AGENTS.md` à la main.

Exemple de `AGENTS.md` minimal pour un challenge court :

```
# Mon exercice — Contexte Bob

## Objectif
- (une phrase : ce qu'on doit obtenir)

## Contraintes
- Durée : 1 heure
- Langue des réponses Bob : français
- Rester simple ; ne pas ajouter de fonctionnalité non demandée

## Fichiers importants
- enonce.md — l'énoncé du challenge
```

Gardez ce fichier **court** : il est relu à chaque conversation et consomme des BobCoins à chaque échange. Voir fiche [`01_bob_bobcoin.md`](01_bob_bobcoin.md).

---

## 4. Règles Bob dans `.bob/rules/` (optionnel)

Les rules sont des fichiers Markdown chargés automatiquement par Bob à chaque conversation, dans tous les modes. Pour un challenge court, `AGENTS.md` suffit presque toujours. Si vous souhaitez un réglage permanent, créez un petit fichier `.bob/rules/01_langue.md` :

```
# Langue et format des réponses

- Répondre toujours en français
- Réponses concises : aller droit au but
- Indiquer le nom du fichier concerné avant un bloc de code
```

Les règles du dossier (`.bob/rules/`) priment sur vos règles globales personnelles (`~/.bob/rules/`). Gardez-les **courtes et denses**.

---

## 5. Travailler en binôme

Bob ne partage pas les conversations : chaque conversation est **locale et privée**. Pour travailler à deux :

- **Un pilote, un relecteur** : le pilote tape dans Bob, le relecteur vérifie les résultats et les commandes exécutées. On échange les rôles à chaque challenge.
- **Un seul poste modifie les fichiers à la fois.** Si les deux utilisent un même dossier partagé (ou un même dépôt Git), prévenez avant de modifier un fichier.
- **Consigner les décisions utiles** dans un fichier `notes.md` du dossier de travail : décision validée, prompt qui a bien marché, cause d'un bug. Ainsi personne ne repose la même question.
- **Ne partagez jamais une clé API** (ni dans un fichier, ni dans un message).

Exemple d'entrée dans `notes.md` :

```
## Décision — format de sortie
- Choix : tableau Markdown
- Pourquoi : lisible sans outil supplémentaire
- Vérifié par : <prénom>
```

---

## 6. Partager un serveur MCP (optionnel)

Le fichier `.bob/mcp.json` du dossier de travail peut déclarer un serveur MCP (par exemple Tavily pour la recherche web). Les identifiants et clés API ne doivent **jamais** y figurer en clair : chacun les configure sur son propre poste. Procédure détaillée : fiche [`03_bob_mcp_web.md`](03_bob_mcp_web.md).

---

## 7. Checklist avant de démarrer un challenge

- [ ] Bob est installé et vous êtes connecté avec votre IBMid
- [ ] Le dossier de travail du challenge existe et est **ouvert dans Bob** (File → Open Folder)
- [ ] L'énoncé et les fichiers fournis sont dans ce dossier
- [ ] Un test simple en mode Ask fonctionne
- [ ] Votre solde BobCoin est noté (Settings → General)
- [ ] En binôme : pilote et relecteur sont désignés
- [ ] Aucune clé API n'est écrite dans un fichier

---

*Voir aussi : [`00_bob_intro.md`](00_bob_intro.md) — c'est quoi Bob · [`01_bob_bobcoin.md`](01_bob_bobcoin.md) — gérer son budget · [`03_bob_mcp_web.md`](03_bob_mcp_web.md) — recherche web*

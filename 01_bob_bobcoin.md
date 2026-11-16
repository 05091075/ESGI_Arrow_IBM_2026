# Les BobCoin — gérer son budget pendant un challenge
> Fiche 01 · Mode opératoire

📚 **Doc officielle** : [BobCoins — IBM Bob](https://bob.ibm.com/docs/ide/account/bobcoins)

---

## C'est quoi un BobCoin ?

> *"Bobcoins are the consumption-based billing metric used for Bob plans. They provide a transparent, predictable way to measure and bill for your Bob usage."*
> — [Documentation IBM Bob](https://bob.ibm.com/docs/ide/account/bobcoins)

Sous le capot, Bob utilise des **tokens** — les unités de traitement des modèles de langage. Chaque mot que vous écrivez, chaque fichier que Bob lit, chaque réponse qu'il génère consomme des tokens. Les BobCoin mesurent les ressources consommées, dont les tokens — avec des différences selon les modèles et les opérations.

```
Votre prompt         →  tokens en entrée  ┐
Contexte (fichiers,  →  tokens en entrée  ├─→  BobCoin consommés
  historique, rules) →  tokens en entrée  │
Réponse de Bob       →  tokens en sortie  ┘
```

> 📚 Doc : [Bobcoins — comprendre la consommation](https://bob.ibm.com/docs/ide/account/bobcoins#understanding-bobcoins)

---

## Ce qui consomme des BobCoin

### 🔴 Consommation élevée
- **Mode Agent sur un gros fichier** : Bob peut lire des fichiers entiers si le contexte l'exige
- **Conversations longues** : le contexte actif est renvoyé au modèle à chaque message, et grossit avec le temps
- **Prompts vagues qui nécessitent plusieurs allers-retours** : chaque échange coûte
- **Demander à Bob de lire toute la codebase** sans cibler un fichier précis

### 🟡 Consommation moyenne
- **Mode Plan** : réflexion et conception, la réponse peut être longue
- **Mode Agent sur un fichier ciblé** : Bob peut lire des plages de lignes et faire des recherches ciblées
- **Correction de bug avec contexte précis** : efficace si le bug est bien décrit

### 🟢 Consommation faible
- **Mode Ask avec question courte** : réponse directe — *attention, un prompt court accompagné d'un contexte déjà volumineux reste coûteux*
- **Demande de génération de texte simple** : le coût dépend du contexte chargé et de la longueur du résultat

### ⚪ Coûte peu, apporte beaucoup
- **`/init`** — génère l'`AGENTS.md` : un investissement de quelques coins qui structure toute la session
- **`.bob/rules/`** — instructions projet chargées automatiquement : à rédiger dense et court pour un coût minimal
- **`AGENTS.md`** — contexte projet permanent : bien rédigé une fois, réutilisé à chaque conversation
- **Ouvrir une nouvelle conversation** (`+`) — repart d'un contexte vide, sans l'historique accumulé

> 💡 Ces éléments ont un coût de contexte faible **si on les garde concis**. Un `AGENTS.md` de 500 lignes ou des `rules/` verbeux se retrouvent dans chaque requête et consomment à chaque échange.

> 📚 Doc contexte : [Context window management](https://bob.ibm.com/docs/ide/core-concepts/context-window-management)

---

## La règle d'or : Ask → Plan → Agent

Pour quelqu'un qui découvre l'outil, cet ordre est **le plus naturellement économique** — il évite de lancer des actions coûteuses avant d'avoir clarifié le besoin.

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   💬 ASK          🗺️ PLAN          🤖 AGENT                │
│   "Est-ce que  →  "Voilà le    →  "Fais exactement         │
│   cette archi     plan précis"    ce plan"                  │
│   tient ?"                                                  │
│                                                             │
│   Peu de coins    Coins moyens     Coins élevés             │
│   Aucun fichier   Modifications    Modifie les fichiers     │
│   modifié         limitées                                   │
└─────────────────────────────────────────────────────────────┘
```

### Pourquoi cet ordre ?

**Sans Plan, Agent part dans la mauvaise direction.** À titre d'exemple : corriger une mauvaise implémentation peut coûter 3× plus cher que de l'avoir planifiée correctement. Un aller-retour en Agent (implémenter → constater que c'est faux → réimplémenter) peut consommer 15–20 coins là où un Plan de ~3 coins aurait évité l'erreur.

> *Ces chiffres sont illustratifs — la consommation réelle dépend du contexte, du modèle et de la complexité de la tâche.*

En pratique, l'objectif est : **choisir le mode adapté, fournir le contexte pertinent et vérifier le résultat avant de poursuivre.**

> 📚 Doc : [Modes disponibles](https://bob.ibm.com/docs/ide/features/modes)

### Exemple concret

❌ **Approche sans plan** (risque de gaspillage) :
```
[Agent] "Crée-moi une API FastAPI avec authentification, 
         base de données PostgreSQL, gestion des rôles et 
         envoi d'emails"
→ Bob génère quelque chose, vous réalisez que l'archi ne convient pas
→ Vous redemandez, Bob régénère
→ Exemple : 3 allers-retours ≈ ~30 coins pour un résultat insatisfaisant
```

✅ **Approche planifiée** :
```
[Ask]   "Quels sont les trade-offs entre JWT et sessions 
         pour notre API ?" → ~2 coins
[Plan]  "Conçois l'architecture de l'API : endpoints, 
         modèles, auth — priorité simplicité" → ~4 coins
[Agent] "Implémente exactement ce plan dans /backend/api.py" → ~8 coins
         Exemple : total ~14 coins, résultat aligné dès le premier essai
```

> *Ces montants sont des exemples destinés à illustrer l'écart potentiel, pas des valeurs garanties.*

---

## Budget indicatif pour un challenge

*Votre enveloppe de BobCoins dépend de votre compte — **vérifiez-la dans Settings → General avant de commencer**.*

Un challenge de 30 min à 1 h demande peu de coins s'il est bien conduit. Ordre de grandeur par étape :

| Étape | Fiche | Mode principal | Part du budget | Ce qu'on fait avec Bob |
|---|---|---|---|---|
| **Comprendre et cadrer** | 05 | Ask | ~15 % | Reformuler l'énoncé, repérer les limites |
| **Plan et mise en place** | 06 | Ask → Plan | ~20 % | Plan en quelques étapes, premier test minimal |
| **Réalisation** | 07 | Agent | ~35 % | Produire le résultat par petites étapes |
| **Vérification** | 08 | Agent | ~15 % | Relancer, corriger, noter les limites |
| **Restitution** | 09 | Ask | ~5 % | Résumé court et retour sur l'usage de Bob |
| **Réserve** | — | — | ~10 % | Imprévus, bug bloquant |

> La réserve de 10 % est **fortement recommandée** : un imprévu arrive presque toujours.

> *Ces proportions sont indicatives. Notez votre solde au début et à la fin de chaque challenge pour calibrer le suivant.*

---

## Seul ou en binôme

- **Seul** : une conversation par étape, un fichier ciblé par demande.
- **En binôme** : une personne pilote Bob, l'autre relit et vérifie. Évitez que les deux posent la même question en parallèle — une seule personne interroge Bob, puis partage la réponse utile.

---

## Les 5 erreurs qui augmentent inutilement la consommation

### ❌ Erreur 1 — Conversation fleuve
Garder la même conversation pendant 6h. Le contexte actif grossit, chaque message coûte de plus en plus cher.
**Fix** : ouvrir une nouvelle conversation (`+`) dès qu'on change de sujet ou de tâche. Avant de fermer, noter dans un petit fichier les décisions prises, les fichiers importants et ce qui reste à faire.

> 📚 Doc : [Create a new context window](https://bob.ibm.com/docs/ide/getting-started/tutorials/context-window)

### ❌ Erreur 2 — Demander à Bob de lire tout le projet
`"Regarde tout mon code et dis-moi ce qui ne va pas"` — Bob charge tout, ça coûte énorme.
**Fix** : cibler le fichier ou la fonction précise. `"Dans /backend/api.py ligne 45, pourquoi cette erreur ?"`.

### ❌ Erreur 3 — Prompt vague → réponse ratée → recommencer
Un prompt imprécis génère une réponse inexacte, vous recorrigez, Bob régénère. Chaque aller-retour coûte.
**Fix** : 2 minutes à formuler un prompt précis peuvent économiser plusieurs allers-retours et une bonne dizaine de coins — *à titre d'exemple*.

### ❌ Erreur 4 — Utiliser Agent pour une question
`"[Agent] Explique-moi comment fonctionne OAuth"` — Agent charge tout le contexte projet pour répondre à une question qui n'en a pas besoin.
**Fix** : Ask pour les questions, Agent pour les actions.

### ❌ Erreur 5 — Perdre les réponses utiles
Bob répond brillamment à une question → la réponse reste enfouie dans une conversation.
**Fix** : copier les **décisions validées** dans un fichier `notes.md` de votre dossier de travail. Vous (et votre binôme) en profitez, personne ne repose la même question.

---

## Vérifier son solde

Votre solde BobCoin est visible dans **Settings → General**. D'autres indicateurs de consommation sont disponibles dans le panneau Bob et dans **Bobalytics**. Consultez-le au début et à la fin de chaque challenge pour ajuster votre stratégie.

> 📚 Doc : [Suivi de consommation](https://bob.ibm.com/docs/ide/account/bobcoins#monitoring-your-usage)

---

*Voir aussi : [`00_bob_intro.md`](00_bob_intro.md) — c'est quoi Bob · [`02_bob_projet_equipe.md`](02_bob_projet_equipe.md) — organiser son dossier de travail*

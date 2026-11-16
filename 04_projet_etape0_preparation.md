# Étape 0 — Préparation
> Fiche 04 · Mode opératoire

## 1. Objectif

Arriver au premier challenge avec un environnement fonctionnel. Cette étape se fait **avant** les exercices et prend 10 à 15 minutes. Elle n'est pas comptée dans la durée d'un challenge.

## 2. Livrables attendus

- Bob installé et connexion avec IBMid testée. 📚 [`02_bob_organisation.md`](02_bob_organisation.md)
- Compte GitHub créé, `git` installé (`git --version` dans un terminal) et authentification GitHub testée.
- Dossier des fiches ouvert dans Bob et mode Ask testé.
- Connexion au MCP web testée uniquement si le challenge l'exige, selon la fiche 03. 📚 [`03_bob_mcp_web.md`](03_bob_mcp_web.md)
- Budget BobCoin connu et choix entre Ask, Plan ou Agent compris. 📚 [`00_bob_intro.md`](00_bob_intro.md) · [`01_bob_bobcoin.md`](01_bob_bobcoin.md)

## 3. Actions, dans l'ordre

1. Ouvrir Bob et se connecter avec son IBMid.
2. Vérifier `git --version` dans un terminal. Si absent, installer [git-scm.com](https://git-scm.com).
3. Récupérer les fiches et ouvrir le dossier `ESGI_Arrow_IBM_2026` dans Bob (voir le `README.md`).
4. Tester le mode Ask avec une question courte sur le contenu d'une fiche.
5. Noter son solde de BobCoins de départ.
6. Créer un dossier de travail vide pour les exercices, par exemple `BobIA/mon-exercice`.
7. Si le MCP web est demandé, le tester selon la fiche [`03_bob_mcp_web.md`](03_bob_mcp_web.md).

## 4. Usage de Bob

Utiliser **Ask** pour comprendre un document ou une consigne, sans rien modifier.

> **Workspace Bob** = un dossier ouvert dans l'application Bob. Le dossier ouvert fournit le contexte de travail. Bob n'interroge pas le web si aucun MCP web n'est configuré.

### Prompt de test

```
[Ask] Résume en cinq lignes le rôle des trois modes de Bob (Ask, Plan, Agent)
d'après la fiche 00 de ce dossier.
Indique la fiche utilisée comme source.
```

### Prompt générique d'analyse d'un énoncé

À utiliser dès que l'animateur remet l'énoncé d'un challenge.

```
[Ask] Analyse uniquement l'énoncé [NOM DU CHALLENGE] à partir de [FICHIER OU TEXTE].

Réponds uniquement aux points suivants :
1. Quel résultat est demandé ?
2. Quelles informations ou données sont fournies ?
3. Quelles sont les contraintes explicites ?
4. Que manque-t-il pour commencer ?
5. Quelles questions faut-il poser à l'animateur ?

Distingue ce qui est écrit dans l'énoncé, ce qui est absent et ce qui est une hypothèse.
Ne propose pas encore de solution.
```

## 5. Points de vigilance

- Ne pas inventer une consigne, une donnée ou une contrainte absente de l'énoncé.
- Distinguer une information confirmée d'une hypothèse à valider.
- Ne pas consommer le budget sur des explorations inutiles : cibler les questions et ouvrir une nouvelle conversation lorsqu'on change de sujet. 📚 [`01_bob_bobcoin.md`](01_bob_bobcoin.md)
- Ne jamais copier une clé API dans un fichier texte, un chat ou un email — utiliser une variable d'environnement. 📚 [`03_bob_mcp_web.md`](03_bob_mcp_web.md)

## 6. Checklist de sortie

- [ ] IBMid créé (ou existant confirmé) et connexion à Bob testée.
- [ ] Compte GitHub créé et `git --version` retourne une version dans le terminal.
- [ ] Bob répond en mode Ask sur le dossier des fiches.
- [ ] Un dossier de travail vide est prêt pour les exercices.
- [ ] MCP web testé, ou explicitement écarté.
- [ ] Aucun secret n'est placé dans un fichier partagé.
- [ ] Le solde BobCoin de départ est noté.

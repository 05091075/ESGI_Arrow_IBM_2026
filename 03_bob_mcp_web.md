# Ajouter la recherche web à Bob — MCP Tavily
> Fiche 03 · Mode opératoire

📚 **Configuration MCP Bob** : [Using MCP in Bob](https://bob.ibm.com/docs/ide/configuration/mcp/mcp-in-bob)
📚 **Mentions URL Bob** : [Context mentions — URL mentions](https://bob.ibm.com/docs/ide/features/context-mentions#url-mentions)
📚 **Tavily MCP (officiel)** : [github.com/tavily-ai/tavily-mcp](https://github.com/tavily-ai/tavily-mcp)
📚 **Crédits Tavily** : [docs.tavily.com/documentation/api-credits](https://docs.tavily.com/documentation/api-credits)

---

## 1. Quand utiliser l'URL directe ou Tavily

Bob peut lire une page web dont vous connaissez l'adresse — sans Tavily, sans installation. Tavily sert à **trouver des pages** quand vous n'avez pas l'URL.

| Besoin | Ce qu'il faut utiliser |
|---|---|
| Lire une page dont vous connaissez l'URL | `@https://url-exacte.com` dans le chat Bob |
| Trouver des pages sur un sujet (pas d'URL connue) | Recherche Tavily via Bob |
| Interroger une API métier | Appel direct avec ses paramètres et autorisations |

> 📚 La syntaxe `@url` est documentée : [Context mentions — URL mentions](https://bob.ibm.com/docs/ide/features/context-mentions#url-mentions)

---

## 2. Connecter le serveur Tavily distant

Tavily fournit un **serveur MCP distant** (Streamable HTTP) : aucune installation locale n'est nécessaire.

> ⚠️ **À tester dans Bob avant le premier challenge** : la compatibilité du transport Streamable HTTP avec votre version de Bob doit être vérifiée une fois en conditions réelles.

Créer ou éditer `.bob/mcp.json` à la racine de votre dossier de travail :

```json
{
  "mcpServers": {
    "tavily": {
      "type": "http",
      "url": "https://mcp.tavily.com/mcp/",
      "headers": {
        "Authorization": "Bearer ${TAVILY_API_KEY}"
      }
    }
  }
}
```

> 📚 Source transport : [github.com/tavily-ai/tavily-mcp](https://github.com/tavily-ai/tavily-mcp)

---

## 3. Configurer son authentification

### Créer un compte Tavily

1. Aller sur [app.tavily.com](https://app.tavily.com)
2. S'inscrire (email ou GitHub)
3. Copier la clé API : format `tvly-xxxxxxxxxxxxxxxx`

### Définir la variable d'environnement localement

La valeur `${TAVILY_API_KEY}` dans `mcp.json` est une substitution — Bob lit la variable d'environnement au démarrage. **Ne jamais inscrire la clé en dur dans le fichier.**

**macOS / Linux** — ajouter dans `~/.zshrc` ou `~/.bashrc` :
```bash
export TAVILY_API_KEY="<votre clé Tavily>"
```
Puis relancer le terminal. **Note** : si Bob est lancé depuis le Finder (pas depuis un terminal), la variable peut ne pas être disponible. Dans ce cas, ouvrir Bob depuis un terminal avec `bob .` après avoir sourcé `.zshrc`.

**Windows** (PowerShell) :
```powershell
[System.Environment]::SetEnvironmentVariable("TAVILY_API_KEY","<votre clé Tavily>","User")
```
Puis redémarrer Bob.

### Si vous utilisez Git — sans la clé

Si le dossier est versionné avec Git, ne commitez `.bob/mcp.json` qu'avec `${TAVILY_API_KEY}`, jamais avec la clé réelle. Ajoutez-le au `.gitignore` si vous préférez ne pas le partager :

```
.bob/mcp.json
```

> 📚 Voir aussi : [Understanding MCP — identifiants](https://bob.ibm.com/docs/ide/configuration/mcp/understanding-mcp)

### En binôme

Chacun crée son propre compte Tavily (plan gratuit : 1 000 crédits/mois). Si vous préférez une clé unique, une seule personne la gère et la communique en message privé — jamais dans un dépôt, un fichier partagé ou un chat de groupe.

---

## 4. Effectuer un test observable

Un test fiable doit vérifier deux choses séparément :

**Étape 1 — Le serveur est connecté**
Aller dans **Settings → MCP** : le serveur `tavily` doit afficher un statut vert et lister ses outils (ex. `tavily_search`).

**Étape 2 — L'outil est réellement appelé**
Dans le chat Bob :

```
Utilise l'outil Tavily pour chercher : quelle est la documentation 
officielle de Markdown (syntaxe de base) ?
Indique le titre exact des pages trouvées, leur URL officielle, 
les conditions d'accès (libre / inscription / payant) 
et ce que la recherche n'a pas permis de confirmer.
```

Un test réussi montre :
- un appel à l'outil `tavily_search` visible dans la conversation ;
- des résultats avec titres et URLs ;
- une mention explicite de ce qui reste incertain.

> Une réponse avec un lien ne prouve pas que Tavily a été utilisé — c'est l'appel d'outil visible qui le confirme.

---

## 5. Comprendre les deux compteurs et limiter les recherches

### Les deux compteurs

| Compteur | Ce qu'il mesure | Où le voir |
|---|---|---|
| **BobCoin** | Traitement Bob (tokens en entrée et sortie) | Fiche 01 |
| **Crédits Tavily** | Appels aux services Tavily | [app.tavily.com](https://app.tavily.com) |

Ces deux compteurs sont **indépendants**. Lire le résultat d'une recherche Tavily consomme aussi des tokens Bob (le texte retourné entre dans la fenêtre de contexte).

### Tarification Tavily (plan gratuit)

- **1 000 crédits/mois** offerts
- Recherche `basic` : **1 crédit**
- Recherche `advanced` : **2 crédits**

> 📚 Source : [docs.tavily.com/documentation/api-credits](https://docs.tavily.com/documentation/api-credits)

### Prompts économiques

Demander une URL ou un titre plutôt qu'une synthèse réduit le nombre de recherches.

❌ Coûteux :
```
Recherche web sur tout ce qui existe sur les langages de programmation
```

✅ Économique :
```
Recherche Tavily : URL de la documentation officielle de Python 
sur le module « csv » — titre exact et lien direct
```

---

## Checklist avant le premier challenge

- [ ] Compte Tavily créé sur [app.tavily.com](https://app.tavily.com)
- [ ] Clé API `tvly-…` copiée
- [ ] Variable d'environnement `TAVILY_API_KEY` définie (et Bob ouvert depuis un terminal)
- [ ] `.bob/mcp.json` créé avec la config du serveur distant
- [ ] Bob redémarré — serveur `tavily` vert dans Settings → MCP, outils visibles
- [ ] Test d'appel d'outil réussi (appel `tavily_search` visible dans la conversation)
- [ ] `.bob/mcp.json` commité **sans la clé** (valeur `${TAVILY_API_KEY}`, si le dossier est versionné)

---

*Voir aussi : `01_bob_bobcoin.md` — gérer son budget · `02_bob_organisation.md` — organiser son dossier de travail*

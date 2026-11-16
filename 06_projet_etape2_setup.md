# Étape 2 — Plan & mise en place
> Fiche 06 · Mode opératoire

## 1. Objectif

Transformer l'objectif en un **plan court** et vérifier qu'une première version minimale fonctionne avant de continuer. Cette étape dure **5 minutes pour un challenge de 30 minutes** et **10 minutes pour un challenge d'une heure**.

« Avoir un plan » ne suffit pas. L'objectif est de prouver que l'approche choisie fonctionne sur un tout petit cas.

## 2. Livrables attendus

- Plan en trois à cinq étapes, chacune avec un résultat vérifiable.
- Dossier de travail prêt et ouvert dans Bob.
- Un premier test minimal qui fonctionne (même très simple).
- Le principal risque identifié et testé, ou une solution de secours prévue.

## 3. Actions, dans l'ordre

1. Ouvrir dans Bob le dossier de travail prévu pour l'exercice (fiche 04).
2. Faire proposer un plan en trois à cinq étapes par Bob (mode Plan).
3. Relire le plan : supprimer tout ce qui n'est pas nécessaire à l'objectif.
4. Faire un premier test minimal : le plus petit cas qui prouve que l'approche fonctionne.
5. Si ce test échoue, ajuster l'approche maintenant, pas à la fin.
6. En cas de travail en binôme, vérifier que chacun comprend le plan et sait qui fait quoi.

## 4. Usage de Bob

Utiliser **Plan** pour structurer, puis **Agent** pour créer les fichiers de départ. 📚 [`00_bob_intro.md`](00_bob_intro.md)

### Prompt générique de plan

```
[Plan] À partir de l'objectif et de l'approche retenus à l'étape précédente,
propose un plan en 3 à 5 étapes pour un challenge de [DURÉE].

Pour chaque étape : ce qui est produit, comment je le vérifie, durée estimée.
Indique le principal risque et comment le tester en premier.
N'ajoute aucune étape hors objectif.
Ne génère aucun code.

[OBJECTIF ET CRITÈRE DE RÉUSSITE — sortie de l'étape 1]
[APPROCHE RETENUE]
```

### Prompt générique de première version

```
[Agent] Crée uniquement la plus petite version qui prouve que l'approche fonctionne.
Critère de succès : [CRITÈRE DE LA PREMIÈRE ÉTAPE DU PLAN].
Utilise les outils et langages déjà disponibles sur ma machine.
N'ajoute aucune fonctionnalité en plus.
Indique les commandes à exécuter pour vérifier, puis exécute-les
et rapporte le résultat réel.

[PLAN VALIDÉ — sortie du prompt précédent]
```

### Gabarit de validation

**Pour le plan :**
- [ ] Trois à cinq étapes, chacune avec un résultat vérifiable
- [ ] Le risque principal est identifié avec un moyen de le tester
- [ ] Rien n'est prévu en dehors de l'objectif

**Pour la première version :**
- [ ] Elle s'exécute sans erreur
- [ ] Le résultat obtenu correspond à ce qui était attendu
- [ ] Les commandes de vérification ont réellement été exécutées

**Ce qui bloque le passage à l'étape 3 :**
- Premier test qui échoue sans cause comprise
- Dépendance indisponible (accès, outil, donnée) sans solution de secours

## 5. Points de vigilance

- Ne pas choisir un outil ou un langage que vous ne connaissez pas, sauf si l'énoncé l'exige.
- Ne pas placer de clé API dans un fichier. 📚 [`03_bob_mcp_web.md`](03_bob_mcp_web.md)
- Ne pas confondre une démonstration simple et une solution complète : viser le plus simple qui répond à l'objectif.
- Prévoir un chemin de secours avec des données d'exemple explicitement marquées lorsque l'accès à une source est indisponible.
- Un démarrage rapide peut cacher une difficulté plus loin : choisir l'option la plus simple à **terminer**, pas seulement à commencer.

## 6. Checklist de sortie

- [ ] Plan en trois à cinq étapes validé.
- [ ] Dossier de travail prêt et ouvert dans Bob.
- [ ] Premier test minimal exécuté avec succès.
- [ ] Risque principal testé ou solution de secours prévue.
- [ ] Chacun sait quelle étape il réalise (en binôme).

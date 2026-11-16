# Étape 1 — Comprendre & cadrer
> Fiche 05 · Mode opératoire

## 1. Objectif

Comprendre l'énoncé du challenge et formuler un objectif réaliste pour le temps disponible. Cette étape dure **5 minutes pour un challenge de 30 minutes** et **10 minutes pour un challenge d'une heure**.

## 2. Livrables attendus

- Énoncé reformulé en une phrase.
- Résultat attendu décrit simplement.
- Critère de réussite vérifiable.
- Ce qui est explicitement hors périmètre.
- Contraintes et hypothèses séparées.

## 3. Actions, dans l'ordre

1. Lire l'énoncé en entier une première fois, sans rien produire.
2. Poser à l'animateur les questions qui bloquent et noter les réponses exactes.
3. Reformuler le besoin : ce qui est donné, ce qui est demandé, pour qui.
4. Écrire le critère de réussite : comment saurez-vous que c'est terminé ?
5. Écrire ce qui est hors périmètre pour rester dans le temps imparti.
6. En binôme, faire valider l'objectif par l'autre personne avant de commencer.

### Format de phrase d'objectif

> À partir de **[ce qui est fourni]**, je veux obtenir **[résultat attendu]**, vérifié par **[critère de réussite]**.

## 4. Usage de Bob

Utiliser **Ask** pour clarifier l'énoncé, puis **Plan** si plusieurs approches sont possibles. Ici, on demande explicitement à Bob de ne pas produire de code. 📚 [`00_bob_intro.md`](00_bob_intro.md) · [Modes Bob](https://bob.ibm.com/docs/ide/features/modes)

### Prompt générique de cadrage

```
[Plan] Voici l'énoncé du challenge et les précisions de l'animateur.

Contrainte : le résultat doit être terminé et vérifié en [DURÉE : 30 min ou 1 h],
vérification comprise. Je travaille [seul / en binôme].

Propose deux ou trois approches simples.
Pour chacune : résultat obtenu, étapes principales, risque principal,
et ce qui est explicitement hors périmètre.
Indique laquelle tient le mieux dans le temps et pourquoi.
Le choix final m'appartient.
Ne génère aucun code.

[ÉNONCÉ]
[PRÉCISIONS DE L'ANIMATEUR]
```

### Gabarit de validation — ce que la sortie doit contenir

> Quatre éléments suffisent pour passer à l'étape suivante.

- [ ] Un objectif en une phrase (voir le format ci-dessus)
- [ ] Un critère de réussite que l'on peut vérifier soi-même
- [ ] Un hors périmètre explicite
- [ ] L'approche retenue, avec son principal risque

**Ce qui bloque le passage à l'étape 2 :**
- Objectif trop large pour le temps disponible
- Critère de réussite impossible à vérifier
- Plusieurs approches retenues sans choix tranché

> **Note** : la sortie réelle de Bob dépend de votre conversation. Le choix final vous appartient, à partir des propositions de Bob et de vos vérifications.

## 5. Points de vigilance

- Ne pas commencer la réalisation tant que vous ne savez pas répondre à « que dois-je obtenir, et comment le vérifier ? ».
- Un objectif ambitieux n'est pas un bon objectif s'il ne peut pas être vérifié dans le temps imparti.
- En cas de doute sur l'énoncé, poser la question plutôt que de supposer.
- Toute information utilisée doit pouvoir être rattachée à l'énoncé ou à une réponse de l'animateur.

## 6. Checklist de sortie

- [ ] Énoncé compris et reformulé en une phrase.
- [ ] Objectif validé (par soi-même ou par le binôme).
- [ ] Critère de réussite écrit.
- [ ] Hors périmètre explicite.
- [ ] Risques et hypothèses notés.
- [ ] Budget BobCoin de l'étape respecté. 📚 [`01_bob_bobcoin.md`](01_bob_bobcoin.md)

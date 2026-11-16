# Étape 3 — Réalisation
> Fiche 07 · Mode opératoire

## 1. Objectif

Obtenir le résultat attendu **par petites étapes vérifiées**. Cette étape est la plus longue : **10 minutes pour un challenge de 30 minutes** et **20 minutes pour un challenge d'une heure**.

La première version minimale existe déjà (fiche 06). Il s'agit maintenant de dérouler le plan, une étape après l'autre, en vérifiant chaque résultat avant de passer à la suivante.

## 2. Livrables attendus

- Le résultat attendu par l'énoncé est obtenu, au moins dans sa version essentielle.
- Chaque étape du plan a été vérifiée avant la suivante.
- Un cas normal et un cas limite ont été essayés.
- Les parties simulées ou fictives sont clairement identifiées.
- Les limites et les points restants sont notés.

## 3. Actions, dans l'ordre

1. Reprendre le plan validé et la première version minimale.
2. Réaliser **une seule étape à la fois** avec Bob, puis la vérifier avant de continuer.
3. En cas d'erreur, donner à Bob le message exact et le fichier concerné.
4. Corriger en priorité ce qui empêche d'obtenir le résultat principal ; le reste attend.
5. Faire un point rapide à mi-parcours (voir section 5) et réduire le périmètre si le temps manque.
6. En binôme, une personne pilote Bob et l'autre relit chaque résultat.

## 4. Usage de Bob

Utiliser **Agent** pour des changements ciblés, une étape à la fois. Donner à Bob la tâche, les fichiers concernés et le résultat attendu ; ne pas lui demander de tout refaire. 📚 [`00_bob_intro.md`](00_bob_intro.md) · [`01_bob_bobcoin.md`](01_bob_bobcoin.md)

### Prompt principal — réaliser une étape du plan

```
[Agent] Réalise uniquement l'étape [NUMÉRO ET NOM] du plan.

Tâche : [décrire ce qui doit être produit]
Fichiers concernés : [LISTE]
Comportement attendu : [décrire le résultat précis]

Exemple d'entrée : [EXEMPLE]
Exemple de sortie attendue : [EXEMPLE]

Critère de réussite : [ce qui doit être vrai pour que l'étape soit terminée]

Contraintes :
- Limiter les modifications à celles nécessaires à cette étape
- Préserver ce qui fonctionne déjà
- Exécuter les vérifications après modification et rapporter les résultats réels ;
  signaler celles qui n'ont pas pu être exécutées
```

### Prompt complémentaire — données d'exemple

À utiliser si l'énoncé ne fournit pas de données de test suffisantes.

> **Distinction importante** : des données d'exemple réellement traitées démontrent que le traitement fonctionne. Un résultat écrit à la main et affiché tel quel ne démontre rien sur le traitement. Choisir le niveau de simulation en fonction de ce que l'on veut prouver.

```
[Agent] J'ai besoin de quelques données d'exemple pour tester [FONCTION].
Données existantes : [DÉCRIRE CE QUI EXISTE]

Crée uniquement les cas manquants :
1. [CAS NORMAL]
2. [CAS LIMITE]

Marque clairement ces données comme fictives (nom de fichier ou champ dédié).
Ne modifie pas les données existantes.
```

### Prompt complémentaire — corriger une erreur

```
[Agent] Dans [FICHIER], la commande [COMMANDE] produit cette erreur :
[ERREUR EXACTE]

Résultat attendu : [RÉSULTAT].

Commence par analyser la cause dans ce fichier. Si elle vient d'ailleurs,
étends l'analyse et justifie toute modification hors du fichier signalé.
Propose le changement minimal, applique-le, puis relance la commande
pour vérifier. Le critère de qualité est la correction ciblée,
pas le nombre de fichiers touchés.
```

### Gabarit de validation — sortie de l'étape

> La sortie est utilisable pour passer à la vérification si elle satisfait les critères suivants.

- [ ] Le résultat principal est obtenu sur un cas représentatif
- [ ] Le résultat correspond au critère de réussite défini à l'étape 1
- [ ] Un cas normal et un cas limite ont été essayés
- [ ] Les parties fictives ou simulées sont identifiées

**Ce qui bloque le passage à l'étape 4 :**
- Le résultat principal n'est pas obtenu et aucune réduction de périmètre n'a été décidée
- Les parties simulées ne sont pas identifiées — risque de les présenter comme réelles
- Aucune vérification n'a été exécutée

## 5. Point de contrôle à mi-parcours

À la moitié du temps de cette étape, répondre à trois questions :

- Qu'est-ce qui fonctionne déjà ?
- Qu'est-ce qui bloque ?
- Que faut-il simplifier ou abandonner pour terminer à temps ?

## 6. Points de vigilance

- Le résultat principal passe avant tout ajout secondaire.
- Un petit résultat qui fonctionne vaut mieux qu'un grand résultat à moitié terminé.
- Distinguer données fictives et traitement simulé : ce sont deux niveaux différents.
- Tout élément simulé doit rester identifiable dans les fichiers et dans la restitution.
- Ne pas dépenser des BobCoins pour une réponse générale quand une question ciblée suffit. 📚 [`01_bob_bobcoin.md`](01_bob_bobcoin.md)

## 7. Checklist de sortie

- [ ] Le résultat principal est obtenu.
- [ ] Chaque étape du plan a été vérifiée.
- [ ] Un cas normal et un cas limite ont été essayés.
- [ ] Les éléments fictifs ou simulés sont identifiés.
- [ ] Une version qui fonctionne est conservée (copie du dossier ou commit).
- [ ] Les limites et points restants sont notés.

> Si le résultat principal est encore bloqué à la fin de l'étape, réduire le périmètre ou activer la solution de secours prévue — noter le blocage ne suffit pas.

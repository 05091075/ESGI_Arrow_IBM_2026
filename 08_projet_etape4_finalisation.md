# Étape 4 — Vérification & finalisation
> Fiche 08 · Mode opératoire

## 1. Objectif

Vérifier que le résultat fonctionne de bout en bout et qu'il peut être relancé par quelqu'un d'autre. Cette étape dure **5 minutes pour un challenge de 30 minutes** et **10 minutes pour un challenge d'une heure**. À partir de ce moment, on n'ajoute plus de fonctionnalité.

## 2. Livrables attendus

- Le résultat relancé une dernière fois depuis le début, sans erreur.
- Un court mode d'emploi (quelques lignes) pour le relancer.
- Les limites connues écrites sans les minimiser.
- Une version finale identifiée et conservée.

## 3. Actions, dans l'ordre

> **Point de départ :** si le résultat principal ne fonctionne pas encore, appliquer d'abord l'arbitrage de l'étape 3 — réduire le périmètre ou activer la solution de secours. Cette étape n'est pas une nouvelle phase de réalisation.

1. Arrêter l'ajout de fonctionnalités.
2. Relancer le résultat depuis le début, dans les conditions où il sera présenté.
3. Corriger uniquement les défauts qui empêchent d'obtenir ou de comprendre le résultat.
4. Rédiger un court mode d'emploi : comment lancer, ce que l'on doit voir, ce qui est simulé.
5. Noter les limites : ce qui ne marche pas, ce qui n'a pas été testé.
6. Conserver la version finale (copie du dossier ou commit).

## 4. Usage de Bob

Utiliser **Agent** sur des fichiers ciblés pour corriger et rédiger le mode d'emploi. 📚 [`00_bob_intro.md`](00_bob_intro.md)

### Prompt générique de vérification

```
[Agent] Il reste [TEMPS RESTANT] avant la fin de l'exercice.

Analyse uniquement le résultat suivant. Ne crée aucune nouvelle fonctionnalité.
Corrige seulement ce qui empêche le résultat de fonctionner ou d'être compris.
Si une correction est trop risquée dans le temps restant, signale-le
et propose une alternative plus simple.

Résultat à vérifier : [DÉCRIRE LE RÉSULTAT ET COMMENT IL SE LANCE]
Commence par les fichiers suivants : [FICHIERS]

En sortie, indique :
- les commandes exécutées ;
- les résultats constatés ;
- les vérifications non réalisées ;
- les défauts connus qui restent.
```

### Prompt générique de mode d'emploi

```
[Agent] Rédige ou mets à jour un fichier README.md court pour qu'une autre personne puisse :
1. comprendre ce que fait le résultat ;
2. le lancer ;
3. distinguer ce qui est réel de ce qui est simulé ;
4. connaître les limites.
N'invente aucune commande : vérifie ce qui existe réellement dans le dossier.
```

### Gabarit de validation

**Résultat :**
- [ ] Il se lance sans manipulation imprévue
- [ ] Il fonctionne sur au moins deux essais consécutifs
- [ ] Aucune erreur bloquante
- [ ] Les éléments simulés sont visibles et identifiés

**Mode d'emploi :**
- [ ] Les commandes ont été vérifiées dans le dossier
- [ ] Une autre personne pourrait relancer le résultat sans étape implicite
- [ ] Les limites sont écrites sans les minimiser

**Ce qui bloque le passage à la restitution :**
- Résultat non reproductible
- Mode d'emploi contenant des commandes inventées ou non vérifiées
- Éléments simulés non identifiés

> **Note** : la sortie réelle de Bob dépend de votre dossier. Vérifiez vous-même le résultat après chaque correction avant de le déclarer terminé.

## 5. Points de vigilance

- Tester dans les conditions réelles de la restitution, pas seulement dans l'éditeur.
- Ne jamais remplacer une source indisponible par une donnée non signalée.
- À partir de cette étape, trois règles s'appliquent :
  - **Pas de nouvelle fonctionnalité.**
  - **Une version finale identifiée** : une copie ou un commit précis, testé et conservé.
  - **Correction exceptionnelle** : uniquement pour un défaut bloquant, avec nouvelle vérification.

## 6. Checklist de sortie

- [ ] Le résultat a été relancé depuis le début, sans erreur.
- [ ] Les éléments simulés sont clairement annoncés.
- [ ] Un mode d'emploi court existe et a été vérifié.
- [ ] Les limites sont écrites.
- [ ] La version finale est identifiée et conservée.

La préparation de la restitution peut avancer **en parallèle** de ces vérifications.

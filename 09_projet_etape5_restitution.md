# Étape 5 — Restitution
> Fiche 09 · Mode opératoire

## 1. Objectif

Présenter le résultat de façon claire, honnête et courte, puis faire le point sur l'usage de Bob. Cette étape dure **5 minutes pour un challenge de 30 minutes** et **10 minutes pour un challenge d'une heure**. La restitution elle-même tient en **deux à trois minutes**, sauf consigne contraire de l'animateur.

## 2. Livrables attendus

- Un résumé oral ou écrit en quatre parties : objectif, démarche, résultat, limites.
- Le résultat montré en fonctionnement, ou une trace de son fonctionnement si le matériel ne le permet pas.
- Un retour sur l'usage de Bob : ce qui a aidé, ce qui a été corrigé, ce qui a coûté.
- Les réponses prêtes aux questions probables.

## 3. Structure de la restitution

1. **Objectif** : ce que demandait le challenge, en une phrase.
2. **Démarche** : les grandes étapes suivies avec Bob (Ask, Plan, Agent).
3. **Résultat** : montrer ce qui fonctionne, et uniquement ce qui a été vérifié.
4. **Limites** : ce qui ne marche pas, ce qui est simulé, ce qui n'a pas été testé.
5. **Retour d'expérience** : un prompt efficace, une erreur rencontrée, le solde de BobCoins consommé.

> Les parties résultat et limites sont les plus importantes. Quelques phrases suffisent ; il n'est pas nécessaire d'inventer un gain chiffré.

### Actions, dans l'ordre

1. Reprendre l'objectif écrit à l'étape 1 — ne pas en inventer un nouveau.
2. Choisir ce qui sera montré : le chemin le plus simple qui prouve le résultat.
3. Répartir la parole si vous êtes plusieurs.
4. Mesurer la durée totale (parole et manipulations) et supprimer ce qui n'aide pas à comprendre.
5. Préparer une solution de repli (capture d'écran ou résultat enregistré) si la démonstration en direct échoue.
6. Préparer deux ou trois réponses aux questions probables.

## 4. Usage de Bob

Utiliser **Ask** pour challenger le message, puis **Agent** si un fichier de synthèse doit être rédigé. 📚 [`00_bob_intro.md`](00_bob_intro.md)

### Prompt générique de résumé

```
[Ask] À partir de l'objectif, du résultat obtenu et des vérifications réalisées,
propose un résumé oral en quatre parties : objectif, démarche, résultat, limites.

Contrainte : durée maximale [DURÉE COMMUNIQUÉE PAR L'ANIMATEUR, par défaut 2 à 3 minutes].
Reste factuel : sépare ce qui est démontré, ce qui est une hypothèse et ce qui reste à faire.
N'invente aucun chiffre. Ne présente comme réalisée aucune fonctionnalité non vérifiée.

[OBJECTIF — sortie de l'étape 1]
[RÉSULTAT ET VÉRIFICATIONS — sortie de l'étape 4]
[LIMITES CONNUES]
```

### Prompt générique de questions

```
[Ask] À partir du contexte ci-dessous, liste cinq questions que l'on pourrait me poser
sur le résultat, la démarche, les limites et l'usage de Bob.
Pour chaque question, propose une réponse courte fondée uniquement sur ce qui a
réellement été fait, et indique ce qui reste à valider.
Une réponse peut exposer une hypothèse, à condition de ne pas la présenter comme acquise.

[CONTEXTE — objectif, résultat, vérifications, limites]
```

### Gabarit de validation

**Structure :**
- [ ] Objectif en une phrase
- [ ] Démarche résumée en quelques étapes
- [ ] Résultat montré tel qu'il fonctionne réellement
- [ ] Limites annoncées explicitement
- [ ] Retour d'expérience sur Bob

**Factualité :**
- [ ] Aucun résultat présenté comme obtenu s'il n'a pas été vérifié
- [ ] Les éléments simulés sont annoncés comme tels
- [ ] Les pistes d'amélioration sont présentées comme des travaux futurs

**Durée :**
- [ ] Présentation chronométrée, manipulations comprises
- [ ] Respecte la durée annoncée avec une marge

**Plan de repli :**
- [ ] Une capture ou un résultat enregistré est prêt
- [ ] On sait à quel moment basculer vers ce repli

**Ce qui bloque une restitution convaincante :**
- Présenter comme réalisé ce qui n'a pas été vérifié
- Durée non testée
- Aucune solution de repli

> **Note** : la sortie réelle de Bob dépend de votre exercice. Vérifiez que le résumé correspond à ce que vous pouvez réellement montrer.

## 5. Points de vigilance

- Ne pas transformer une projection en résultat obtenu.
- Ne pas noyer la restitution dans les détails techniques : le public doit comprendre le résultat.
- Annoncer les limites ; elles renforcent la crédibilité.
- Éviter toute séance de dépannage en direct ; basculer vers le repli prévu.
- Vérifier la durée exacte demandée auprès de l'animateur.

## 6. Checklist de sortie

- [ ] L'objectif, le résultat et les limites sont compris en moins d'une minute.
- [ ] La restitution suit l'objectif écrit à l'étape 1.
- [ ] Les éléments simulés et les limites sont annoncés.
- [ ] Les pistes d'amélioration sont présentées comme futures.
- [ ] La durée est respectée avec une marge.
- [ ] Une solution de repli est prête.
- [ ] Le solde de BobCoins consommé est noté. 📚 [`01_bob_bobcoin.md`](01_bob_bobcoin.md)

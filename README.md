# ESGI_Arrow_IBM_2026 — Guide pratique avec IBM Bob

> ESGI_Arrow_IBM_2026 · Exercices pratiques de 30 minutes à 1 heure
> Dix fiches pour prendre en main IBM Bob, réaliser un challenge court et en présenter le résultat.

## 1. À quoi sert ce dépôt ?

Ce dépôt rassemble des fiches pratiques pour accompagner les participants à ESGI_Arrow_IBM_2026 avec [IBM Bob](https://bob.ibm.com).

Vous y trouverez des explications, des prompts à adapter, une méthode de travail en quatre ou cinq étapes courtes et des critères pour vérifier votre progression.

Chaque exercice est un **challenge pratique de 30 minutes à 1 heure**. Le but est d'obtenir **un petit résultat concret, vérifié et expliqué**, en utilisant Bob de façon efficace.

Les exercices peuvent se faire seul ou en binôme. Ajustez la méthode à la consigne donnée pour chaque challenge.

## 2. Par où commencer ?

1. **Découvrez Bob** avec la [fiche 00](00_bob_intro.md).
2. **Préparez votre poste** avec la [fiche 04](04_projet_etape0_preprojet.md).
3. Consultez la [fiche 01](01_bob_bobcoin.md) pour suivre votre consommation et la [fiche 02](02_bob_projet_equipe.md) pour organiser votre dossier de travail, seul ou en binôme.
4. Si vous avez besoin de recherche web, consultez la [fiche 03](03_bob_mcp_web.md).
5. Pendant chaque challenge, suivez les étapes des **fiches 05 à 09**.

Les fiches sont consultables directement sur GitHub. Pour les ouvrir dans Bob, téléchargez le dépôt ou clonez-le sur votre machine.

### Récupérer les fiches localement

**macOS / Linux :**

```bash
mkdir -p ~/Documents/BobIA
cd ~/Documents/BobIA
git clone https://github.com/05091075/ESGI_Arrow_IBM_2026.git
cd ESGI_Arrow_IBM_2026
```

**Windows PowerShell :**

```powershell
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\Documents\BobIA"
Set-Location "$env:USERPROFILE\Documents\BobIA"
git clone https://github.com/05091075/ESGI_Arrow_IBM_2026.git
Set-Location ESGI_Arrow_IBM_2026
```

Dans Bob, sélectionnez **File → Open Folder**, puis ouvrez le dossier `ESGI_Arrow_IBM_2026`.

**Ce dépôt contient les supports de travail.** Ce que vous produisez pendant un challenge se range dans un dossier distinct, par exemple `BobIA/mon-exercice`, selon la consigne de l'animateur.

Si vous avez déjà cloné les fiches, réutilisez votre copie existante.

## 3. Les dix fiches

### Comprendre et configurer Bob

| Fiche                                                | Ce qu'elle vous aide à faire                                                     |
| ---------------------------------------------------- | -------------------------------------------------------------------------------- |
| [00 — C'est quoi Bob ?](00_bob_intro.md)             | Comprendre les modes, les outils et le vocabulaire.                              |
| [01 — Gérer ses Bobcoins](01_bob_bobcoin.md)         | Suivre la consommation, maîtriser le contexte et préserver une réserve.          |
| [02 — Organiser son travail](02_bob_projet_equipe.md) | Ouvrir le bon dossier dans Bob, donner du contexte, travailler en binôme.         |
| [03 — Recherche web avec Tavily](03_bob_mcp_web.md)  | Distinguer lecture d'une URL et recherche web, puis configurer et tester le MCP. |

### Réaliser un challenge, de l'énoncé au résultat

| Fiche                                                    | Résultat recherché                                                           |
| -------------------------------------------------------- | ---------------------------------------------------------------------------- |
| [04 — Préparation](04_projet_etape0_preprojet.md)      | Un environnement prêt et un premier test réussi avec Bob.                    |
| [05 — Comprendre et cadrer](05_projet_etape1_cadrage.md)   | Un objectif en une phrase, un hors périmètre et un critère de réussite.      |
| [06 — Plan et mise en place](06_projet_etape2_setup.md)    | Un plan en quelques étapes et un premier test minimal qui fonctionne.        |
| [07 — Réalisation](07_projet_etape3_production.md)         | Le résultat attendu obtenu par petites étapes vérifiées.                     |
| [08 — Vérification](08_projet_etape4_finalisation.md)      | Un résultat relancé de bout en bout, avec ses limites notées.                |
| [09 — Restitution](09_projet_etape5_pitch.md)              | Un résumé court, factuel et un retour sur l'usage de Bob.                    |

## 4. Le déroulé d'un challenge

Les durées ci-dessous sont indicatives. Les consignes de l'animateur prévalent pour les horaires et les livrables. La préparation (fiche 04) se fait **avant** le premier challenge et n'est pas comptée.

| Étape                          | Fiche | Challenge de 30 min | Challenge de 1 h |
| ------------------------------ | ----- | ------------------- | ---------------- |
| **Comprendre et cadrer**       | 05    | 5 min               | 10 min           |
| **Plan et mise en place**      | 06    | 5 min               | 10 min           |
| **Réalisation**                | 07    | 10 min              | 20 min           |
| **Vérification**               | 08    | 5 min               | 10 min           |
| **Restitution**                | 09    | 5 min               | 10 min           |

Si vous prenez du retard, réduisez le périmètre plutôt que de sauter la vérification. Un petit résultat vérifié vaut mieux qu'un grand résultat incertain.

## 5. Bien utiliser Bob pendant un challenge

### Choisir le mode selon le besoin

* **Ask** : comprendre un énoncé, explorer des fichiers ou clarifier une question.
* **Plan** : préparer une réalisation et comparer les options lorsqu'un arbitrage est nécessaire.
* **Agent** : implémenter, modifier des fichiers, exécuter des commandes et vérifier les résultats.

Ask → Plan → Agent est un parcours utile pour une tâche incertaine. Une correction simple peut commencer directement en Agent.

### Donner une tâche vérifiable

Adaptez les prompts des fiches en indiquant :

* le résultat attendu ;
* les fichiers ou éléments concernés ;
* les contraintes à respecter ;
* un exemple d'entrée et de sortie lorsque cela aide ;
* les critères de réussite.

Vérifiez les résultats obtenus et les commandes réellement exécutées. Une réponse convaincante ne suffit pas à valider un résultat.

### Suivre le budget réel

Vérifiez votre solde au démarrage et à la fin de chaque challenge. Les allocations dépendent des comptes utilisés ; les montants donnés en exemple ne constituent pas une garantie.

Les instructions projet et les contenus chargés contribuent au contexte traité par Bob. Gardez-les utiles et concis.

Si vous utilisez Tavily, distinguez **la consommation Bob** et **les crédits du service de recherche**.

## 6. Travailler seul ou en binôme

* Seul, suivez les fiches 05 à 09 dans l'ordre.
* En binôme, répartissez les rôles : une personne pilote Bob, l'autre relit les résultats et vérifie.
* Dans un même dossier de travail, une seule personne modifie les fichiers à la fois.
* Les découvertes utiles (prompt efficace, erreur rencontrée) sont partagées avec le groupe.

Les identifiants et les prérequis locaux restent à configurer sur chaque poste. Ne partagez jamais une clé API.

## 7. Ce que le résultat doit montrer

Un résultat réussi est **simple, vérifié et honnête**.

Distinguez explicitement :

* ce qui a été réellement exécuté et ce qui a été seulement décrit ;
* les données réelles et les données d'exemple ;
* les résultats constatés, les hypothèses et les pistes d'amélioration.

Avant de conclure, relancez le résultat une dernière fois depuis le début et notez ses limites.

## 8. Documents complémentaires et références

Ce dépôt contient les dix fiches et ce README. Les énoncés des challenges sont fournis par l'animateur et ne sont pas inclus dans le dépôt.

### Documentation des outils

* [IBM Bob — Documentation](https://bob.ibm.com/docs/ide)
* [IBM Bob — Modes](https://bob.ibm.com/docs/ide/features/modes)
* [IBM Bob — Bobcoins](https://bob.ibm.com/docs/ide/account/bobcoins)
* [IBM Bob — Initialiser un projet](https://bob.ibm.com/docs/ide/tutorials/start-a-project)
* [IBM Bob — Configuration MCP](https://bob.ibm.com/docs/ide/configuration/mcp/mcp-in-bob)
* [Tavily — Serveur MCP officiel](https://github.com/tavily-ai/tavily-mcp)

---

*ESGI_Arrow_IBM_2026*

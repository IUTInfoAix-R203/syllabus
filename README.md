# <img src="https://raw.githubusercontent.com/IUTInfoAix-R510/Syllabus/main/assets/logo.png" alt="class logo" class="logo" width="120"/> R2.03 — Qualité de développement

## BUT Informatique — 1ère année — IUT Aix-Marseille (département Informatique)

---

## 📋 Informations générales

- **Intitulé** : R2.03 - Qualité de développement
- **Semestre** : S2
- **Volume horaire PN** : 18 h (dont 14 h de TP)
- **Maquette locale 2025-2026** : 4 h CM + 5 h TD + 13 h TP + 2 h test écrit
- **Responsable** : [Sébastien NEDJAR](mailto:sebastien.nedjar@univ-amu.fr)
- **Enseignantes** :
  - [Sophie Nabitz](mailto:sophie.nabitz@univ-avignon.fr)
  - [Leïla Sakli Miled](mailto:leila.SAKLI@univ-amu.fr)
- **Ressource officielle** : [Annexe D du PN BUT Informatique — fiche R2.03](https://cache.media.enseignementsup-recherche.gouv.fr/file/SPE4-MESRI-17-6-2021/35/5/Annexe_17_INFO_BUT_annee_1_1411355.pdf)
- **Mots-clés officiels** : Qualité, Test, Gestion de version

---

## 🎯 Objectifs pédagogiques

### Objectif général (extrait du PN)

> *Cette ressource finalise le niveau 1 de la compétence 1 en introduisant la mécanique de tests, qui est fondamentale à la réalisation d'un développement d'application. Enfin, l'initiation à l'utilisation d'un outil de gestion de version apporte une première mise en pratique des outils de gestion de projet de la compétence 5.*

En pratique, le module vise à maîtriser les **fondations de l'artisanat logiciel** : gestion de version (Git), tests unitaires automatisés (TDD), gestion des erreurs, débogage, relecture de code. L'objectif est de passer de "ça marche sur ma machine" à **produire du code propre, testé et maintenable**.

### Compétences BUT ciblées

Trois compétences du référentiel BUT Informatique sont ciblées par R2.03 :

| Compétence | Intitulé |
|---|---|
| **Compétence 1** | Développer des applications informatiques simples |
| **Compétence 4** | Concevoir et mettre en place une base de données à partir d'un cahier des charges client |
| **Compétence 5** | Identifier les besoins métiers des clients et des utilisateurs |

### Apprentissages critiques (AC)

Les acquis critiques officiellement rattachés à R2.03 :

- **C1 AC2** — Élaborer des conceptions simples
- **C1 AC3** — Faire des essais et évaluer leurs résultats en regard des spécifications *(cœur du module : tests unitaires et non-régression)*
- **C4 AC2** — Visualiser des données *(traces et outils de débogage)*
- **C5 AC2** — Mettre en place les outils de gestion de projet *(gestion de versions Git/GitHub)*

### Savoirs de référence (descriptif PN)

- Première approche de la gestion des cas d'erreurs (ex : `Exception`…)
- Sensibilisation à la production de **tests unitaires**, problématique de la **non-régression**
- **Automatisation** de tests unitaires
- **Traces** et utilisation d'outils de débogage
- Utilisation d'un **outil de gestion de versions**

### SAÉ concernées par cette ressource

- **S2.01** Développement d'une application
- **S2.02** Exploration algorithmique d'un problème
- **S2.05** Gestion d'un projet

### Acquis d'apprentissage détaillés (implémentation 2025-2026)

À l'issue de cette ressource, l'étudiant sera capable de :

1. **Utiliser Git en pro** : rebase, cherry-pick, rebase interactif, reflog, Conventional Commits *(C5 AC2)*
2. **Collaborer** via pull request + code review croisée, et relire constructivement le code d'un pair *(C5 AC2)*
3. **Pratiquer le TDD strict** : cycle RED-GREEN-REFACTOR, baby steps, fake-it, triangulation *(C1 AC3)*
4. **Gérer les cas d'erreur** : `try/catch`, exceptions vérifiées vs non vérifiées, messages d'erreur explicites *(C1 AC2)*
5. **Pratiquer la non-régression** : un filet de tests exécuté en CI à chaque modification *(C1 AC3)*
6. **Lire des traces de test et un stack trace** pour localiser la cause d'un échec *(C4 AC2)*
7. **Utiliser Copilot Chat comme tuteur** (compréhension, documentation), jamais comme générateur de solution *(C5 AC2)*

> **Note** : le TP3 (kata en pair programming) et le TP4 (refactoring et code smells) vont au-delà du strict descriptif PN. Ces ajouts visent à consolider C1 AC3 en pratiquant le TDD sur des exercices plus riches et à préparer la SAÉ 2.01 (développement d'application) en introduisant les réflexes de lecture et d'amélioration de code existant.

---

## 📚 Prérequis

Le PN ne formalise **aucun prérequis** pour R2.03. En pratique, le module s'appuie sur :

### Connaissances recommandées

- **R1.01 (Initiation au développement)** : bases de la programmation (C++)
- **R2.01 (Développement orienté objets)** : POO Java (classes, héritage, interfaces, collections)
- **Bases de Git au S1** : `clone`, `add`, `commit`, `push`, `pull`, `branch`, `checkout` — le TP1 sert justement à corriger les mauvaises habitudes acquises et à introduire les concepts avancés

### Compétences techniques

- Utilisation d'un IDE Java (VS Code, IntelliJ) ou Codespaces dans le navigateur
- Ligne de commande Unix
- Lecture de messages d'erreur et de stacks traces

### Environnement technique

- **Java 25** (JDK Zulu)
- **Maven Wrapper 3.9.14** (`./mvnw` fourni dans chaque TP, aucune installation manuelle)
- **GitHub Codespaces** (recommandé, environnement cloud préconfiguré)
- **VS Code** + extensions Java + **GitHub Copilot Chat** (activé en mode tuteur)

---

## 📖 Programme détaillé

### Calendrier 2025-2026

Le module est concentré sur **4 semaines d'enseignement** du 27 avril au 18 mai 2026, suivies d'un **examen écrit** en commun avec R2.02 le 15 juin :

| Semaine | Date | CM | TD | TP | Contenu |
|---|---|---|---|---|---|
| 1 | Lun. 27 avril 2026 | 2 h | — | — | **CM1** : Artisanat logiciel, qualité, Git avancé |
| 2 | Lun. 4 mai 2026 | 2 h | 4 h | 4 h | **CM2** : TDD & refactoring · **TP1** Git (~2 h TD) · **TP2** TDD |
| 3 | Lun. 11 mai 2026 | — | — | 4 h | **TP3** Kata en pair programming |
| 4 | Lun. 18 mai 2026 | — | — | 4 h | **TP4** Refactoring |
| **Examen** | **Lun. 15 juin 2026** | — | **2 h** | — | **CC3** test écrit commun avec R2.02 (salle de test) |

**Durée d'une séance** : bloc de 4 h ou 2 × 2 h selon le groupe. Le responsable organise le découpage avec la scolarité.

**Entre le TP4 (18 mai) et l'examen (15 juin)** : la SAE 2.01 occupe les étudiants. L'examen a lieu **après la SAE** pour que les étudiants y arrivent avec les réflexes TDD consolidés par leur projet.

### Cours magistraux (4 h au total)

| CM | Thème | Prépare | Niveau Bloom | Statut |
|----|-------|---------|--------------|--------|
| CM1 | Artisanat logiciel, qualité, Git avancé | TP1 + TP2 | Comprendre → Appliquer | ⏳ À venir |
| CM2 | TDD, refactoring, code smells, Clean Code | TP3 + TP4 | Analyser → Créer | ⏳ À venir |

Deux **démos live** de 20 min complètent les CM, en ouverture des séances TP3 et TP4 :
- Avant TP3 : kata en pair programming (driver/navigator) sur Bowling ou Tennis
- Avant TP4 : refactoring IDE sur Gilded Rose (reconnaissance d'un code smell, application d'un refactoring de Fowler étape par étape)

**Fil rouge des CM** — trois axes traversent l'ensemble :

- **🔨 Artisanat** : conventions (Conventional Commits) → baby steps → kata comme exercice régulier
- **✨ Qualité** : tests comme spécification exécutable → couverture → code smells → refactorings
- **🤝 Collaboration** : Git avancé → PR + review → pair programming

### Travaux pratiques (13 h TP + 4 h TD)

| TP | Thème | Exercices | Format | Noté | Statut |
|----|-------|-----------|--------|------|--------|
| [TP1](https://github.com/IUTInfoAix-R203/tp1) | Git avancé et bonnes pratiques | 7 ateliers | ~2 h TD (semaine 2) | ❌ mise à niveau | ✅ Publié |
| TP2 | TDD | 6 + 1 bonus | ~6 h (TD semaine 2 + TP semaine 2) | ✅ autograding | ⏳ À venir |
| TP3 | Kata et pair programming | 6 | 4 h TP (semaine 3) | ✅ autograding | ⏳ À venir |
| TP4 | Refactoring | 6 | 4 h TP (semaine 4) | ✅ autograding | ⏳ À venir |

Chaque TP est autonome (son propre repo Git, sa propre fiche Classroom) mais s'inscrit dans la progression : le workflow Git du TP1 (branche → PR → review → merge) est appliqué systématiquement dans TP2-4, et le TDD baby-steps du TP2 est le cadre d'exécution des kata du TP3 et des refactorings du TP4.

---

## 🎓 Philosophie pédagogique

### Approche TDD baby-step (TP2 à TP4)

Chaque exercice pendant les TP est structuré comme une série de **tests désactivés** (`@Disabled`). L'étudiant active les tests **un par un** dans l'ordre, écrit le code minimal pour les faire passer (fake-it → triangulation → obvious), puis avance.

Cette approche :

- Évite la panique face à une page blanche
- Rend visible la progression (chaque test vert = un concept maîtrisé)
- Habitue au **développement incrémental** professionnel
- Donne un feedback continu via l'autograding GitHub Classroom

### Workflow professionnel

- **Lien Classroom** pour chaque TP → un repo par étudiant dans `IUTInfoAix-R203-2026`
- **Une branche par exercice** (workflow introduit au TP1)
- **Pull Request** pour chaque exercice terminé, **revue croisée** obligatoire (voisin·e + revue Copilot automatique)
- **Auto-évaluation** via les tests qui tournent en CI GitHub Actions (TP2-4)
- **Historique propre** en Conventional Commits (pas de `wip` ni de `fix typo`)

### Copilot comme tuteur (pas comme générateur)

L'usage de **GitHub Copilot Chat** est **encouragé** dans un rôle pédagogique précis, défini dans chaque TP via `.github/copilot-instructions.md` :

- ✅ Expliquer un concept avant de proposer du code (escalade 3 niveaux : concept → Javadoc → code minimal)
- ✅ Orienter vers la documentation officielle
- ✅ Refuser les commandes destructrices sans expliquer leurs effets (ex : `git reset --hard`, `git push --force`)
- ❌ Donner une solution complète dès la première demande
- ❌ Écrire plus de code que le strict minimum pour faire passer le test rouge courant

**Pourquoi c'est essentiel** : l'évaluation CC3 se fait **sur feuille, sans outil**. L'étudiant doit construire ses propres automatismes.

---

## 📊 Évaluations

| Contrôle | Coefficient | Modalité | Description |
|----------|------------|----------|-------------|
| **CC1** | 10 | Automatique | Moyenne des notes autograding des **TP2 + TP3 + TP4** (TP1 non compté) |
| **CC2** | 10 | Continue | Participation, qualité des revues de PR, régularité des commits |
| **CC3** | 40 | Écrit final | Mini-kata TDD à écrire sur feuille (2 heures, sans outil d'assistance) |

### CC1 — Autograding TP

Chaque TP (à partir du TP2) publie une note sur GitHub Classroom via le workflow `classroom.yml` :

- Compilation : 10 pts
- Chaque exercice : 90 / N pts (équirépartition sur les N exercices)
- À l'intérieur d'un exercice : les points sont répartis entre les méthodes de test
- Un test `@Disabled` rapporte **0 point** (un TP "non fait" reste à 0, pas 100)
- Total sur 100 par TP

La **moyenne de TP2, TP3 et TP4** constitue la note CC1. Le TP1 Git est une mise à niveau obligatoire mais non notée.

### CC2 — Participation et implication

Appréciée tout au long du semestre. Critères :

- Présence active en TP
- Qualité des questions posées
- **Qualité des revues de PR** croisées avec ses voisins (pas des "ok lgtm", mais des commentaires utiles)
- Respect du workflow git (commits Conventional, branches par exercice, PR systématiques)

### CC3 — Examen terminal écrit

- **Date** : lundi 15 juin 2026, **en commun avec R2.02** (salle de test)
- **Durée** : 2 heures
- **Documents autorisés** : aucun outil d'assistance (pas de Copilot, pas d'IDE, pas de navigateur)
- **Sujet** : mini-kata TDD à coder sur feuille — on donne un cahier de tests, l'étudiant écrit le code qui les fait passer en TDD baby steps
- **Barème** : cohérent avec les sujets d'examen des années précédentes

### Anciens sujets d'examen (archive)

- [TestIHM2022 dans l'archive](https://github.com/IUTInfoAix-R203-archive/) — ancien CC partagé R2.02 / R2.03 (kata Wordle). Peut servir comme entraînement pour le format "mini-kata TDD sur feuille".

---

## 🛠️ Ressources techniques

### Dépôts GitHub (organisation [`IUTInfoAix-R203`](https://github.com/IUTInfoAix-R203))

- [`tp`](https://github.com/IUTInfoAix-R203/tp) — index public des TP avec liens Classroom
- [`tp1`](https://github.com/IUTInfoAix-R203/tp1) — TP1 Git avancé
- `tp2`, `tp3`, `tp4` — à venir
- [`syllabus`](https://github.com/IUTInfoAix-R203/syllabus) — ce document
- `cours` — slides Marp des CM (à venir)
- [`template-tp-java`](https://github.com/IUTInfoAix-R203/template-tp-java) — méta-template utilisé pour générer chaque TP (privé, mécanique interne)
- [`classroom-sync`](https://github.com/IUTInfoAix-R203/classroom-sync) — automate la propagation des TPs enseignant vers les templates Classroom (privé, mécanique interne)
- [`IUTInfoAix-R203-archive`](https://github.com/IUTInfoAix-R203-archive/) — anciennes versions des TP (2022) et CC Wordle

### Environnement recommandé

- **GitHub Codespaces** (option cloud gratuite via GitHub Education) — **vivement recommandé**, tout est préconfiguré
- **VS Code + extensions Java + GitHub Copilot Chat** (en local ou dans Codespace)
- **IntelliJ IDEA** (accepté, configurations `.idea/` fournies dans les templates)

### Documentation officielle

- [Pro Git — livre complet gratuit, en français](https://git-scm.com/book/fr/v2)
- [Learn Git Branching — tutoriel interactif](https://learngitbranching.js.org/?locale=fr_FR)
- [Conventional Commits — spécification](https://www.conventionalcommits.org/fr/)
- [JUnit 5 User Guide](https://junit.org/junit5/docs/current/user-guide/)
- [AssertJ Core Documentation](https://assertj.github.io/doc/)
- [Mockito Documentation](https://site.mockito.org)
- [ApprovalTests Java](https://github.com/approvals/ApprovalTests.Java)
- [Martin Fowler — Refactoring](https://refactoring.com) (référence du TP4)
- [Martin Fowler — Test Double](https://martinfowler.com/bliki/TestDouble.html)

### Lectures conseillées (au-delà du module)

- *Clean Code* — Robert C. Martin
- *The Pragmatic Programmer* — Hunt & Thomas
- *Working Effectively with Legacy Code* — Michael Feathers (pour aller plus loin sur le refactoring)
- *Test-Driven Development by Example* — Kent Beck (référence du TDD baby steps)

---

## 📞 Contact

- **Responsable** : [Sébastien NEDJAR](mailto:sebastien.nedjar@univ-amu.fr)
- **Équipe pédagogique** : via les issues GitHub du repo concerné, ou e-mail direct aux enseignantes
- **Questions d'ordre privé** : e-mail au responsable

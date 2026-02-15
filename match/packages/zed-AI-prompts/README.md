# 🤖 Zed AI Prompts — Espanso Package

Templates professionnels de prompts IA pour Espanso. 16 prompts organisés en 6 catégories pour une interaction LLM instantanée.

## 📋 Vue d'ensemble

**Zed LLM Prompts** fournit des templates de prompts d'accès rapide. Tapez `:pr ` (avec un espace) pour ouvrir le menu de recherche de prompts, ou utilisez directement un trigger (ex. `:coder`).

### ✨ Caractéristiques Clés

- 🚀 **16 Prompts Professionnels** — 6 catégories fonctionnelles
- ⚡ **Expansion Instantanée** — Tapez `:trigger` → prompt complet
- 🏭 **Expert Industriel** — Autom&ElecExpert pour les projets d'automatisation
- 📍 **Insertion Facile** — `$|$` marque où coller le contenu
- 🇫🇷 **Support Français** — Autom&ElecExpert répond en français

---

## 🎯 Contenu

### 📦 Architecture

```
zed-AI-prompts/
├── package.yml        # Les 16 prompts
├── _manifest.yml      # Métadonnées du paquet
└── README.md          # Ce fichier
```

### 📚 16 Prompts (6 Catégories)

| Catégorie | Nombre | Triggers |
|-----------|--------|----------|
| **Frameworks** | 1 | `:rtf` |
| **Codage** | 4 | `:coder`, `:review`, `:explain`, `:refactor` |
| **Écriture** | 4 | `:writer`, `:grammar`, `:summary`, `:expand` |
| **Analyse** | 3 | `:analyze`, `:pros-cons`, `:brainstorm` |
| **Productivité** | 3 | `:tldr`, `:list`, `:outline` |
| **Spécialisé** | 1 | `:autom` |

---

## 🚀 Démarrage Rapide

### Installation

```bash
espanso install zed-AI-prompts
```

### Utilisation

1. 📍 Tapez `:pr ` pour ouvrir le menu de recherche de prompts, puis sélectionnez le prompt désiré (ex. `coder`) — ou utilisez `:coder` directement
2. 📋 Collez votre code/contenu où se trouve le curseur
3. 🤖 Interagissez avec le LLM

**Menu de recherche :** Tapez `:pr ` seul (notez l'espace terminal)

---

## 📖 Vue d'Ensemble des Prompts

### 🔧 Frameworks
**1. Role-Task-Format (`:rtf`)** — Définissez le rôle, la tâche, le format de sortie

### 💻 Codage
**2-5. Coding** — Solutions d'expert, reviews, explications, refactoring
- `:coder` — Expert en solutions de codage
- `:review` — Révision de code professionnel
- `:explain` — Explication détaillée
- `:refactor` — Refactorisation de code

### ✍️ Écriture
**6-9. Writing** — Amélioration professionnelle, grammaire, résumés, expansion
- `:writer` — Assistant d'écriture professionnel
- `:grammar` — Correction grammaticale
- `:summary` — Génération de résumés
- `:expand` — Expansion de contenu

### 🔍 Analyse
**10-12. Analysis** — Analyse approfondie, pros/cons, brainstorming
- `:analyze` — Analyse analytique
- `:pros-cons` — Avantages et inconvénients
- `:brainstorm` — Génération d'idées

### ⚡ Productivité
**13-15. Productivity** — TL;DR, listes, outlines
- `:tldr` — Version résumée
- `:list` — Formatage en liste
- `:outline` — Création de plan

### 🏭 Spécialisé
**16. Autom&ElecExpert (`:autom`)** — Expert en automatisation industrielle
- 🔌 Expertise Siemens, Beckhoff, Schneider Electric
- ⚡ Ingénierie électrique & conformité (NF C 15-100, ATEX)
- 📊 Gestion de projet & analyse de risques (AMDEC/HAZOP)
- 🇫🇷 Réponses en français pour les projets français

---

## 💡 Bonnes Pratiques

1. 🎯 **Utilisez RTF** — `:rtf` (ou via `:pr `) pour des demandes structurées
2. 🔗 **Chaînez les Prompts** — Combinez-les pour une analyse plus profonde
3. 📝 **Soyez Spécifique** — Plus de contexte = meilleurs résultats
4. 📍 **Utilisez le Point d'Insertion** — `$|$` montre où coller

---

## 📜 Licence

Ce paquet est licencié sous **GPL-3.0**. Voir le fichier `LICENSE` à la racine du projet.

---

## 👤 Auteur

Mathieu Gros — 2026

---

## 🔧 Personnalisation

### Éditer les Prompts

```bash
Éditer : package.yml
```

### Ajouter un Nouveau Prompt

```yaml
- triggers: [":myname", ":pr "]
  replace: "Your prompt: $|$"
  label: "My Prompt"
```

Reload Espanso for changes.

---

## 📄 Files

- **package.yml** - Configuration with all 16 prompts
- **README.md** (in zed-llm-prompts/) - Full documentation
- **README.md** - This overview

---

## � Analyse technique — `match/base.yml` vs `zed-AI-prompts/package.yml`

Résumé :
- `match/base.yml` = fichier *global* (snippets & launchers accessibles partout). Exemples : `:vs`, `:ge`, `:cl`, `:git`, `:date`.
- `zed-AI-prompts/package.yml` = ensemble *spécialisé* de prompts LLM (triggers `:rtf`, `:coder`, `:explain`, `:autom`, etc.).

Constat clé : le package `zed-AI-prompts` contient **majoritairement** des templates LLM — c’est cohérent. Cependant, certaines entrées sont plutôt des commandes d’exécution / utilitaires (non‑prompts) : elles sont candidates au déplacement.

Commandes identifiées comme mal placées (dans `zed-AI-prompts/package.yml`)
- `:runserver`  — démarreurs / instructions d’environnement (dev tooling)
- `:runserver2` — script de détection/lancement multi‑langages (Node/Python/Ruby/Go/Rust)
- `:run`        — `run test` (ambigu et potentiel conflit de trigger)

Pourquoi déplacer : ces trois éléments sont des actions/launchers d’environnement — ils n’appartiennent pas à une collection de *prompts* (séparation des responsabilités, clarté, moindre risque de conflit de triggers).

Recommandations (priorisées) :
1. Créer un package `dev-tools` (ex. `match/packages/dev-tools/`) et y déplacer `:runserver`, `:runserver2`, `:run` **(recommandé)**.
2. Sinon : déplacer ces commandes dans `match/base.yml` (elles deviennent globales).
3. Renommer `:run` en `:runtest` ou `:run:test` pour éviter collisions et ambiguïtés.

Autres suggestions de nettoyage :
- Regrouper les *launchers personnels* (`:git` pointant vers un profil spécifique) dans un package `personal-launchers` si vous voulez exporter/partager le dépôt.
- Harmoniser les triggers (ajouter l’espace terminal `:pr ` consistently) et documenter les conventions dans le `README` racine.

---

## 📧 Aide & Références

- Documentation complète : `zed-llm-prompts/README.md`
- Site officiel Espanso : https://espanso.org/docs/
- Guide Prompt Engineering : https://www.promptingguide.ai/

**Bonnes pratiques de contribution** :
- Vérifier le dépôt upstream avant d’ouvrir une issue.
- Ouvrir une issue descriptive, puis proposer un PR pour la correction.
- Respecter les guidelines de contribution (format, tests, style).

---

## 📄 License

MIT License

---

**Happy prompting! 🚀**

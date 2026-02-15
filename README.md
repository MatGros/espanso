# ✨ Espanso — Collection de Paquets (Local)

Un workspace local pour vos *matches* Espanso (snippets, prompts et launchers). Conçu pour usage personnel **et** partage éventuel (packages dans `match/packages/`).

## 📚 Ressources Utiles

- 🔗 [Projet Espanso](https://github.com/espanso/espanso)
- 📖 [Documentation Officielle](https://espanso.org/docs/)
- 🌐 [Site Web](https://espanso.org)

## 🎯 Objectifs

- ✅ Centraliser vos paquets Espanso (prompts LLM, launchers, snippets)
- ✅ Fournir des outils rapides pour développer, tester et partager des paquets
- ✅ Maintenir une structure modulaire et réutilisable

## 📂 Structure du Projet

```
.
├── match/                      # Définitions Espanso
│   ├── base.yml               # Configuration de base
│   └── packages/              # Paquets exportables
│       ├── zed-AI-prompts/   # Prompts LLM professionnels
│       └── calc/              # Utilitaires de calcul
├── config/                     # Options de configuration
│   ├── default.yml
│   └── notion.yml
└── README.md                   # Ce fichier
```

## 🚀 Démarrage Rapide

```bash
# Installer un paquet local
espanso install zed-AI-prompts

# Ouvrir l'éditeur de configuration
espanso edit

# Recharger Espanso après modification
espanso restart
```

## 💡 Conventions et Bonnes Pratiques

- **Triggers avec menu** : Utilisez `:pr ` (notez l'espace terminal) pour ouvrir le menu de prompts
- **Séparation des responsabilités** : Séparez les *prompts* (contenu LLM) des *launchers* (exécution/shell)
- **Documentation** : Documentez chaque package via un `README.md` local
- **Nommage** : Utilisez des triggers explicites et mémorables

## 🔧 Développement & Maintenance

### Recommandations (priorisées)

1. 📦 Créer un package `dev-tools/` pour les utilitaires (`:runserver`, `:runserver2`, `:run`)
2. 📋 Ajouter `CONTRIBUTING.md` et `CODE_OF_CONDUCT.md` si partage/publication planifiée
3. 🔗 Ajouter le champ `repository` dans les manifests pour faciliter le lien vers GitHub

Each package in `match/packages/` has its own README.md with full documentation.

---

## 📝 Licence

Ce dépôt est **licencié sous la GNU GPL v3.0** (GPL‑3.0). Voir le fichier `LICENSE` à la racine.

Ce que cela signifie :

- ✅ Vous pouvez utiliser, modifier et redistribuer ces fichiers
- ✅ Toute redistribution de travaux dérivés doit conserver la même licence (GPL‑3.0)
- ℹ️ Pour un usage strictement local, aucune action n'est nécessaire

---

## 👤 Auteur

Mathieu Gros — `mathieu.gros@gmail.com` (2026)

---

**Contributions bienvenues !** Si vous souhaitez améliorer ce projet, n'hésitez pas à soumettre une PR ou une issue.
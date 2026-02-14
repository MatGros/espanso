# Espanso — collection de paquets (local)

Ce dossier contient des paquets Espanso personnalisés destinés à un usage local ou à la distribution (voir `match/packages/`).

Références principales
- Projet Espanso (upstream) : https://github.com/espanso/espanso
- Documentation Espanso : https://espanso.org/docs/

But / Utilisation
- Ce workspace regroupe des paquets (prompts, configurations) pour Espanso.
- Le paquet `zed-AI-prompts` fournit des modèles de prompts utiles pour préparer du code ou s'informer sur les bonnes pratiques avant de programmer.

Recommandations pour l'architecture de la documentation
- Centraliser la documentation : garder un `README.md` à la racine + README par paquet.
- Ajouter `CONTRIBUTING.md` et `CODE_OF_CONDUCT.md` si contributions externes prévues.
- Ajouter le champ `repository` dans `_manifest.yml` / `package.yml` pour chaque paquet.
- Considérer un dossier `docs/` pour guidance, exemples et procédures de contribution.

Prochaines étapes suggérées
1. Harmoniser les `README.md` par paquet et centraliser les consignes.
2. Ajouter un `CONTRIBUTING.md` avec procédures de PR et tests.
3. Mettre à jour les manifests pour référencer le repo GitHub.

---

Si vous voulez, je peux appliquer ces changements supplémentaires (CONTRIBUTING, manifests, etc.).
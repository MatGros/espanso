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

Analyse rapide des fichiers `match/base.yml` et `match/packages/zed-AI-prompts/package.yml`

- `match/base.yml` : définitions globales — snippets et launchers (ex. `:vs`, `:ge`, `:cl`, `:date`, `:git`).
- `zed-AI-prompts/package.yml` : collection spécialisée de *prompts LLM* (ex. `:coder`, `:review`, `:explain`, `:autom`).

Commandes candidates au déplacement (actuellement dans `zed-AI-prompts/package.yml`) :
- `:runserver`, `:runserver2`, `:run` — utilitaires d'exécution/serveur (dev tooling) → recommandé : les déplacer dans un package `dev-tools/` ou dans `base.yml`.

Souhaitez‑vous que je déplace ces commandes maintenant ? (je peux aussi renommer `:run` pour lever l'ambiguïté). 

---

Si vous voulez, je peux appliquer ces changements supplémentaires (CONTRIBUTING, manifests, déplacer commandes, etc.).
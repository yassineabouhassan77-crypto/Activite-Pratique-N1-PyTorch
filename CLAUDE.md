# Instructions pour Claude Code

Projet : TP « Activité pratique N°1 — Mise en œuvre du framework PyTorch » (EMSI, filière Data & IA).
Projet **uv** (`pyproject.toml`, `uv.lock`, `.python-version`), notebooks à la racine.
Langue du projet : **français** (code commenté, markdown, messages de commit).

## Règle principale : une étape à la fois

Le dépôt est publié sur GitHub **étape par étape**. Le plan est dans `ETAPES.md`.

Quand l'utilisateur dit « fais l'étape N » :
1. Vérifier avec `git log --oneline` que l'étape N-1 est déjà commitée et poussée. Sinon, s'arrêter et le dire.
2. Faire l'action de l'étape (colonne « Action » de `ETAPES.md`). Pour un notebook :
   `uv run jupyter nbconvert --to notebook --execute --inplace <notebook>`
3. Lire les sorties : vérifier qu'il n'y a pas d'erreur et résumer les résultats (pertes, accuracy, MAE...).
   Les exercices 2 et 4 (MNIST) n'ont pas pu être exécutés sur les vraies données lors de la préparation :
   vérifier que les chiffres cités dans leurs cellules de conclusion (≈ 97 %, > 98 %, effet du Dropout)
   correspondent aux sorties obtenues, et corriger le texte si besoin avant de commiter.
4. `git add` **uniquement** les fichiers listés pour l'étape N dans `ETAPES.md`.
5. `git commit -m "<message de ETAPES.md>"` puis `git push`.
6. À l'étape 7, mettre à jour les lignes « voir le notebook » de `README_final.md` avec les accuracy obtenues avant de le renommer.
7. Expliquer en 5 lignes ce que fait l'étape, pour que l'utilisateur puisse le présenter en démonstration.

Ne jamais ajouter les fichiers d'une étape future (dont `README_final.md` avant l'étape 7), ne jamais faire `git add .`,
ne jamais modifier les dates de commit.

## Environnement

- `uv sync` crée `.venv` (ignoré par git) à partir de `uv.lock`. Lancer tout avec `uv run ...`.
- Les exercices 2 et 4 téléchargent MNIST (~50 Mo) dans `data/MNIST/` (ignoré par git).
- Le graphe `torchviz` de `lab1.ipynb` nécessite le logiciel Graphviz ; sans lui, la cellule affiche simplement un message.
- Tout tourne sur CPU (l'exercice 4 prend quelques minutes).

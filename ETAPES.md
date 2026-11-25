# Plan des étapes (un commit + un push par étape)

Chaque étape = exécuter le notebook, vérifier les résultats, puis `git add` des fichiers listés, `git commit`, `git push`.
Ne jamais ajouter une étape avant que la précédente soit poussée.
`README_final.md` reste hors de git jusqu'à l'étape 7.

## Préparation (une seule fois)

1. Installer uv si besoin (Windows PowerShell) :
   `powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"`
2. Créer un dépôt **vide** sur GitHub (sans README), par ex. `Activite-Pratique-N1-PyTorch`.
3. Dans ce dossier :
```bash
git init -b main
git remote add origin https://github.com/<ton-compte>/Activite-Pratique-N1-PyTorch.git
```

## Étapes

| # | Action | Fichiers à ajouter | Message de commit |
|---|---|---|---|
| 0 | — | `.gitignore` `.python-version` `ETAPES.md` `CLAUDE.md` `data/README.md` | `Initialisation du dépôt` |
| 1 | `uv sync` | `pyproject.toml` `uv.lock` `README.md` `src/lab_pytorch_v1/__init__.py` | `Projet uv lab-pytorch-v1 : dépendances (torch, numpy, ipykernel...)` |
| 2 | exécuter `lab1.ipynb` | `lab1.ipynb` | `Lab 1 : bases de PyTorch (tensors, autograd, nn.Module, boucle d'apprentissage)` |
| 3 | exécuter | `exercice1_salaire.ipynb` | `Exercice 1 : régression du salaire (ancienneté, expertise)` |
| 4 | exécuter | `exercice2_mnist_mlp.ipynb` | `Exercice 2 : classification MNIST avec un réseau entièrement connecté` |
| 5 | exécuter | `exercice3_iris.ipynb` | `Exercice 3 : classification des fleurs Iris` |
| 6 | exécuter | `exercice4_mnist_cnn.ipynb` | `Exercice 4 : classification MNIST avec un CNN` |
| 7 | `mv README_final.md README.md` | `README.md` | `README : résumé des résultats et plan de démonstration` |

Commandes type (étape 3) :

```bash
uv run jupyter nbconvert --to notebook --execute --inplace exercice1_salaire.ipynb
git add exercice1_salaire.ipynb
git commit -m "Exercice 1 : régression du salaire (ancienneté, expertise)"
git push   # à l'étape 0 : git push -u origin main
```

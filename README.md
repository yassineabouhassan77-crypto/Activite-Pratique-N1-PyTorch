# Activité pratique N°1 — Mise en œuvre du framework PyTorch

TP de Deep Learning : tensors, autograd, `nn.Module`, fonctions de coût, optimiseurs, boucle d'apprentissage,
`train()`/`eval()`, `Dataset`/`DataLoader`, sauvegarde de modèles, puis quatre exercices d'application.

Projet géré avec [uv](https://docs.astral.sh/uv/).

## Structure

```
.
├── lab1.ipynb                      Partie 1 : l'essentiel de PyTorch + régression et classification
├── exercice1_salaire.ipynb         Exercice 1 : régression linéaire multiple (salaire ~ ancienneté + expertise)
├── exercice2_mnist_mlp.ipynb       Exercice 2 : MNIST avec un réseau entièrement connecté
├── exercice3_iris.ipynb            Exercice 3 : classification des fleurs Iris
├── exercice4_mnist_cnn.ipynb       Exercice 4 : MNIST avec un CNN
├── src/lab_pytorch_v1/             package du projet
├── data/                           MNIST téléchargé automatiquement (non versionné)
├── pyproject.toml / uv.lock        dépendances (uv)
└── .python-version
```

## Installation

```bash
# installer uv : https://docs.astral.sh/uv/getting-started/installation/
uv sync                 # crée .venv et installe les dépendances du uv.lock
uv run jupyter notebook
```

Dans VS Code : sélectionner l'interpréteur `.venv` comme noyau des notebooks.

## Avancement

Voir `ETAPES.md` : le projet est publié étape par étape.

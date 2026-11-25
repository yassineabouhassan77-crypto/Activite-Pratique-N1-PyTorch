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

## Résultats

| Partie | Résultat |
|---|---|
| Cours — régression `y = 3x + 2 + bruit` | R² = 0.97 |
| Cours — classification 2 classes | Accuracy 100 % |
| Exercice 1 — salaire | MAE test ≈ 380 DH (bruit σ = 500 DH) ; coefficients retrouvés ≈ 593 / 1491 / 4090 (attendus 600 / 1500 / 4000) ; 7 ans + expertise 4 → ≈ 14 200 DH |
| Exercice 2 — MNIST MLP | Accuracy test 97,40 % après 5 époques (F1 macro 0,974) ; 260 erreurs sur 10 000, surtout 5→3, 7→2, 4→9 |
| Exercice 3 — Iris | Accuracy test 100 % ; sans couche cachée ≈ 91 % contre ≈ 98 % avec (moyenne sur 10 graines) |
| Exercice 4 — MNIST CNN | Accuracy test 98,87 % après 3 époques (113 erreurs sur 10 000) ; avec Dropout(0.3) : 98,94 % |

## Démonstration

1. `lab1.ipynb` : autograd (vérification analytique des gradients), boucle d'apprentissage, `train()` contre `eval()` avec Dropout.
2. Exercice 1 : retrouver les coefficients en DH à partir du modèle normalisé.
3. Exercices 2 et 4 : comparaison MLP / CNN, matrice de confusion, images mal classées, sauvegarde et rechargement.

# TP — Data Quality & Data Warehouse

Ce dépôt contient les travaux pratiques du cours de **Data Quality** et de **Data Warehouse / Architecture décisionnelle** à l'EPSI.

Les différents TP sont organisés par chapitre :

```text
epsi-dq-dwh-tp/
├── 01_missing/
│   ├── data/
│   └── notebook/
├── 02_outliers/
│   └── ...
├── pyproject.toml
├── uv.lock
├── .python-version
└── README.md
```

Chaque dossier contient les ressources nécessaires au TP :
notebook, données et éventuellement des fonctions Python déjà fournies.

---

## Recommandation pour Windows

Pour les utilisateurs de Windows, il est **recommandé d'utiliser WSL** (*Windows Subsystem for Linux*) pour réaliser les TP.

Cela permet de travailler dans un environnement Linux plus proche de ceux utilisés en développement et en production, et d'éviter certains problèmes liés aux chemins, aux permissions ou à l'exécution de commandes et scripts.

Si vous utilisez WSL, réalisez les étapes suivantes directement depuis votre terminal Linux.

L'utilisation native de Windows reste possible, mais peut nécessiter quelques adaptations supplémentaires.

---

## 1. Cloner le dépôt

Dans un terminal, placez-vous dans le dossier de votre choix puis exécutez :

```bash
git clone <URL_DU_REPO>
```

Puis :

```bash
cd epsi-dq-dwh-tp
```

---

## 2. Installer `uv`

Le projet utilise **uv** pour gérer Python et les dépendances.

### Windows

Dans PowerShell :

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### Linux / macOS / WSL

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Fermez puis rouvrez votre terminal après l'installation.

Vérifiez ensuite :

```bash
uv --version
```

Sous Windows, si `uv` n'est toujours pas reconnu :

```powershell
$env:Path += ";$HOME\.local\bin"
```

Puis :

```powershell
uv --version
```

---

## 3. Installer l'environnement Python

À la racine du dépôt :

```bash
uv sync
```

Cette commande :

- installe la version de Python utilisée par le cours si nécessaire ;
- crée l'environnement virtuel `.venv` ;
- installe toutes les dépendances nécessaires aux TP.

Il n'est pas nécessaire de créer manuellement un environnement Python.

Vous pouvez vérifier la version utilisée avec :

```bash
uv run python --version
```

---

## 4. Ouvrir les notebooks

Ouvrez le dossier dans VS Code.

Les extensions suivantes sont recommandées :

- Python ;
- Jupyter.

Ouvrez ensuite le notebook du TP.

En haut à droite, cliquez sur **Select Kernel** et sélectionnez l'environnement du projet situé dans :

```text
.venv
```

En cas de doute, exécutez dans une cellule :

```python
import sys
print(sys.executable)
```

Le chemin doit pointer vers le dossier `.venv` du projet.

---

## 5. Réaliser les exercices

Certaines cellules contiennent des zones à compléter :

```python
# =========================
# START CODE HERE
# =========================


# =========================
# END CODE HERE
# =========================
```

Ne modifiez que les parties demandées.

Les notebooks contiennent également des questions d'analyse et d'interprétation. L'objectif n'est pas uniquement d'obtenir du code fonctionnel, mais de justifier les choix effectués.

---

## 6. Récupérer les nouveaux TP

De nouveaux dossiers pourront être ajoutés au dépôt au cours du module.

Pour récupérer les dernières versions :

```bash
git pull
```

Puis, si nécessaire :

```bash
uv sync
```

Les TP déjà publiés sont autant que possible conservés sans modification afin d'éviter les conflits avec votre travail local.

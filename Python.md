# Guide de Développement en Python

## Environnement de Développement

### IDE

- **[PyCharm](https://www.jetbrains.com/fr-fr/pycharm/)** (Recommandé) : Intégration native avec Poetry.

### Éditeur de Code

- **VSCode / [VSCodium](https://vscodium.com/)** : Extension Python à installer afin de bénéficier d'outils de développement.

## Gestion des Versions de Python avec Pyenv

[Pyenv](https://github.com/pyenv/pyenv) permet de gérer plusieurs versions de Python sur un même système.

### Utilisation

1. Installer une version spécifique de Python :

    ```bash
    pyenv install <version>
    ```

2. Définir la version globale du système :

    ```bash
    pyenv global <version>
    ```

> La version de Python doit être choisie en fonction de la compatibilité des bibliothèques principales du projet.

- [Documentation officielle](https://github.com/pyenv/pyenv?tab=readme-ov-file#usage)
- [Documentation non officielle de la CLI](https://cheat.readthedocs.io/en/latest/python/pyenv.html)

## Gestion de projet et des dépendances avec Poetry

[Poetry](https://python-poetry.org) est un outil de gestion de dépendances et d'environnements virtuels pour Python.

### Configuration et Initialisation

1. Configurer Poetry pour créer les environnements virtuels dans le projet :
  
    ```bash
    poetry config virtualenvs.in-project true
    ```

2. Initialiser un projet Poetry :

    Nouveau projet :

    ```bash
    poetry new <project-name>
    ```

    Projet existant :

    ```bash
    cd <project-name>
    poetry init
    ```

### Architecture

Un projet Poetry est structuré comme suit :

```text
<project-name>
┠── pyproject.toml: Metadonnées, dépendances et configurations du projet
┠── poetry.lock: Fichier de gestion des dépendances
┠── <project-name>: Dossier contenant le code source du projet
        ┖── __init__.py: Entrypoint du projet
┠── tests
        ┖── __init__.py: Entrypoint du package de test du projet
```

### Utilisation

- Lancer un script Python dans l'environnement Poetry :

  ```bash
  poetry run python <project-name>/__init__.py
  ```

### Gestion des Dépendances

- Ajouter une dépendance :  

  ```bash
  poetry add <module>
  ```

- Installer les dépendances définies dans `pyproject.toml` :

  ```bash
  poetry install
  ```

- Mettre à jour les dépendances :  

  ```bash
  poetry update
  ```

### Utilisation avec Jupyter Notebook

1. Ajouter Jupyter en tant que dépendance de développement :

   ```bash
   poetry add -D jupyter
   ```

2. Démarrer un serveur Jupyter Notebook depuis l'environnement Poetry :

   ```bash
   poetry run jupyter notebook
   ```

### Gestion de l'Environnement Virtuel

- Afficher les informations sur l'environnement virtuel actuel :

  ```bash
  poetry env info
  ```

- Lister les environnements virtuels disponibles :

  ```bash
  poetry env list
  ```

- Activer l'environnement virtuel du projet :

  ```bash
  poetry env use .venv/Scripts/python.exe
  ```

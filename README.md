# Heap Overflows en 2026

Projet universitaire (TER) sur l'exploitation du tas (glibc 2.40 et 2.41)

## Fichiers

| Document | Source | Sortie |
|---|---|---|
| Rapport principal | `Heap_Overflow_Slides/main.tex` (sections dans `sections/`) | `main.pdf` |

Dépendances de `main.tex` : `sections/` (chapitres), `images/` (figures), `refs-doc.bib` (bibliographie).

## Compilation

Depuis le répertoire `Heap_Overflow_Slides/` :

```bash
make            # génère main.pdf
make clean      # supprime les fichiers générés
```

Ou directement avec [latexmk](https://www.ctan.org/pkg/latexmk), qui enchaîne automatiquement les passes de bibliographie. Le drapeau `-shell-escape` est **obligatoire** car `minted` appelle Pygments :

```bash
latexmk -pdf -shell-escape main.tex
```

## Prérequis

Les blocs de code et les boîtes `pwndbg` utilisent le paquet [`minted`](https://www.ctan.org/pkg/minted), qui délègue la coloration syntaxique à [Pygments](https://pygments.org/) (écrit en Python). Il faut donc, en plus d'une distribution TeX Live :

- **`minted`** (paquet LaTeX) ;
- **Python 3** et **Pygments** ;
- lancer la compilation avec **`-shell-escape`** (déjà activé dans le `Makefile`).

Exemples d'installation :

- Fedora :
  ```bash
  sudo dnf install texlive-scheme-medium texlive-minted latexmk python3-pygments
  ```
- Debian/Ubuntu :
  ```bash
  sudo apt install texlive-latex-extra texlive-plain-generic latexmk python3-pygments
  ```
- Overleaf : fonctionne tel quel (`-shell-escape` y est activé par défaut pour `minted`).

Si `pygmentize` n'est pas dans le `PATH`, l'installer via `pip install Pygments`.

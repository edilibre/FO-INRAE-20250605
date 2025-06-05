---
title: Approfondissement -- LaTeX et outils connexes
author: Sébastien Mengin
bibliography: ExempleBib.bib
---

# Gestion des documents volumineux

- commandes `\input` et `\include`
- commande `\includeonly`
- dossiers pour les éléments graphiques et commande `\graphicspath{}`
- package `comment`

# Conversions en LaTeX et Word

- pratiques actuelles
- améliorations possibles ? (scripts ?)
- utiliser LaTeX pour la mise en page finale[^1]

# Saisie en Markdown

- un exemple : <https://opensource.com/article/18/9/pandoc-research-paper>
- gestion des bibliographies avec Zotero et l'extension better-bibtex [@smith2023economic]
- exemple de commande à saisir dans un terminal pour exporter en LaTeX :
  
  ```shell
  pandoc -f markdown -t latex --biblatex -s FO-INRAE-approfondissement.md -o FO-INRAE-approfondissement.tex
  ```

- éditeur collaboratif en temps réel markdown
  - stylo (<https://stylo.huma-num.fr/>)

# Rédaction collaborative en temps réel avec Overleaf

- limites d'Overleaf en version gratuite : 1 collaborateur max avec droit d'écriture[^droits]

[^droits]: Une note de bas de page peut être balisée avec un chiffre ou avec un mot, `pandoc` se charge des compteurs...

- solutions alternatives :
  - gérer les droits d'accès aux différents collaborateurs (écriture, lecture)
  - utiliser des gestionnaires de version (github et cie). Limite : asynchrone

[^1]: Par conséquent, rédiger en markdown le reste du temps...

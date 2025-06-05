---
title: Approfondissement -- LaTeX et outils connexes
author: Sébastien Mengin
bibliography: ExempleBib.bib
---


# Questions techniques du jour

## Gestion des documents volumineux

- commandes `\input` et `\include`
- commande `\includeonly`
- dossiers pour les éléments graphiques et commande `\graphicspath{}`
- package `comment`

## Conversions en LaTeX et Word

- pratiques actuelles
- améliorations possibles ? (scripts ?)

Avec la ligne suivante les sections ne sont pas numérotées :

  ```
  pandoc --bibliography=Biblio_These.bib --bibliography=ComplementBibTex -o RevueLit.docx main.tex --citeproc --number-sections
  ```


- utiliser LaTeX pour la mise en page finale[^1]

## Bibliographies

Convertir un DOI en bibtex. <https://www.doi2bib.org/>


## Saisie en Markdown

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

# Récapitulatif (benchmark)

## Nextcloud INRAE

- markdown ok
- zotero ? fichiers de bibliographie ?
- images ?
- historique des modifications ?
- validation des modifications ?

## Github ?

## Overleaf version payante

### Rédaction des thèses

Overleaf pour le côté pragmatique, en version payante. Voir pour une version hébergée sur les serveurs INRAE ?

### Rédaction d'articles de recherches

Développer l'instance markdown sur nextcloud INRAE ?

# Perspectives 

Selon nouvelle session de formation 2025-2026 à soumettre.

## Utilisation des templates LaTeX

- rédiger en format basique (article, report, etc.) pour la compatibilité maximale avec d'autres templates
- appliquer un template déterminé lorsqu'il existe ou est fournir par une revue
- créer des templates propres aux articles et travaux publiés pour Dynafor :
  - template écologie
  - template SHS
  - interdisciplinaire

## Groupe de travail LaTeX

Piloté par infogéom, animé par les utilisateurs LaTeX du laboratoire.

# Calendrier prochaines sessions

## Juin 

13, 16, 20, 24, 25

## Juillet

9, 10, 18, 21, 24, 25

[^1]: Par conséquent, rédiger en markdown le reste du temps...

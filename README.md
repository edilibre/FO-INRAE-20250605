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

## Conversions entre LaTeX et Word

- pratiques actuelles
- améliorations possibles ? (scripts ?)

Avec la ligne suivante les sections ne sont pas numérotées :

  ```shell
  pandoc --bibliography=Biblio_These.bib --bibliography=ComplementBibTex -o RevueLit.docx main.tex --citeproc --number-sections
  ```

Avec celles-ci, c'est correct semble-t-il (pour cet exemple on passe du format markdown du présent au fichier au format LaTeX puis enfin du LaTeX au format docx ; c'est absurde mais c'est juste pour l'exemple ! :-)) :

  ```shell
  pandoc -f markdown -t latex -s  --number-sections --bibliography=ExempleBib.bib --citeproc -o test.tex README.md
  pandoc -f latex -t docx --number-sections test.tex -o test.docx
  ```


**Conclusion :** utiliser LaTeX pour la mise en page finale, écrire en Mardown le plus possible[^1].

## Bibliographies

Convertir un DOI en BibTeX. <https://www.doi2bib.org/>


## Saisie en Markdown

Exemples de processus éditoriaux :

- <https://opensource.com/article/18/9/pandoc-research-paper>
- <https://www.innoq.com/en/blog/2021/12/markdown-with-zotero-workflow/>
- gestion des bibliographies avec Zotero et l'extension better-bibtex [@smith2023economic]
  - <https://retorque.re/zotero-better-bibtex/index.html>

- exemple de commande à saisir dans un terminal pour exporter un fichier Markdown en LaTeX :
  
  ```shell
  pandoc -f markdown -t latex --biblatex -s README.md -o FO-INRAE-approfondissement.tex
  ```

Quelques solutions d'édition collaborative avec Markdown qui proposent une fonction d'exportation :
- <https://hackmd.io/>
- <https://www.markdowntutorial.com/>
- stylo (<https://stylo.huma-num.fr/>)

# Rédaction collaborative avec Overleaf

- limites d'Overleaf en version gratuite : 
  - 1 collaborateur max avec droit d'écriture[^droits]
  - pas de connexion à un dépôt git
  - pas de connexion à Zotero

[^droits]: En version gratuite, Overleaf permet de travailler à plusieurs sur un même document, mais avec des droits d'écriture limités à un seul collaborateur. En version payante, il est possible de travailler à plusieurs avec des droits d'écriture pour tous les collaborateurs.

- avantages d'Overleaf en version payante :
  - interface intuitive
  - gestion des versions
  - exportation en PDF, LaTeX, etc.
  - gestion des bibliographies avec Zotero
  - gestion des figures et images
  - gestion des commentaires et discussions

- inconvénients d'Overleaf :
  - dépendance à un service externe
  - coût de la version payante

- solutions alternatives :
  - gérer les droits d'accès aux différents collaborateurs (écriture, lecture)
  - utiliser des gestionnaires de version (github et cie).

# Récapitulatif (benchmark)

## Nextcloud INRAE

- markdown ok
- zotero ? fichiers de bibliographie ?
- images ?
- historique des modifications ?
- validation des modifications ?

## Github ou GitLab ?

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

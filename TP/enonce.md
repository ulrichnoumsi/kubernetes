# Présentation du TP

Dans ce TP il sera question pour nous de mettre en pratique les connaissances acquises en parcourant ce dépot Github, qui vise à promouvoir le partage de la connaissance.

## Enoncé

* Déployez wordpress en suivant les étapes suivantes:
    - Créez un deployment mysql avec un seul replicat
    - Créez un service de type ClusterIP pour exposer vos pods mysql
    - Créez un deployment wordpress avec les bonnes variables d'environnement pour se connecter à la base de données
    - Votre deployment devra stocker les données de wordpress sur un volume monté dans le /data de votre noeud
    - Créez un service de type NodePort pour exposer le frontend wordpress

#### *NB: Pour mener à bience TP il vous faudra utiliser des fichiers manifests pour mieux comprendre le fonctionnement des differents éléments.*

Merci :)

## Authors

- [@Ulrich NOUMSI](https://www.linkedin.com/in/ulrich-steve-noumsi/)


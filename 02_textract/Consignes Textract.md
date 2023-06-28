---
title: "Consignes"
---

-   Relancer une instance Cloud9

-   Cloner le projet Textract:

*https://github.com/alex-faivre/ice-breaker.git*

-   Lancer la stack CloudFormation

*\$ serverless deploy \--stage \<TEAMNAME\>*

-   Récupérer les fichiers scannés, les injecter dans le bucket crée par
    > la stack CloudFormation

-   L'infrastructure va créer de nouveau fichier CSV mais les données
    > sont toujours chiffrées

-   Synchroniser les fichier csv en local pour les concaténer et
    > télécharger le résultat dans le bucket s3

*\$ aws s3 sync s3://workshop-textract-images-\<TEAMNAME\>/
workshop-textract-images*

*\$ cd workshop-textract-images*

*\$ cat \*.csv \> suspects.csv*

*\$ sed -i \'/\^\$/d\' suspects.csv*

*\$ aws s3 sync . s3://workshop-textract-images-\<TEAMNAME\>*

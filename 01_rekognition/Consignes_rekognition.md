Consignes Rekognition

- Lancer une instance Cloud9 par équipe dans ce même subnet publique (prenez des instances large)
- Cloner le répertoire 

<https://gitlab.ippon.fr/devops-cloud-capitalisation/onboarding/ippon-onboarding-workshop-rekognition.git>

- Installer la commande serverless avec

*$ npm install -g serverless*

- Lancer la stack CloudFormation avec la commande : 

*$ serverless deploy --stage <team\_name>*

- Récupérer le fichier index.html et modifier API\_GATEWAY\_URL par l’url donnée lors de la création de la stack
- Copier ce fichier dans le bucket s3 crée par CloudFormation 

*$ aws s3 cp ./index.html s3://ipi-onboarding-rekognition-website-<team\_name>*

- Ce fichier permet de créer une page statique. Pour y accéder, rendez vous sur le service S3, cliquez sur votre bucket, cliquez sur l’objet index.html et cliquez sur l’url de l’objet.
- Utilisez la page statique pour retrouver l’identité du voleur
- Supprimez ce qu’il y a dans le bucket s3 avec la commande:

$ *aws s3 rm s3://ipi-onboarding-rekognition-website-<team\_name>/index.html*

- Détruire l’infrastructure avec la commande:

*$ serverless remove --stage <team\_name>*

#Consignes Glue

Création d’un nouveau job
Utilisez le rôle IAM
Paramétrage du job

1. Lire les fichiers depuis S3 avec les configurations suivantes :
   1. **Data Format** : CSV
   1. **Delimiter** : Comma (,)
   1. **Quote character** : Double quote (“)
   1. **First line of source file contains column headers** : True
   1. Cliquer le bouton “**infer schema**”
1. Décoder et mettre en qualité les données qui proviennent du fichier suspects.csv en utilisant la requête suivante :
   `	`**select**

**cast(unbase64(trim(prenom)) as string) as prenom**

**, cast(unhex(trim(nom)) as string) as nom**

**, trim(id\_adresse) as id\_adresse**

**from myDataSource**

1. Joindre les deux tables tel que id\_adresse = id
1. Ecrire le résultat dans S3 et demander à Glue de créer une table Athena
   1. **S3 Target Location** : insérer un chemin vers un préfix vide (le chemin doit finir par un “/”)
   1. **Create a table in the Data Catalog and on subsequent runs, update the schema and add new partitions** : True
   1. **Database** : default
   1. **Table name** : <nom de l’équipe>
1. Dans l’onglet **Job details** sélectionner le rôle onboarding-glue-role
1. Sauvegarder le job et exécuter


# <a name="_axdxs8gy81c1"></a>Athena - Pour visionner votre résultat
Nous allons utiliser le service Athena qui permet de requêter des fichiers plats stockés dans S3 avec du SQL.

Mais avant d’écrire votre requête, vous aurez besoin de configurer un chemin vers S3 pour le stockage. Cliquez sur le bouton **Edit Settings** du bandeau bleu :

Renseigner le chemin vers votre bucket d’équipe :


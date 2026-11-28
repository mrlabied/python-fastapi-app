
# TP6 – Variables d'environnement, Inputs et Outputs

## Q1. Pourquoi la variable n'est-elle pas disponible dans la step qui l'a définie, mais seulement dans les suivantes ?

GITHUB_ENV est lu par GitHub Actions après l'exécution de la step. Les variables sont donc disponibles uniquement dans les steps suivantes du même job.

## Q2. Quelle est la portée de GITHUB_ENV ?

GITHUB_ENV permet de partager les variables d'environnement entre les steps d'un même job. La variable APP_NAME n'est donc pas disponible dans le job verify-env.

## Q3. Que se passe-t-il si on écrit > au lieu de >> dans GITHUB_OUTPUT ?

L'opérateur >> ajoute les données sans supprimer le contenu précédent. L'opérateur > écrase le contenu précédent. Le deuxième output remplace donc le premier si on utilise > deux fois.

## Q4. Pourquoi GITHUB_ENV ne suffit-il pas ici, alors que GITHUB_OUTPUT fonctionne entre jobs ?

GITHUB_ENV partage les variables entre les steps d'un même job. GITHUB_OUTPUT permet de créer des outputs au niveau d'une step, de les exposer au niveau du job et de les récupérer dans un autre job grâce à needs.

## Q5. Que se passe-t-il si on retire needs: build du job deploy ?

Le job deploy peut s'exécuter en parallèle avec build. Il ne dispose plus de la dépendance permettant de récupérer les outputs de build avec needs.build.outputs.full_version.

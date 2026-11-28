
# TP 8 – Stratégies GitHub Actions

## Q1. Combien de jobs sont générés ? Donnez la liste des combinaisons.

La matrice contient 2 systèmes d'exploitation et 3 versions de Python.

Nombre de jobs = 2 × 3 = 6 jobs.

Les combinaisons sont :

1. Ubuntu / Python 3.11
2. Ubuntu / Python 3.12
3. Ubuntu / Python 3.13
4. Windows / Python 3.11
5. Windows / Python 3.12
6. Windows / Python 3.13

## Q2. Combien de jobs au total après exclude et include ?

Il reste 6 jobs au total.

- La matrice initiale génère 6 jobs.
- exclude supprime Windows / Python 3.11.
- Il reste donc 5 jobs.
- include ajoute Ubuntu / Python 3.14.

Calcul : 6 - 1 + 1 = 6 jobs.

## Q3. Que se passerait-il si vous tentiez d'exclure la combinaison 3.14 ? Pourquoi ?

La combinaison Ubuntu / Python 3.14 resterait présente.

En effet, exclude est appliqué avant include.

La combinaison Python 3.14 n'existe pas encore dans la matrice initiale lorsque exclude est appliqué.

Elle est ensuite ajoutée par include.

## Q4. Quelle est la différence observée entre fail-fast true et false ? Dans quel cas choisiriez-vous true ou false ?

Avec fail-fast: true, lorsqu'un job échoue, GitHub Actions peut annuler les autres jobs encore en cours ou en attente.

Avec fail-fast: false, les autres jobs continuent leur exécution même si un job échoue.

On choisit true pour arrêter rapidement les exécutions après un échec et économiser les ressources.

On choisit false pour obtenir les résultats de toutes les combinaisons, notamment lors des tests de compatibilité sur plusieurs systèmes et versions.

## Q5. Donnez deux raisons d'utiliser max-parallel en entreprise.

1. Contrôler les coûts et la consommation des ressources en limitant le nombre de jobs exécutés simultanément.

2. Éviter la surcharge de l'infrastructure CI/CD et des runners en répartissant les exécutions.

# Comparative-SLAM-EKF-vs-Graph

## Problématique

Comment l'arbitrage entre la précision et la consommation de ressources évolue-t-il lorsqu'on passe d'une approche récursive (Filtre de Kalman) à une approche globale (Optimisation de Graphe) dans un contexte temps-réel ?

## Les deux approches à comparer

### A. Le Filtre de Kalman Étendu (EKF-SLAM)

C'est l'approche historique. On met à jour l'état du robot et des "landmarks" (points de repère) à chaque nouvelle donnée de capteur.Avantage : Faible latence, mathématiquement élégant pour le temps réel.Inconvénient : La matrice de covariance explose en taille à mesure que la carte grandit (complexité quadratique $O(n^2)$).

### B. L'Optimisation de Graphe (Graph-Based SLAM)

Ici, on considère le trajet du robot comme des nœuds et les mesures comme des contraintes entre ces nœuds.Avantage : Plus robuste sur le long terme (on peut corriger tout le trajet d'un coup lors d'une "fermeture de boucle" ou Loop Closure).Inconvénient : Plus gourmand en calcul lors de l'optimisation (nécessite souvent des solveurs de matrices creuses).

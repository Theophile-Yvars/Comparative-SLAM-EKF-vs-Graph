# MicroSLAM-CPP : Système de Cartographie Mobile en Temps Réel

## Présentation du Projet
Ce projet consiste à développer un système de **SLAM (Simultaneous Localization and Mapping)** de A à Z en C++ pour un petit robot mobile. L'objectif est de transformer les données brutes d'un capteur (Lidar ou Caméra) en une carte cohérente tout en estimant la position du robot avec précision.

## Objectifs du Projet
1.  **Acquisition de données :** Interfaçage avec les capteurs du robot (Lidar/IMU/Odométrie).
2.  **Scan Matching :** Aligner les mesures successives pour estimer le déplacement (Algorithme ICP ou Correlative Scan Matching).
3.  **Cartographie :** Construction d'une grille d'occupation (Occupancy Grid) en temps réel.
4.  **Optimisation :** Correction de la trajectoire lors des fermetures de boucle (Loop Closure).

## Configuration Matérielle
* **Robot :** [Indique ton modèle, ex: TurtleBot, Châssis DIY, etc.]
* **Capteur Principal :** [Ex: RPLidar A1, Intel RealSense, ou simple Caméra USB]
* **Calculateur :** [Ex: Raspberry Pi 4, Jetson Nano]

## Architecture Logicielle (C++)
Le projet est découpé en modules indépendants pour garantir la performance :
* **`Sensor_Driver`** : Lecture et filtrage des données brutes.
* **`Odometry_Engine`** : Calcul de la pose relative via les encodeurs et l'IMU.
* **`SLAM_Core`** : Algorithme de localisation et mise à jour de la carte.
* **`Visualizer`** : Rendu de la carte et du trajet (via OpenCV ou SFML).

## Dépendances
* **Eigen 3** : Pour tous les calculs matriciels et les transformations géométriques.
* **OpenCV** : Pour la visualisation de la grille d'occupation et le traitement d'image.
* **PThreads/C++ Threads** : Pour séparer l'acquisition de données du calcul SLAM.

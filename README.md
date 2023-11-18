# Machine State Classification Using Edge Impulse and Arduino

#  Overview

Ce projet se concentre sur la mise en œuvre d'un système d'apprentissage automatique embarqué pour classer les données de mouvement et de vibration de différentes machines. Notre objectif principal est de détecter différents états opérationnels, tels que 'éteint', 'allumé', 'faible charge', 'forte charge', et d'identifier les anomalies, le tout sans nécessiter de modification des machines.

#  Objectif
L'objectif central du projet est d'exploiter les capacités de l'apprentissage automatique pour catégoriser les états distincts des machines en se basant sur les données d'accéléromètre. Cela comprend la distinction entre les modes de fonctionnement normaux et les anomalies potentielles, ce qui est crucial pour la maintenance prédictive et l'efficacité opérationnelle dans les environnements industriels.

# Configuration et Initialisation

Connexion de la Carte Arduino : Le projet a débuté par la connexion de la carte Arduino à notre système, formant la base de notre appareil de collecte de données.

Chargement du Firmware : Nous avons chargé le firmware Edge Impulse sur l'Arduino à l'aide du script flash fourni (.bat pour Windows). Cette étape était essentielle pour rendre la carte compatible avec Edge Impulse.

Vérification du Système : Après le flashage, nous avons effectué un reset de la carte Arduino et vérifié dans le projet Edge Impulse pour assurer une connectivité et une préparation sans faille pour l'acquisition de données.

# Collecte de Données

Méthodologie : À l'aide d'une application pour smartphone conçue pour générer des vibrations, nous avons imité différents états de machines et collecté les données correspondantes de l'accéléromètre.

Étiquetage des Données : Chaque ensemble de données a été méticuleusement étiqueté selon son état opérationnel pour assurer l'exactitude des phases d'entraînement et de test. Cette étape est cruciale dans les tâches d'apprentissage supervisé.

Volume et Variété : Des données adéquates pour chaque état (off, light, heavy) ont été rassemblées, en veillant à l'équilibre entre les ensembles de données d'entraînement et de test.

![Texte alternatif](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/issues/1#issue-2000591401)

# Extraction de Caractéristiques

Approche : Nous avons employé l'analyse spectrale pour transformer les données brutes de l'accéléromètre en une représentation plus abstraite et informative, adaptée aux algorithmes d'apprentissage automatique.
Intégration du Réseau Neuronal : Un réseau neuronal a été utilisé pour son aptitude à extraire et à apprendre des motifs complexes dans les données.
Détection d'Anomalies avec K-means : Nous avons intégré le clustering K-means pour distinguer les anomalies, une étape cruciale pour détecter des modèles inhabituels qui pourraient indiquer des problèmes potentiels.

![Texte alternatif](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/issues/2#issue-2000593319)

# Entraînement du Modèle

Modèle de Réseau Neuronal : Le cœur de notre projet, le modèle de réseau neuronal, a été entraîné avec les caractéristiques extraites. Les hyperparamètres ont été finement ajustés pour optimiser les performances du modèle.

Précision et Validation : La précision du modèle a été étroitement surveillée pour garantir qu'elle se situe dans des plages acceptables, essentiel pour la fiabilité du système.

![Texte alternatif](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/issues/4#issue-2000593749)

# Détection d'Anomalies

Entraînement de Modèle Séparé : Un modèle de détection d'anomalies supplémentaire a été entraîné, se concentrant sur les caractéristiques qui indiquent le mieux les modèles inhabituels, renforçant les capacités prédictives du système.

![Texte alternatif](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/issues/5#issue-2000594110)

# Test du Modèle

Évaluation des Performances : Les modèles entraînés ont été rigoureusement testés avec des données inédites pour évaluer leur performance, assurant la fiabilité et l'exactitude du système dans des scénarios réels.

![Texte alternatif](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/issues/6#issue-2000594344)

# Déploiement

Application en Temps Réel sur Arduino : L'étape finale a impliqué le déploiement des modèles entraînés sur la carte Arduino, permettant au système de classer efficacement les états des machines en temps réel.

![Texte alternatif](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/issues/7#issue-2000594581)

![Texte alternatif](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/issues/8#issue-2000595253)

![Texte alternatif](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/issues/9#issue-2000595400)

![Texte alternatif](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/issues/10#issue-2000595521)

# Conclusion

Ce projet démontre le potentiel de l'utilisation de l'apprentissage automatique dans un environnement embarqué pour des applications pratiques telles que la surveillance et la classification des états opérationnels des machines. Le déploiement réussi sur la plateforme Arduino souligne la faisabilité d'employer de tels systèmes dans des contextes industriels.



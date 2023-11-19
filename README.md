# Machine State Classification Using Edge Impulse and Arduino
![image](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/assets/148441001/a4e00fb0-9d42-4b18-9aef-4475fb45ef5b) ![image](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/assets/148441001/e4656c55-5ad5-455c-a3da-c7207978ab65)



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

Étiquetage des Données : Chaque ensemble de données a été méticuleusement étiqueté (label) selon son état opérationnel pour assurer l'exactitude des phases d'entraînement et de test. Cette étape est cruciale dans les tâches d'apprentissage supervisé.

Volume et Variété : Des données adéquates pour chaque état (off= anomalie, light = charge légère, heavy = lourde charge) ont été rassemblées, en veillant à l'équilibre entre les ensembles de données d'entraînement et de test.
![Data_acquisation](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/assets/148441001/2dc3cbc8-45de-47f6-960f-1de9049814df)


# Extraction de Caractéristiques

Approche : Nous avons employé l'analyse spectrale pour transformer les données brutes de l'accéléromètre en une représentation plus abstraite et informative, adaptée aux algorithmes d'apprentissage automatique.
Intégration du Réseau Neuronal : Un réseau neuronal a été utilisé pour son aptitude à extraire et à apprendre des motifs complexes dans les données.
Détection d'Anomalies avec K-means : Nous avons intégré le clustering K-means pour distinguer les anomalies, une étape cruciale pour détecter des modèles inhabituels qui pourraient indiquer des problèmes potentiels.

![select_features](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/assets/148441001/ff2d46eb-4c5d-415d-96f5-753387e4815b)
![spectral_features](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/assets/148441001/f3ab5680-e596-4e09-940f-cbcdc58a3e26)


# Entraînement du Modèle

Modèle de Réseau Neuronal : Le cœur de notre projet, le modèle de réseau neuronal, a été entraîné avec les caractéristiques extraites. Les hyperparamètres ont été finement ajustés pour optimiser les performances du modèle.

Précision et Validation : La précision du modèle a été étroitement surveillée pour garantir qu'elle se situe dans des plages acceptables, essentiel pour la fiabilité du système.

![classifier](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/assets/148441001/cc12fbb6-6969-4aa9-aaae-a08d616a53a4)

# Détection d'Anomalies

Entraînement de Modèle Séparé : Un modèle de détection d'anomalies supplémentaire a été entraîné, se concentrant sur les caractéristiques qui indiquent le mieux les modèles inhabituels, renforçant les capacités prédictives du système.

![anomaly_detection](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/assets/148441001/97eda03c-2218-4037-8508-c8d307523018)

# Test du Modèle

Évaluation des Performances : Les modèles entraînés ont été rigoureusement testés avec des données inédites pour évaluer leur performance, assurant la fiabilité et l'exactitude du système dans des scénarios réels.

![model_testing](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/assets/148441001/814dfd29-374d-4332-92a3-0ba8d521c849)

# Déploiement

Application en Temps Réel sur Arduino : L'étape finale a impliqué le déploiement des modèles entraînés sur la carte Arduino, permettant au système de classer efficacement les états des machines en temps réel.

![dep](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/assets/148441001/27733114-1307-4adf-9b5e-06d08af1e018)

![light](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/assets/148441001/a4f26c71-d090-4621-bf54-566f1bc0d185)
![heavy](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/assets/148441001/1fdde810-342a-4f55-8bdc-de38bbdf608b)
![off](https://github.com/GhozlenBY/Motion-Classification-and-Anomaly-Detection/assets/148441001/b498845c-12f5-4451-9bd4-2b5699ccff34)


# Conclusion

Ce projet démontre le potentiel de l'utilisation de l'apprentissage automatique dans un environnement embarqué pour des applications pratiques telles que la surveillance et la classification des états opérationnels des machines. Le déploiement réussi sur la plateforme Arduino souligne la faisabilité d'employer de tels systèmes dans des contextes industriels.



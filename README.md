## 1-Contexte
Les données issues de capteurs installés sur trois éoliennes étaient collectées toutes les 10 minutes, mais leur traitement, analyse et visualisation nécessitaient des interventions manuelles.
L’enjeu principal était donc d’automatiser la collecte, le nettoyage, la transformation, l’analyse et la surveillance des données de production électrique afin de:
- Mieux suivre la performance des éoliennes au quotidien,
- Identifier les anomalies de production,
- Faciliter la prise de décision opérationnelle.
## 2-Approche technique choisie
Le projet met en œuvre une architecture en médaillons (Bronze, Silver, Gold) entièrement orchestrée dans Microsoft Fabric, en s’appuyant sur plusieurs composants intégrés:
- Bronze (Lakehouse Bronze): ingestion des données brutes depuis un fichier CSV et des fichiers quotidiens issus d’une page web.
- Silver (Lakehouse Silver): nettoyage, enrichissement et préparation des données via deux méthodes:
  - Dataflow Gen2 (approche no-code)
  - Notebook Spark Python (approche code)
- Gold (Lakehouse Gold): modélisation en schéma en étoile (tables de faits et de dimensions) prête pour la BI.
- Power BI: création de modèles sémantiques et de rapports interactifs analysant la production d’électricité par jour, heure, et turbine.
- Data Factory: orchestration complète du processus (pipeline d’ingestion, transformation, mise à jour du rapport).
- Reflex/Data Activator: configuration d’alertes automatiques (Outlook/Teams) en cas d’anomalie de production (<120 000 kWh/jour).
L’ensemble du pipeline s’exécute quotidiennement sans intervention manuelle.

## 3-Insights et résultats générés
Le projet a permis de:
- Centraliser et fiabiliser les données issues des capteurs.
- Visualiser la production d’électricité par turbine, région et période dans Power BI.
- Détecter rapidement les anomalies ou baisses de production grâce à un système d’alertes automatiques.
- Réduire les efforts manuels et améliorer la réactivité opérationnelle.
#### KPIs principaux observés:
- Production moyenne journalière: ~150 000 kWh.
- Détection automatique de seuils bas, notifications immédiates.
- Mise à jour quotidienne du rapport et des données en moins de 10 minutes.

  ## Auteur
Mamadou Mouctar CAMARA

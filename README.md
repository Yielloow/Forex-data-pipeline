# Forex-data-pipeline

✅ Jour 1 – Préparation

Crée un repo GitHub : forex-data-pipeline.

Installe les outils :

Python (pandas, requests, sqlalchemy, matplotlib).

PostgreSQL (ou SQLite si tu veux plus simple au début).

Docker (si tu veux dockeriser à la fin).

Choisis une API Forex gratuite :

Alpha Vantage
 (50 requêtes/min gratuit).

Yahoo Finance via yfinance
 (historique facile).

Twelve Data
 (limite gratuite).

✅ Jour 2 – Ingestion

Script Python ingest.py :

Récupérer les cotations EUR/USD en temps réel ou en bougies (1 min ou 5 min).

Sauvegarder brut dans data/raw/eurusd_YYYYMMDD.csv.

Exemple de colonnes : timestamp, open, high, low, close, volume.

✅ Jour 3 – Transformation

Script transform.py :

Charger le CSV.

Nettoyer les valeurs manquantes.

Générer des features :

Moyenne mobile (MA 5, 20).

RSI ou volatilité simple.

Sauvegarder dans data/clean/eurusd_clean.csv.

✅ Jour 4 – Base de données (Load)

Lancer PostgreSQL (local ou via Docker).

Créer une table eurusd_prices :

CREATE TABLE eurusd_prices (
  timestamp TIMESTAMP PRIMARY KEY,
  open FLOAT,
  high FLOAT,
  low FLOAT,
  close FLOAT,
  volume FLOAT,
  ma5 FLOAT,
  ma20 FLOAT,
  rsi FLOAT
);

Script Python load.py :

Insérer les données transformées dans PostgreSQL.

✅ Jour 5 – Visualisation

Installer Grafana ou Metabase (Docker).

Connecter à PostgreSQL.

Créer des dashboards :

Courbe du prix EUR/USD en temps réel.

Moyennes mobiles.

RSI / volatilité.

✅ Jour 6 – Automatisation (DevOps touch)

Créer un Dockerfile pour ton app Python.

Créer docker-compose.yml qui lance :

PostgreSQL

Ton pipeline

Grafana

Ajouter un requirements.txt avec les dépendances.

✅ Jour 7 – CI/CD & Documentation

Mettre en place GitHub Actions :

Lancer ingest.py toutes les heures/jours (scheduler).

Lancer les tests (unitaires si possible).

Ajouter un README.md :

Schéma d’architecture (pipeline).

Instructions pour lancer le projet (docker-compose up).

Captures du dashboard.

🚀 Résultat attendu

Un repo GitHub avec :

Code clair (ingest.py, transform.py, load.py).

Dockerfile + docker-compose.

Un dashboard visible.

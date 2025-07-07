# Consultas SQL – Projeto Cyclistic Bike Sharing

Este arquivo reúne as principais consultas SQL utilizadas durante a análise exploratória do sistema de bicicletas compartilhadas da cidade de Chicago, no contexto do projeto *Cyclistic*. As consultas foram desenvolvidas no PgAdmin 4 utilizando PostgreSQL.

---

##  1. Criação da Tabela (Importação do CSV)

```sql
-- Criação da tabela base para importar os dados de julho de 2025
CREATE TABLE trips_07_2025 (
  ride_id TEXT,
  rideable_type TEXT,
  started_at TIMESTAMP,
  ended_at TIMESTAMP, 
  start_station_name TEXT, 
  start_station_id TEXT,
  end_station_name TEXT,
  end_station_id TEXT,
  start_lat DOUBLE PRECISION,
  start_lng DOUBLE PRECISION,
  end_lat DOUBLE PRECISION,
  end_lng DOUBLE PRECISION,
  member_casual TEXT
);


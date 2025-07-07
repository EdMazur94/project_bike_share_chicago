# SQL Queries do Projeto "_NAME_"

Criação das tabelas para trazer o CSV para o PgAdmin4:

```sql 

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

```



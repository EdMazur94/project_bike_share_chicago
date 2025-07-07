# SQL Queries do Projeto "_NAME_"

- Criação das tabelas para trazer o CSV para o PgAdmin4:

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

- Concatenação dos meses utilizados

```sql

INSERT INTO all_trips
SELECT * FROM trips_04_2024;

INSERT INTO all_trips
SELECT * FROM trips_05_2024;

INSERT INTO all_trips
SELECT * FROM trips_06_2024;

INSERT INTO all_trips
SELECT * FROM trips_07_2024;

INSERT INTO all_trips
SELECT * FROM trips_08_2024;

INSERT INTO all_trips
SELECT * FROM trips_09_2024;

INSERT INTO all_trips
SELECT * FROM trips_10_2024;

INSERT INTO all_trips
SELECT * FROM trips_11_2024;

INSERT INTO all_trips
SELECT * FROM trips_12_2024;

INSERT INTO all_trips
SELECT * FROM trips_01_2025;

INSERT INTO all_trips
SELECT * FROM trips_02_2025;

INSERT INTO all_trips
SELECT * FROM trips_03_2025;

INSERT INTO all_trips
SELECT * FROM trips_04_2025;
```
- Contagem dos Membros

```sql
SELECT member_casual,
COUNT(*) AS total_usuarios
FROM all_trips
GROUP BY member_casual
```

- Média de viagens por dia separado por tipo de usuário:
```sql
SELECT
	member_casual,
	ROUND(AVG(total_rides)::numeric) AS avg_rides_per_day
FROM(
	SELECT
	started_at::DATE AS date_travel,
	member_casual,
	COUNT(*) AS total_rides
FROM all_trips
GROUP BY started_at::DATE, 
		member_casual
ORDER BY date_travel) AS daily_counts
GROUP BY
	member_casual
ORDER BY
	member_casual;
```
- Média de tempo de viagem por tipo de usuário:
```sql
SELECT
	member_casual,
	ROUND(AVG(EXTRACT(EPOCH FROM(ended_at - started_at))/60),2) as ride_length
FROM all_trips
	GROUP BY member_casual
```

- Distribuição do uso das bicicletas por hora do dia e por tipo de usuário:

```sql 
SELECT
  EXTRACT(HOUR FROM started_at) AS hour,
  member_casual,
  COUNT(*) AS total
FROM all_trips
GROUP BY hour, member_casual
ORDER BY hour;
```


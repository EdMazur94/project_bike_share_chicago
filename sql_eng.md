# SQL Queries – How to Turn Casual Riders into Members: A Data Analysis of Chicago’s Bike Sharing System

This file contains the main SQL queries used during the exploratory analysis of the Chicago bike sharing system. All queries were executed using PostgreSQL in PgAdmin 4.

---

## 1. Table Creation (CSV Import)

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

## 2. Combining All Monthly Tables into all_trips

```sql
INSERT INTO all_trips SELECT * FROM trips_04_2024;
INSERT INTO all_trips SELECT * FROM trips_05_2024;
INSERT INTO all_trips SELECT * FROM trips_06_2024;
INSERT INTO all_trips SELECT * FROM trips_07_2024;
INSERT INTO all_trips SELECT * FROM trips_08_2024;
INSERT INTO all_trips SELECT * FROM trips_09_2024;
INSERT INTO all_trips SELECT * FROM trips_10_2024;
INSERT INTO all_trips SELECT * FROM trips_11_2024;
INSERT INTO all_trips SELECT * FROM trips_12_2024;
INSERT INTO all_trips SELECT * FROM trips_01_2025;
INSERT INTO all_trips SELECT * FROM trips_02_2025;
INSERT INTO all_trips SELECT * FROM trips_03_2025;
INSERT INTO all_trips SELECT * FROM trips_04_2025;
```

## 3. Analysis Queries

### 3.1 Total Users by Type (Casual vs Member)

```sql
SELECT member_casual,
       COUNT(*) AS total_users
FROM all_trips
GROUP BY member_casual;
```

### 3.2 Bike Types Used by Each User Type

```sql
SELECT rideable_type, 
       member_casual,
       COUNT(*) AS total_by_type
FROM all_trips
GROUP BY rideable_type, member_casual;
```

### 3.3 Average Rides per Day by User Type

```sql
SELECT member_casual,
       ROUND(AVG(total_rides)::numeric) AS avg_rides_per_day
FROM (
    SELECT started_at::DATE AS date_travel,
           member_casual,
           COUNT(*) AS total_rides
    FROM all_trips
    GROUP BY started_at::DATE, member_casual
) AS daily_counts
GROUP BY member_casual
ORDER BY member_casual;
```

### 3.4 Average Ride Duration

```sql
SELECT member_casual,
       ROUND(AVG(EXTRACT(EPOCH FROM (ended_at - started_at))/60), 2) AS ride_length
FROM all_trips
GROUP BY member_casual;
```

### 3.5 Bike Usage by Hour of the Day

```sql
SELECT EXTRACT(HOUR FROM started_at) AS hour,
       member_casual,
       COUNT(*) AS total
FROM all_trips
GROUP BY hour, member_casual
ORDER BY hour;
```

### 3.6 Seasonality: Usage by Month

```sql
SELECT TO_CHAR(started_at, 'YYYY-MM') AS month,
       member_casual,
       COUNT(*) AS total_rides
FROM all_trips
GROUP BY month, member_casual
ORDER BY month;
```

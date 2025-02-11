# ProjectAdvCoding
## 📌SQL Queries for KSA Trading Data

#### This repository contains a set of SQL queries designed to analyze and extract meaningful insights from the ksa table in the tradings database. The dataset includes various entertainment venues such as theaters and cinemas, along with details like ratings, review counts, locations, and user comments.

#### These queries help in retrieving, filtering, and summarizing the data efficiently. Whether you are looking for the highest-rated places, analyzing customer reviews, or finding location-based insights, these queries will provide valuable results.

## 🚀 SQL Queries
### Below are the queries that can be used to explore and analyze the data:


#### Connect to the database before running the queries.
```sql
USE tradings;
```
#### 1. Retrieve all data from the table.
```sql
SELECT * FROM tradings. ksa;
```

#### 2. Show all places with a rating higher than 4.
```sql
SELECT * FROM ksa WHERE rating > 4;
```
#### 3. Count the number of places for each genre.
```sql
SELECT genre, COUNT(*) AS total_places FROM ksa GROUP BY genre;
```
#### 4. Display places that have more than 10,000 reviews.
```sql
SELECT * FROM ksa WHERE review_count > 10000;
```
#### 5. Find the highest-rated places, sorted in descending order.
```sql
SELECT * FROM ksa ORDER BY rating DESC;
```
#### 6. Show places that have comments (where best_comment is not empty).
```sql
SELECT * FROM ksa WHERE best_comment IS NOT NULL;
```
#### 7. Display places that are located in Saudi Arabia only.
```sql
SELECT * FROM ksa WHERE location LIKE '%Saudi Arabia%';
```
#### 8. Calculate the average rating for each genre.
```sql
SELECT genre, AVG(rating) AS avg_rating FROM ksa GROUP BY genre;
```
#### 9. Show places that have the word "Theater" in their name.
```sql
SELECT * FROM ksa WHERE name LIKE '%Theater%';
```
#### 10. Retrieve 5 random places from the table.
```sql
SELECT * FROM ksa ORDER BY RAND() LIMIT 5;
```

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
![image](https://github.com/user-attachments/assets/828418a2-6497-4be5-87f4-c33bdf2cd7c9)


#### 2. Show all places with a rating higher than 4.
```sql
SELECT * FROM ksa WHERE rating > 4;
```
![image](https://github.com/user-attachments/assets/6a15b0b3-cf46-49fe-bfc5-37c424e913fa)


#### 3. Count the number of places for each genre.
```sql
SELECT genre, COUNT(*) AS total_places FROM ksa GROUP BY genre;
```
![image](https://github.com/user-attachments/assets/00aa62b9-0042-45bd-ac1f-b76e37d372f2)


#### 4. Display places that have more than 90,000 reviews.
```sql
SELECT * FROM ksa WHERE review_count > 10000;
```
![image](https://github.com/user-attachments/assets/e129eef8-186e-4620-96b7-fe1d3f1dd0d0)


#### 5. Find the highest-rated places, sorted in descending order.
```sql
SELECT * FROM ksa ORDER BY rating DESC;
```
![image](https://github.com/user-attachments/assets/583c3b10-e1ac-4154-97f9-37e11346fea2)


#### 6. Show places that have comments (where best_comment is not empty).
```sql
SELECT * FROM ksa WHERE best_comment IS NOT NULL;
```
![image](https://github.com/user-attachments/assets/7e644d43-27a8-467c-bc9d-368783eeaabe)


#### 7. Display places that are located in Saudi Arabia only.
```sql
SELECT * FROM ksa WHERE location LIKE '%Saudi Arabia%';
```
![image](https://github.com/user-attachments/assets/86b07edc-5f74-4b42-a2d0-3b24343b6c4d)


#### 8. Calculate the average rating for each genre.
```sql
SELECT genre, AVG(rating) AS avg_rating FROM ksa GROUP BY genre;
```
![image](https://github.com/user-attachments/assets/195b72f7-8240-4139-8851-eed7bfcca1fa)


#### 9. Show places that have the word "Theater" in their name.
```sql
SELECT * FROM ksa WHERE name LIKE '%Theater%';
```
![image](https://github.com/user-attachments/assets/6ae3c813-854d-4770-9af8-78772b07b7b3)


#### 10. Retrieve 5 random places from the table.
```sql
SELECT * FROM ksa ORDER BY RAND() LIMIT 5;
```
![image](https://github.com/user-attachments/assets/ae43702f-2b59-4668-a15d-6c8064d0bb2b)

#### 11. Create a function that returns the average rating of a given genre.

```sql
USE tradings;
DELIMITER //
CREATE FUNCTION get_avg_rating(genre_name VARCHAR(255)) 
RETURNS DECIMAL(5,2) DETERMINISTIC
BEGIN
    DECLARE avg_rating DECIMAL(5,2);
    
    SELECT AVG(rating) INTO avg_rating 
    FROM ksa 
    WHERE genre = genre_name;
    
    RETURN avg_rating;
END;
//
DELIMITER ;
SELECT get_avg_rating('Movie theater') AS average_rating;

```
<img width="831" alt="Screenshot 2025-02-11 at 12 27 56 PM" src="https://github.com/user-attachments/assets/d3be6558-c884-42cc-b9ec-81aff89bfccc" />

<img width="845" alt="Screenshot 2025-02-11 at 12 28 12 PM" src="https://github.com/user-attachments/assets/98998a0a-c4f2-4383-90e8-e2a9f7c600c1" />


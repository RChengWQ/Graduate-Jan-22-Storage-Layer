# 1. 
SELECT movie_name, release_date<br>
FROM movies;<br>

# 2. 
SELECT first_name, last_name<br>
FROM directors<br>
WHERE nationality = 'American';<br>

# 3. 
SELECT *<br>
FROM actors<br>
WHERE gender = 'M' AND date_of_birth > '1970-01-01';<br>

# 4.
SELECT movie_name<br>
FROM movies<br>
WHERE movie_length > 90 AND movie_lang = 'English';<br>

# 5.
SELECT movie_name, movie_lang<br>
FROM movies<br>
WHERE movie_lang IN ('English', 'Spanish', 'Korean');<br>

# 6.
SELECT first_name, last_name<br>
FROM actors<br>
WHERE last_name LIKE 'M%' AND date_of_birth BETWEEN '1940-01-01' AND '1969-12-31';<br>

# 7.
SELECT first_name, last_name<br>
FROM directors<br>
WHERE nationality IN ('British', 'French', 'German') AND date_of_birth BETWEEN '1950-01-01' AND '1980-12-31';<br>
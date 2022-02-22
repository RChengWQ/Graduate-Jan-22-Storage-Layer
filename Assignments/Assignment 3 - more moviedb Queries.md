# 1.
SELECT *<br>
FROM directors<br>
WHERE nationality = 'American'<br>
ORDER BY date_of_birth DESC;<br>

# 2.
SELECT DISTINCT nationality<br>
FROM directors;<br>

# 3.
SELECT first_name, last_name, date_of_birth<br>
FROM actors<br>
WHERE gender = 'F'<br>
ORDER BY date_of_birth ASC<br>
LIMIT 10;<br>

# 4.
SELECT *<br>
FROM movie_revenues<br>
WHERE international_takings IS NOT NULL<br>
ORDER BY international_takings DESC<br>
LIMIT 3;<br>

# 5.
SELECT CONCAT_WS(' ', first_name, last_name) as full_name<br>
FROM directors;<br>

# 6.
SELECT *<br>
FROM actors<br>
WHERE first_name IS NULL OR date_of_birth IS NULL;<br>

# 7.
SELECT COUNT(*)<br>
FROM actors<br>
WHERE date_of_birth > '1970-01-01';<br>

# 8.
SELECT MAX(domestic_takings), MIN(domestic_takings)<br>
FROM movie_revenues;<br>

# 9.
SELECT SUM(movie_length)<br>
FROM movies<br>
WHERE age_certificate = '15';<br>

# 10.
SELECT COUNT(*)<br>
FROM directors<br>
WHERE nationality = 'Japanese';<br>

# 11.
SELECT AVG(movie_length)<br>
FROM movies<br>
WHERE movie_lang = 'Chinese';<br>

# 12.
SELECT nationality, COUNT(nationality)<br>
FROM directors<br>
GROUP BY nationality;<br>

# 13.
SELECT SUM(movie_length), age_certificate, movie_lang<br>
FROM movies<br>
GROUP BY age_certificate, movie_Lang;<br>

# 14.
SELECT movie_lang, SUM(movie_length)<br>
FROM movies<br>
GROUP BY movie_lang<br>
HAVING SUM(movie_length) > 500;<br>


# 15.
SELECT first_name, last_name, movie_name, release_date<br>
FROM directors<br>
INNER JOIN movies ON directors.director_id = movies.director_id<br>
WHERE movie_lang IN ('Chinese', 'Korean', 'Japanese');<br>

# 16.
SELECT movie_name, release_date, international_takings, <br>
FROM movies<br>
INNER JOIN movie_revenues ON movies.movie_id = movie_revenues.movie_id<br>
WHERE movie_lang = 'English';<br>

# 17.
SELECT movie_name, domestic_takings, international_takings<br>
FROM movies<br>
INNER JOIN movie_revenues ON movies.movie_id = movie_revenues.movie_id<br>
WHERE movie_revenues.domestic_takings IS NULL OR movie_revenues.international_takings IS NULL<br>
ORDER BY movie_name ASC;<br>

# 18.
SELECT first_name, last_name, movie_name, age_certificate<br>
FROM directors<br>
LEFT JOIN movies ON directors.director_id = movies.director_id<br>
WHERE directors.nationality = 'British';<br>

# 19.
SELECT first_name, last_name, COUNT(*)<br>
FROM directors<br>
INNER JOIN movies ON directors.director_id = movies.director_id<br>
GROUP BY directors.director_id;<br>

# 20.
SELECT first_name, last_name, date_of_birth<br>
FROM directors<br>
UNION<br>
SELECT first_name, last_name, date_of_birth<br>
FROM actors<br>
ORDER BY date_of_birth ASC;<br>

# 21.
SELECT first_name, last_name<br>
FROM directors<br>
WHERE date_of_birth BETWEEN '1960-01-01' AND '1969-12-31'<br>
UNION<br>
SELECT first_name, last_name<br>
FROM actors<br>
WHERE date_of_birth BETWEEN '1960-01-01' AND '1969-12-31'<br>
ORDER BY last_name ASC;<br>
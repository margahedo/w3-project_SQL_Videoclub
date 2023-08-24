-- QUERY 1

select * from 
film;

-- Query 2

Select *
from film as f
left join language as l on l.language_id = f.language_id;

-- Query 3

Select *
from film as f
left join actor_per_film as apf on f.title = apf.title
left join category as c on apf.category_id = c.category_id;

--Query 4

SELECT apf.actor_actress_name, c.name
FROM film AS f
LEFT JOIN actor_per_film AS apf ON f.title = apf.title
LEFT JOIN category AS c ON apf.category_id = c.category_id
WHERE c.name = 'documentary';

--Query 5

Select c.name, avg(f.length) 
from film as f
left join actor_per_film as apf on f.title = apf.title
left join category as c on apf.category_id = c.category_id

group by c.name;
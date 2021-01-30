https://sqlzoo.net/wiki/The_JOIN_operation
- 1. SELECT matchid, player 
FROM goal
WHERE teamid = 'GER';
- 2.SELECT id, stadium, team1, team2 
FROM game
WHERE id = 1012;
- 3.SELECT player, teamid, stadium, mdate
  FROM game,goal
WHERE teamid = 'GER'
AND game.id = goal.matchid;
- 4.SELECT team1, team2, player 
FROM game JOIN goal ON (id = matchid)
WHERE player LIKE 'Mario%'
- 5.SELECT player, teamid, coach, gtime
  FROM goal JOIN eteam on teamid=id 
 WHERE gtime<=10 
 - 6.SELECT DISTINCT mdate, teamname 
FROM goal
JOIN game ON (goal.matchid =  game.id)
JOIN eteam ON  (goal.teamid = eteam.id)
WHERE eteam.coach = 'Fernando Santos' AND game.team1 = 'GRE'
- 7. SELECT player
FROM goal
JOIN game ON goal.matchid = game.id
WHERE stadium = 'National Stadium, Warsaw';
- 8. SELECT DISTINCT player
  FROM game JOIN goal ON matchid = id 
    WHERE (team1='GER' OR team2='GER')
AND goal.teamid <> 'GER';
- 9.SELECT teamname, COUNT(teamid)
  FROM eteam JOIN goal ON id=teamid
GROUP BY teamname;
- 10.SELECT stadium, COUNT(matchid) AS total_goal
FROM goal
JOIN game ON id = matchid
GROUP BY stadium
- 11.SELECT matchid, mdate, COUNT(matchid)
  FROM goal JOIN game ON matchid = id 
 WHERE (team1 = 'POL' OR team2 = 'POL')
GROUP BY matchid, mdate
 - 12.SELECT matchid, mdate, COUNT(matchid)
FROM goal
JOIN game ON matchid = id
WHERE teamid = 'GER'
GROUP BY matchid, mdate
https://sqlzoo.net/wiki/SELECT_basics
- 1. SELECT population FROM world
  WHERE name = 'Germany'
- 2. SELECT name, population FROM world
  WHERE name IN ('Sweden','Norway','Denmark');
- 3. SELECT name, area FROM world
  WHERE area BETWEEN 200000 AND 250000
https://sqlzoo.net/wiki/SELECT_from_WORLD_Tutorial
- 1. SELECT name, continent, population FROM world
- 2. SELECT name
  FROM world
 WHERE population > 200000000
- 3. SELECT name, (gdp/population) FROM world WHERE population > 200000000
- 4. SELECT name, population/1000000 FROM world WHERE continent = 'South America'
- 5. SELECT name, population FROM world WHERE name IN ('France', 'Germany', 'Italy')
- 6. SELECT name FROM world WHERE name LIKE '%United%'
- 7. SELECT name, population, area FROM world WHERE area > 3000000 OR population > 250000000
- 8. SELECT name, population, area FROM world WHERE (area > 3000000 AND population < 250000000) OR (population > 250000000 AND area < 3000000)
- 9. SELECT name, ROUND(population/1000000, 2) AS Population_million, ROUND(gdp/1000000000, 2) AS Population_billion FROM world WHERE continent = 'South America'
- 10. SELECT name, ROUND(gdp / population /1000, 0)*1000 FROM world WHERE gdp > 1000000000000;
- 11. SELECT name,capital 
  FROM world
 WHERE LEN(name) = LEN(capital)
 - 12. SELECT name, capital
FROM world WHERE LEFT(name,1) = LEFT(capital,1) AND name <> capital
- 13. SELECT name FROM world WHERE name LIKE '%a%' AND name LIKE '%e%' AND name LIKE '%i%' AND name LIKE '%o%' AND name LIKE '%u%' AND name NOT LIKE '% %'
https://sqlzoo.net/wiki/SELECT_from_Nobel_Tutorial
- 1. SELECT yr, subject, winner
  FROM nobel
 WHERE yr = 1950
 - 2. SELECT winner
  FROM nobel
 WHERE yr = 1962
   AND subject = 'Literature'
 - 3. SELECT yr, subject FROM nobel WHERE winner =  'Albert Einstein'
 - 4. SELECT winner FROM nobel WHERE yr >= 2000 AND subject = 'Peace'
 - 5. SELECT * FROM nobel WHERE subject = 'Literature' AND yr BETWEEN 1980 AND 1989
 - 6. SELECT * FROM nobel
 WHERE winner IN ('Theodore Roosevelt', 'Woodrow Wilson', 'Jimmy Carter', 'Barack Obama')
 - 7. SELECT winner FROM nobel WHERE winner LIKE 'John%'
 - 8. SELECT * FROM nobel WHERE (subject = 'Physics' AND yr = 1980) OR (subject = 'Chemistry' AND yr = 1984)
 - 9. SELECT * FROM nobel WHERE subject NOT IN ('Chemistry', 'Medicine') AND yr = 1980
 - 10. 


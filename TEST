SELECT *
FROM PortfolioProject..CovidDeaths -- table 1
ORDER BY 3, 4

SELECT *
FROM PortfolioProject..CovidVaccinations -- table 2
ORDER BY 3, 4

-- Select the Data that we are going to be using 

SELECT location, date, total_cases, new_cases, total_deaths, population
FROM PortfolioProject..CovidDeaths
ORDER BY 1, 2 -- let's keep this going because i don't like things not being organized 


-- looking at Total Cases VS Total Deaths
-- how many cases are there in this country and how many deaths do they have for their entire cases
-- so let's say they have a thousand people who have been diagnosed they had 10 people who died what's the percentage of people who died who had it
-- so now we want to know the percentage of people who are dying who actually get infected or who report being infected
-- Shows likelihood of dying if you contract covid in your country 

SELECT location, date, total_cases, total_deaths, (total_deaths /total_cases) * 100 AS DeathPercentage 
FROM PortfolioProject..CovidDeaths
WHERE location LIKE '%states%' 
	 OR 
	  location LIKE 'jor%'
ORDER BY 1, 2 DESC



-- looking at Total Cases VS Population
-- shows what percentage of population has got Covid 
-- it has gotten a test and it's been confirmed 
SELECT location, date, Population, total_cases, (total_cases /Population) * 100 AS PercentPopulationInfected 
FROM PortfolioProject..CovidDeaths
/*
WHERE location LIKE '%states%' 
	 OR 
	  location LIKE 'jor%'
*/
ORDER BY 1, 2 DESC


-- i'm really curious as to what countries have the highest infection rates compared to the population
-- looking at countries with Highest Infection Rate compared to Population

SELECT location, population, MAX(total_cases) AS HighestInfectionCount, MAX((total_cases /Population) * 100) AS PercentPopulationInfected
FROM PortfolioProject..CovidDeaths
/*
WHERE location LIKE '%states%' 
	 OR 
	  location LIKE 'jor%'
*/
GROUP BY location, population
ORDER BY 4 DESC










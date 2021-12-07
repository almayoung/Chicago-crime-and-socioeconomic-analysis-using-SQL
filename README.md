# Chicago Crime and Socioeconomic Analysis using SQL

## The Data
**[City of Chicago Crimes](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2/data)**

**[Chicago Socioecomic Indicators](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2/data)**

## **EXPLORING CHICAGO CRIME DATASET**


* **DISPLAY THE FIRST 10 RECORDS**

` SELECT TOP 10 * FROM [dbo].[Crimes];`

 ![image](https://user-images.githubusercontent.com/16657494/144781569-d7b4a7b1-ed24-4efa-b765-32ca938a5129.png)
  
* **DISPLAY ROBBERY THAT OCCURED IN AN APARTMENT**
```
SELECT [Primary Type], [Description], [Location Description]
FROM [dbo].[Crimes]
WHERE [Primary Type] = 'ROBBERY'
AND [Location Description] = 'APARTMENT';
```

![image](https://user-images.githubusercontent.com/16657494/144938683-e84a911a-ff78-4285-8ec7-88bee152ffbb.png)


* **DISPLAY UNIQUE CRIME IN THE PRIMARY TYPE COLUMN**

`SELECT DISTINCT [Primary Type] FROM [dbo].[Crimes];`

![image](https://user-images.githubusercontent.com/16657494/144782583-78e35d28-0c87-419a-b9f1-1fc8ecec4374.png)

* **HOW MANY BURGLARIES WERE REPORTED IN 2018?**
```
SELECT COUNT(*) AS Total_Burglaries
FROM [dbo].[Crimes]
WHERE [Primary Type] = 'BURGLARY';
```
![image](https://user-images.githubusercontent.com/16657494/144782801-2372675c-352d-40bb-b604-2a44789870eb.png)

* **HOW MANY HOMICIDES WERE REPORTED IN 2018?**
```
SELECT COUNT(*) AS Total_Homicides
FROM [dbo].[Crimes]
WHERE [Primary Type] = 'HOMICIDE';
```
![image](https://user-images.githubusercontent.com/16657494/144782936-5bdfa093-54f3-4f05-b1cb-fb51e8317b2a.png)

* **WHAT TYPES OF CRIMES ARE COMMITED MOST FREQUENTLY?**
```
SELECT [Primary Type], COUNT(*) AS Total_Crimes
FROM [dbo].[Crimes]
GROUP BY [Primary Type]
ORDER BY Total_Crimes DESC;
```
![image](https://user-images.githubusercontent.com/16657494/144939434-7a656c08-e70b-42f8-a70c-aa24277a83b2.png)

* **WHERE ARE THE FREQUENT CRIMES BEING COMMITTED?**
```
SELECT [Location Description], COUNT(*) AS Number_of_Crimes
FROM [dbo].[Crimes]
GROUP BY [Location Description]
ORDER BY Number_of_Crimes DESC;
```

![image](https://user-images.githubusercontent.com/16657494/144947883-44765cf0-1130-4558-b867-40fc455a81cc.png)

* **HOW MANY CRIMES INVOLVE AN ARREST?**
```
SELECT COUNT(ARREST) AS Arrested
FROM [dbo].[Crimes]
WHERE Arrest = 'TRUE';
```
![image](https://user-images.githubusercontent.com/16657494/144948159-72bc4f7c-1932-4423-a18c-d1c1deae7a3d.png)

* **HOW MANY CRIMES INVOLVE WITH NO ARREST?**
```
SELECT COUNT(ARREST) AS Not_Arrested
FROM [dbo].[Crimes]
WHERE Arrest = 'FALSE';
```

![image](https://user-images.githubusercontent.com/16657494/144948277-66e6a59e-f357-4119-9919-3afcc18bc936.png)

* **WHICH UNIQUE TYPES OF CRIMES HAVE BEEN RECORDED AT GAS STATION LOCATIONS?**
```
SELECT DISTINCT [Primary Type]
FROM [dbo].[Crimes]
WHERE [Location Description] = 'GAS STATION';
```

![image](https://user-images.githubusercontent.com/16657494/144948467-1f49beb6-8727-409c-97c5-56c4a7346ea5.png)

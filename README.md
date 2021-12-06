# Chicago Crime and Socioeconomic Analysis using SQL

## The Data
**[City of Chicago Crimes](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2/data)**

**[Chicago Socioecomic Indicators](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2/data)**

## **EXPLORING CHICAGO CRIME DATASET**


* **DISPLAY THE FIRST 10 RECORDS**

` SELECT TOP 10 * FROM [dbo].[Crimes];`

 ![image](https://user-images.githubusercontent.com/16657494/144781569-d7b4a7b1-ed24-4efa-b765-32ca938a5129.png)
  
* **DISPLAY ROBBERY THAT OCCURED IN THE STREET**
```
SELECT [Primary Type], [Description], [Location Description]
FROM [dbo].[Crimes]
WHERE [Primary Type] = 'ROBBERY'
AND [Location Description] = 'STREET';
```

![image](https://user-images.githubusercontent.com/16657494/144782143-a225cb46-98a0-471e-90b1-d1de747314f8.png)




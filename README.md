# Power BI Projects

This repository contains my Power BI projects, which focuses on analyzing and visualizing data using Microsoft Power BI Query Editor for data cleaning, and DAX calculations.

## Contoso Sales DAX Project 📈

The main objective of this project is to provide a detailed analysis of Contoso's company sales, using more than **60 DAX calculations** to obtain key information on financial performance and trends over time.

This is my **largest** data analysis project with Power BI ☑️📊. You can access the project through the following link:
https://bit.ly/ProyectoContosoSalesDAXFabianaRodriguez

- **About Contoso dataset:**

  This is a fictitious company frequently used in Microsoft product demonstrations for simulated sales and business transactions.

  This database generally includes tables such as DimProduct (product information), DimCustomer (customer information), DimDate (date information), and FactSales (sales records), among others.

### 🟢 Analysis Performed 

1. **Project Overview: 👀** General visualization of the sales data.

2. **Revenue Variation: 💸** Comparison of revenues compared to the same month of the previous year.

3. **Rankings: 🥇** Sales ranking by continent and store type and identification of the products that generate the most profit.

4. **Returns: ⬅️** Analysis of returns by continent and product category, and calculations of the average unit price of returned products between 2007-2009.

5. **Unit Price Adjustment Forecast: 📈** Evaluation of how adjusting the unit price of products in a specific range (0.3 - 0.4) would affect the 2010 profit forecast.

![1](https://github.com/FabianaRod/PowerBiProjects/assets/155020943/79514a23-3e63-4d54-9a46-4483ba78e245)

###
![2](https://github.com/FabianaRod/PowerBiProjects/assets/155020943/472450f5-ff4f-4f67-bd2f-50bfd63abd59)


### 🔵 Calculations Performed 

The following are some of the key calculations performed in the project using the DAX formula language in which I performed almost **60 different calculations** by applying the following:

**1. Date & Time Functions**
  - **Año:** `YEAR(DimCalendar[DateKey])`
  - **Mes:** `MONTH(DimCalendar[DateKey])`
  - **Dia:** `DAY(DimCalendar[DateKey])`
  - **Trimestre:** `QUARTER(DimCalendar[DateKey])`
  - **SemanaAño:** `WEEKNUM(DimCalendar[DateKey],2)`
  - **Dia Semana:** `WEEKDAY(DimCalendar[DateKey],2)`
  - **DiasPromo:** `DATEDIFF(DimPromotion[StartDate], DimPromotion[EndDate], DAY)`

**2. Conditional and Logical Functions**
  - **Devolucion:** `IF(FactSales[ReturnQuantity]>0,"Si","No")`
  - **Tipo Venta:** `IF(FactSales[SalesQuantity]>10,"Mayoreo","Menudeo")`
  - **Tipo Devolucion:** `IF(FactSales[ReturnQuantity]=0,BLANK(),IF(FactSales[ReturnQuantity]=1,"Unica","Multiple"))`
  - **Fin Semana:** `IF(DimCalendar[Dia Semana] in {6,7}, "Fin de semana", "Dia laboral")`
  - **Descuento por Mayor:** `IF(FactSales[Tipo Venta]= "Por Mayor" && FactSales[channelKey] = 1 &&  FactSales[PromotionKey] = 1, 0.05, 0)`

**3. Text Functions**
  - **Ubicación Completa:** `DimGeography[RegionCountryName] & ", " & DimGeography[ContinentName]`
  - **Trimestre:** `"Trimestre " & QUARTER(DimCalendar[DateKey])`
  - **Mes Corto:** `LEFT(DimCalendar[CalendarMonthLabel],1)`
  - **Dia Txt:** `FORMAT(DimCalendar[DateKey], "DDDD")`
  - **Tienda:** `SUBSTITUTE(DimStores[StoreName], "Store", BLANK())`

**4. Measures**
  - **Cantidad Ventas:** `SUM(FactSales[SalesQuantity])`
  - **Cantidad Devoluciones:** `SUM(FactSales[ReturnQuantity])`
  - **Cantidad Total:** `[Cantidad Ventas] - [Cantidad Devoluciones]`
  - **Ratio Devoluciones:** `DIVIDE([Cantidad Devoluciones],[Cantidad Ventas],0)`
  - **PU Promedio:** `AVERAGE(DimProduct[UnitPrice])`

... and many more.

This is only a summary of the calculations performed in the project. 

## Super Bowl Stats 1967 - 2020 

In this repository you can also find my (smaller) 👌 Super Bowl Project. You can take a look here: https://bit.ly/3vvQgpG 👀 and also download the raw file.

This one has allowed me to apply the main DAX functions and tools such as concatenation, SWITCH function and its respective ELSE, calculated columns, TOTALYTD function, creation of a Calendar Table and COUNTX function.

  **This is an overview:** 😎



![image](https://github.com/FabianaRod/PowerBiProjects/assets/155020943/7b4232e3-39af-4bda-ae5e-a06317cb40c2)



I'll be uploading some other projects in the following weeks.

Thanks fo reading 💙


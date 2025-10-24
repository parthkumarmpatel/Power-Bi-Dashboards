
# 🧠 Power BI DAX Functions – Complete Cheat Sheet

This is a **full DAX functions cheat sheet** for Power BI interviews. Functions are categorized by type with **example** and **context**.

---

## 🔹 1️⃣ Aggregation Functions
| Function | Description | Example | Context |
|-----------|--------------|----------|----------|
| SUM() | Adds numeric values. | `SUM(Sales[Amount])` | Filter |
| AVERAGE() | Mean of a column. | `AVERAGE(Sales[Profit])` | Filter |
| COUNT() | Count numeric values. | `COUNT(Sales[Quantity])` | Filter |
| COUNTA() | Count non-blank values. | `COUNTA(Sales[Customer])` | Filter |
| COUNTROWS() | Count rows in a table. | `COUNTROWS(Sales)` | Filter |
| DISTINCTCOUNT() | Count unique values. | `DISTINCTCOUNT(Sales[CustomerID])` | Filter |
| MIN() / MAX() | Minimum / Maximum value. | `MAX(Sales[Revenue])` | Filter |
| SUMX() | Iterate over table rows and sum. | `SUMX(Sales, Sales[Qty]*Sales[Price])` | Row + Filter |
| AVERAGEX() | Iterate over table rows and average. | `AVERAGEX(Sales, Sales[Profit])` | Row + Filter |
| MAXX(), MINX(), COUNTX() | Iterators for max/min/count. | `MAXX(Products, Products[Price])` | Row + Filter |

---

## 🔹 2️⃣ Filter / Context Modifier Functions
| Function | Description | Example | Context |
|-----------|--------------|----------|----------|
| CALCULATE() | Change or add filter context. | `CALCULATE(SUM(Sales[Revenue]), Sales[Region]="East")` | Filter Modifier |
| FILTER() | Return filtered table. | `FILTER(Sales, Sales[Revenue]>1000)` | Filter Modifier |
| ALL() | Remove all filters. | `ALL(Sales)` | Filter Modifier |
| ALLEXCEPT() | Remove filters except specified columns. | `ALLEXCEPT(Sales, Sales[Category])` | Filter Modifier |
| ALLSELECTED() | Keeps only report-level filters. | `ALLSELECTED(Sales)` | Filter Modifier |
| REMOVEFILTERS() | Remove filters from column/table. | `REMOVEFILTERS(Sales[Region])` | Filter Modifier |
| KEEPFILTERS() | Apply filter without overriding existing filters. | `CALCULATE(SUM(Sales[Revenue]), KEEPFILTERS(Sales[Region]="West"))` | Filter Modifier |
| VALUES() | Returns unique values of a column. | `VALUES(Sales[Category])` | Filter Context |
| DISTINCT() | Returns distinct values of a column. | `DISTINCT(Sales[ProductID])` | Filter Context |

---

## 🔹 3️⃣ Row Context / Iterator Functions
| Function | Description | Example | Context |
|-----------|--------------|----------|----------|
| RELATED() | Fetch value from related table. | `RELATED(Product[Category])` | Row |
| RELATEDTABLE() | Returns related rows. | `COUNTROWS(RELATEDTABLE(Orders))` | Row |
| EARLIER() | Access previous row context. | `Sales[Profit] - EARLIER(Sales[Profit])` | Row |
| ADDCOLUMNS() | Add calculated column to table. | `ADDCOLUMNS(Sales, "Profit", Sales[Revenue]-Sales[Cost])` | Row |
| SUMX(), AVERAGEX(), MAXX(), MINX(), COUNTX() | Iterate table and aggregate. | `SUMX(Sales, Sales[Qty]*Sales[Price])` | Row + Filter |
| VAR / RETURN | Define variables for reuse. | `VAR Total = SUM(Sales[Amount]) RETURN Total*0.1` | Row / Filter |
| GENERATE() | Row-by-row table combination. | `GENERATE(Products, Sales)` | Row / Table |

---

## 🔹 4️⃣ Date & Time Intelligence Functions
| Function | Description | Example | Context |
|-----------|--------------|----------|----------|
| TODAY(), NOW() | Current date/time. | `TODAY()` | None |
| YEAR(), MONTH(), DAY() | Extract components. | `YEAR(Sales[Date])` | Row |
| DATEDIFF() | Difference between two dates. | `DATEDIFF(Sales[OrderDate], Sales[ShipDate], DAY)` | Row |
| DATEADD() | Shift date by interval. | `DATEADD(Dates[Date], -1, MONTH)` | Date Intelligence |
| SAMEPERIODLASTYEAR() | Compare same period last year. | `CALCULATE(SUM(Sales[Revenue]), SAMEPERIODLASTYEAR(Dates[Date]))` | Date Intelligence |
| PREVIOUSMONTH(), NEXTMONTH() | Previous / Next month value. | `PREVIOUSMONTH(Dates[Date])` | Date Intelligence |
| TOTALYTD(), TOTALQTD(), TOTALMTD() | YTD / QTD / MTD aggregation. | `TOTALYTD(SUM(Sales[Revenue]), Dates[Date])` | Date Intelligence |
| DATESINPERIOD() | Dates within specified period. | `DATESINPERIOD(Dates[Date], MAX(Dates[Date]), -30, DAY)` | Date Intelligence |
| STARTOFYEAR(), ENDOFYEAR(), ENDOFMONTH() | Return boundary date. | `ENDOFMONTH(Dates[Date])` | Date Intelligence |

---

## 🔹 5️⃣ Text / String Functions
| Function | Description | Example | Context |
|-----------|--------------|----------|----------|
| UPPER(), LOWER() | Convert to upper/lower case. | `UPPER(Customer[Name])` | Row |
| CONCATENATE() | Join two text values. | `CONCATENATE(Customer[FName], Customer[LName])` | Row |
| CONCATENATEX() | Join multiple rows into text. | `CONCATENATEX(Products, Products[Name], ", ")` | Row + Filter |
| LEFT(), RIGHT(), MID() | Extract substring. | `LEFT(Customer[Name], 3)` | Row |
| LEN() | Text length. | `LEN(Customer[Name])` | Row |
| TRIM() | Remove spaces. | `TRIM(Customer[Name])` | Row |
| SUBSTITUTE(), REPLACE() | Replace text. | `SUBSTITUTE(Customer[City], "NY", "New York")` | Row |
| SEARCH(), FIND() | Locate substring. | `SEARCH("A", Customer[Name])` | Row |

---

## 🔹 6️⃣ Logical / Conditional Functions
| Function | Description | Example | Context |
|-----------|--------------|----------|----------|
| IF() | Conditional logic. | `IF(Sales[Profit]>1000, "High", "Low")` | Row |
| SWITCH() | Multiple conditions. | `SWITCH(TRUE(), Sales[Profit]>1000,"High",Sales[Profit]>500,"Med","Low")` | Row |
| AND(), OR(), NOT() | Logical operations. | `AND(Sales[Qty]>10, Sales[Profit]>100)` | Row |
| ISBLANK() | Check for blank. | `IF(ISBLANK(Sales[Profit]),0,Sales[Profit])` | Row |

---

## 🔹 7️⃣ Information Functions
| Function | Description | Example | Context |
|-----------|--------------|----------|----------|
| HASONEVALUE() | True if only one value exists. | `HASONEVALUE(Customer[Region])` | Filter |
| ISFILTERED() | True if column is filtered. | `ISFILTERED(Sales[Region])` | Filter |
| ISCROSSFILTERED() | True if cross-filter applied. | `ISCROSSFILTERED(Customer[CustomerID])` | Filter |
| SELECTEDVALUE() | Returns single value or alternate. | `SELECTEDVALUE(Customer[Region], "Multiple")` | Filter |

---

## 🔹 8️⃣ Table / Relational Functions
| Function | Description | Example | Context |
|-----------|--------------|----------|----------|
| SUMMARIZE() | Create summary table. | `SUMMARIZE(Sales, Sales[Category], "Total", SUM(Sales[Revenue]))` | Filter |
| UNION(), INTERSECT(), EXCEPT() | Combine tables. | `UNION(Table1, Table2)` | Table |
| CROSSJOIN() | Cartesian join. | `CROSSJOIN(Product, Customer)` | Table |

---

## 🔹 9️⃣ Ranking / Statistical Functions
| Function | Description | Example | Context |
|-----------|--------------|----------|----------|
| RANKX() | Rank values. | `RANKX(ALL(Sales), SUM(Sales[Revenue]))` | Filter |
| TOPN() | Top N rows. | `TOPN(5, Sales, Sales[Revenue], DESC)` | Filter |
| MEDIANX() | Median value. | `MEDIANX(Sales, Sales[Revenue])` | Row + Filter |
| PERCENTILEX.INC() | Percentile calculation. | `PERCENTILEX.INC(Sales, Sales[Revenue], 0.9)` | Row + Filter |

---

## 🔹 🔟 Parent-Child / Hierarchy Functions
| Function | Description | Example | Context |
|-----------|--------------|----------|----------|
| PATH() | Create hierarchy path. | `PATH(Employee[ID], Employee[ManagerID])` | Row |
| PATHITEM() | Extract item from path. | `PATHITEM(EmployeePath, 2)` | Row |
| PATHLENGTH() | Number of levels in path. | `PATHLENGTH(EmployeePath)` | Row |

---

✅ **Interview Tip:** Focus on **CALCULATE + FILTER + ALL + Time Intelligence** with row vs. filter context; that’s the most common scenario in dashboards.


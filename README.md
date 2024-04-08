# Home_Sales
## Preparing the data
* Read the home_sales_revised.csv data in the starter code into a Spark DataFrame.
* Create a temporary table called home_sales.

## Answer the following questions using SparkSQL:
* What is the average price for a four-bedroom house sold for each year? Round off your answer to two decimal places.
+--------------------+----------+
|round(avg(price), 2)|year(date)|
+--------------------+----------+
|            300263.7|      2019|
|           298353.78|      2020|
|           301819.44|      2021|
|           296363.88|      2022|
+--------------------+----------+

* What is the average price of a home for each year the home was built, that has three bedrooms and three bathrooms? Round off your answer to two decimal places.
+--------------------+----------+
|round(avg(price), 2)|date_built|
+--------------------+----------+
|           292859.62|      2010|
|           291117.47|      2011|
|           293683.19|      2012|
|           295962.27|      2013|
|           290852.27|      2014|
|            288770.3|      2015|
|           290555.07|      2016|
|           292676.79|      2017|
+--------------------+----------+

* What is the average price of a home for each year the home was built, that has three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet? Round off your answer to two decimal places.
+--------------------+----------+
|round(avg(price), 2)|date_built|
+--------------------+----------+
|           285010.22|      2010|
|           276553.81|      2011|
|           307539.97|      2012|
|           303676.79|      2013|
|           298264.72|      2014|
|           297609.97|      2015|
|            293965.1|      2016|
|           280317.58|      2017|
+--------------------+----------+

* What is the average price of a home per "view" rating having an average home price greater than or equal to $350,000? Determine the run time for this query, and round off your answer to two decimal places.
+----+--------------------+
|view|round(avg(price), 2)|
+----+--------------------+
|  51|           788128.21|
|  54|           798684.82|
|  69|           750537.94|
|  87|           1072285.2|
|  73|           752861.18|
|  64|           767036.67|
|  59|            791453.0|
|  85|          1056336.74|
|  52|           733780.26|
|  71|            775651.1|
|  98|          1053739.33|
|  99|          1061201.42|
|  96|          1017815.92|
| 100|           1026669.5|
|  70|           695865.58|
|  61|           746877.59|
|  75|          1114042.94|
|  78|          1080649.37|
|  89|          1107839.15|
|  77|          1076205.56|
+----+--------------------+

## Further Steps
* Cache your temporary table home_sales.

* Check if your temporary table is cached.

* Using the cached data, run the last query that calculates the average price of a home per "view" rating having an average home price greater than or equal to $350,000. Determine the runtime and compare it to uncached runtime.
original runtime: --- 1.32511568069458 seconds ---
uncached runtime: --- 0.9027597904205322 seconds ---
the cached runtime of 0.9027597904205322 was shorter than the original runtime of 1.32511568069458 seconds by *0.42235589027404785* seconds

* Partition by the "date_built" field on the formatted parquet home sales data.

* Create a temporary table for the parquet data.

* Run the last query that calculates the average price of a home per "view" rating having an average home price greater than or equal to $350,000. Determine the runtime and compare it to uncached runtime.
the cached runtime of 0.9027597904205322 was shorter than the partitioned runtime of 1.452556848526001 seconds by *0.5497970581054688* seconds

* Uncache the home_sales temporary table.

* Verify that the home_sales temporary table is uncached using PySpark.

* Download your Home_Sales.ipynb file and upload it into your "Home_Sales" GitHub repository.
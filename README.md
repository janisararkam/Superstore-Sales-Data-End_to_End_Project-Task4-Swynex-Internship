# Superstore-Sales-Data-End_to_End_Project-Task4-Swynex-Internship
End-to-end Data Analytics project covering data cleaning, exploratory data analysis and interactive Power BI dashboard.

                                                  Data Cleaning & Preparation

The project started with a **Superstore Sales dataset** containing **9,800 records and 18 columns**.
The dataset includes information about orders, customers, shipping, locations, products, categories, and sales. 
Key fields include Order ID, Order Date, Ship Date, Ship Mode, Customer ID, Segment, Country, City, State, Postal Code, Region, Product ID, Category, Sub-Category, Product Name, and Sales.

The dataset was loaded into Python using **Pandas** for data inspection and cleaning.

### Data Cleaning Steps

#### 1. Initial Data Inspection
The dataset was first inspected using the first and last records, dataset shape, column names, data types, and information about missing values. The initial dataset contained 9,800 rows and 18 columns.

#### 2. Date and Data Type Formatting
The `Order Date` and `Ship Date` columns were converted from text format into proper datetime format using the `DD/MM/YYYY` format.

The `Postal Code` column was converted from `float64` to nullable integer (`Int64`) format to represent postal codes appropriately.

#### 3. Missing Value Handling
A missing-value check identified **11 missing values in the Postal Code column**. These records belonged to **Burlington, Vermont**, and the missing postal codes were filled with **5401**. After this step, no missing values remained in the dataset. 

#### 4. Column Name Standardization
Column names containing spaces or special characters were standardized using underscores. For example:

- `Row ID` → `Row_ID`
- `Order ID` → `Order_ID`
- `Order Date` → `Order_Date`
- `Ship Date` → `Ship_Date`
- `Customer ID` → `Customer_ID`
- `Postal Code` → `Postal_Code`
- `Product ID` → `Product_ID`
- `Sub-Category` → `Sub_Category`
- `Product Name` → `Product_Name`

This made the column names easier to use in Python and subsequent analysis.

#### 5. Categorical Data Validation
Categorical columns such as Ship Mode, Segment, Country, Region, Category, and Sub-Category were checked for unexpected values.

The validation confirmed the expected categories and values, including the three product categories — Furniture, Office Supplies, and Technology — and the four regions — South, West, Central, and East.

#### 6. ID and Sales Validation
Important identifier columns were checked for invalid or missing values.

- Row IDs less than or equal to zero: **0**
- Missing Order IDs: **0**
- Missing Customer IDs: **0**
- Missing Product IDs: **0**
- Postal Codes less than or equal to zero: **0**
- Missing Postal Codes after cleaning: **0**
- Sales values less than or equal to zero: **0**

These checks confirmed that the key identifiers and Sales field contained valid values.

#### 7. Sales Outlier Analysis
The Interquartile Range (IQR) method was used to identify statistical outliers in the Sales column.

The analysis identified **1,145 potential outlier records**, with an upper limit of approximately **500.64**. These records were inspected further rather than automatically removed, as they represented high-value sales transactions in the dataset.

#### 8. Date Validation
The date ranges were checked to understand the coverage of the dataset:

- Order Date: **03 January 2015 – 30 December 2018**
- Ship Date: **07 January 2015 – 05 January 2019**

The relationship between Order Date and Ship Date was also validated, and there were **0 records where Ship Date occurred before Order Date**.

#### 9. Duplicate Validation
Duplicate records were checked using both the complete dataset and the Row ID column.

- Duplicate complete rows: **0**
- Duplicate Row IDs: **0**

This confirmed that no duplicate records required removal. 

### Final Output

After completing the cleaning and validation process, the cleaned dataset was exported as:

Cleaned_Superstore_cleaned_Data_Set.csv

This cleaned dataset was then ready for the next stage of the project — **Exploratory Data Analysis (EDA)**.










                                                      Exploratory Data Analysis (EDA)

After completing the data cleaning and preparation process, the cleaned Superstore Sales dataset was analyzed in **Microsoft Excel** to identify sales patterns, trends, and business performance across different dimensions.

The EDA was performed using sales aggregations and comparisons across categories, sub-categories, regions, shipping modes, customer segments, time periods, states, cities, products, and customers.

### Analysis Performed

#### 1. Category-wise Sales Analysis
Sales were analyzed across the three main product categories:

- **Technology:** ₹8,27,455.87
- **Furniture:** ₹7,28,658.58
- **Office Supplies:** ₹7,05,422.33

Technology generated the highest total sales among the three categories.

#### 2. Sub-Category-wise Sales Analysis
Sales were further analyzed at the sub-category level to identify the strongest-performing product groups.

The analysis showed that **Phones** was the highest-selling sub-category with sales of **₹3,27,782.45**, followed by **Chairs** with **₹3,22,822.73**.

#### 3. Region-wise Sales Analysis
Sales performance was compared across the four regions:

- **West:** ₹7,10,219.68
- **East:** ₹6,69,518.73
- **Central:** ₹4,92,646.91
- **South:** ₹3,89,151.46

The **West region** recorded the highest total sales.

#### 4. Ship Mode-wise Sales Analysis
Sales were analyzed across different shipping modes.

**Standard Class** generated the highest sales with **₹13,40,831.31**.

#### 5. Segment-wise Sales Analysis
Customer sales were analyzed across the Consumer, Corporate, and Home Office segments.

The **Consumer segment** recorded the highest sales at **₹11,48,060.53**.

#### 6. Yearly Sales Analysis
Year-wise sales were analyzed to understand the overall sales trend from 2015 to 2018.

- **2015:** ₹4,79,856.21
- **2016:** ₹4,59,436.01
- **2017:** ₹6,00,192.55
- **2018:** ₹7,22,052.02

**2018 recorded the highest yearly sales** during the analyzed period.

#### 7. Monthly Sales Analysis
Monthly sales were analyzed to identify high-performing months.

The highest monthly sales were recorded in:

- **November:** ₹3,50,161.71
- **December:** ₹3,21,480.17

#### 8. Region & Category-wise Analysis
Sales were also analyzed by combining **Region and Category** to understand how different product categories performed within each region.

#### 9. Segment & Category-wise Analysis
A combined analysis of **Customer Segment and Category** was performed to understand category performance across Consumer, Corporate, and Home Office customers.

#### 10. State-wise and City-wise Analysis
Sales were analyzed at both state and city levels to identify geographic sales distribution.

#### 11. Product and Customer Analysis
The EDA also included:

- Product Name-wise Sales Analysis
- Customer Name-wise Sales Analysis

These analyses helped examine sales contribution at individual product and customer levels.

### EDA Outcome

The Excel-based EDA provided a detailed view of the Superstore's sales performance across **products, categories, regions, customers, shipping modes, locations, and time periods**.

The findings from this analysis were then used to identify key business insights and support the development of the **interactive Power BI dashboard** in the next stage of the project.













                                                         Interactive Power BI Dashboard
   
After completing the data cleaning and exploratory data analysis, the cleaned Superstore Sales dataset was imported into **Microsoft Power BI** to create an interactive dashboard for visual analysis and business reporting.

The dashboard was designed to provide a clear view of sales performance across different time periods, product categories, regions, shipping modes, customer segments, products, states, and cities.

### Dashboard Title

**Superstore Sales Interactive Dashboard**

### Key Performance Indicators

The dashboard includes KPI cards to provide a quick overview of important sales and customer/order metrics:

- **Total Sales** – Displays the overall sales generated from the dataset.
- **Order Metric** – Provides an order-level summary from the sales data.
- **Unique Customer** – Displays the customer-level metric for the dataset.

### Sales Analysis Visuals

The dashboard contains multiple visuals to analyze sales performance from different perspectives:

1. **Sales by Year**  
   A time-based visualization showing how sales perform across different years.

2. **Sales by Category**  
   Compares sales across the major product categories such as Technology, Furniture, and Office Supplies.

3. **Sales by Sub-Category**  
   Provides a more detailed view of sales performance across individual product sub-categories.

4. **Sales by Region**  
   Compares sales performance across different geographical regions.

5. **Sales by Ship Mode**  
   Analyzes sales based on the shipping modes used for orders.

6. **Sales by Segment**  
   Shows sales distribution across different customer segments.

7. **Sales by Product**  
   Provides product-level sales analysis to identify products contributing to overall sales.

8. **Sales by State**  
   Allows comparison of sales performance across individual states.

9. **Sales by City**  
   Provides a city-level view of sales performance.

10. **Monthly Sales Trend**  
    A line chart showing the movement of sales across months, helping identify changes and patterns in monthly sales performance.

### Interactive Filters

Two slicers were added to make the dashboard interactive:

- **Year Slicer**
- **Month Slicer**

These filters allow users to select specific years and months and analyze the corresponding sales data across the dashboard visuals.

### Dashboard Objective

The main objective of the Power BI dashboard is to transform the analyzed sales data into an interactive and easy-to-understand business reporting interface. Users can explore sales performance across time, products, customers, shipping modes, and geographical dimensions using the available visuals and filters.

The dashboard therefore acts as the final visualization layer of this project, connecting the cleaned dataset and Excel-based EDA with an interactive business dashboard.




















## Key Business Insights

The combined analysis of the cleaned dataset, Excel EDA, and Power BI dashboard produced the following key business insights:

- **Technology** was the highest-selling category, generating total sales of **₹8,27,455.87**.
- **West** was the highest-selling region, with total sales of **₹7,10,219.68**.
- **Standard Class** generated the highest sales among shipping modes, with total sales of **₹13,40,831.31**.
- **Consumer** was the highest-selling customer segment, generating **₹11,48,060.53** in sales.
- **Phones** was the highest-selling sub-category with sales of **₹3,27,782.45**, followed by **Chairs** with **₹3,22,822.73**.
- **2018** recorded the highest yearly sales at **₹7,22,052.02**, while **2015** recorded **₹4,79,856.21**.
- **November** recorded the highest monthly sales at **₹3,50,161.71**, followed by **December** at **₹3,21,480.17**.

These findings provide a clear overview of the strongest-performing categories, regions, customer segments, shipping modes, products, and time periods in the dataset.

##  Tools & Technologies

The project was completed using the following tools and technologies:

- **Python** – Used for data inspection, cleaning, validation, data type handling, missing-value treatment, and data quality checks.
- **Pandas** – Used for working with and preparing the Superstore Sales dataset.
- **Microsoft Excel** – Used for Exploratory Data Analysis (EDA), including category, sub-category, region, segment, shipping mode, yearly, monthly, state, city, product, and customer-level analysis.
- **Microsoft Power BI** – Used to create the interactive sales dashboard and visualize key business metrics and trends.
- **Power BI Slicers** – Used to provide interactive Year and Month filtering.
- **GitHub** – Used to organize and present the complete project, including the cleaning work, EDA, dashboard, and documentation.
- **Jupyter Notebook** – Used for the Python-based data cleaning and preparation process.

##  Conclusion

This project provided an end-to-end data analytics workflow using a Superstore Sales dataset.

The project started with **data cleaning and preparation**, where the dataset was inspected, data types were standardized, missing values were handled, column names were cleaned, duplicate and data-quality checks were performed, and potential sales outliers were analyzed.

The cleaned dataset was then analyzed in **Microsoft Excel** to identify sales patterns across categories, sub-categories, regions, shipping modes, customer segments, years, months, states, cities, products, and customers.

Finally, the analysis was transformed into an **interactive Power BI dashboard**, allowing users to explore sales performance through multiple visualizations and Year and Month slicers.

Overall, this project demonstrates the complete process of transforming raw sales data into meaningful analysis and an interactive business reporting dashboard using **Python, Excel, and Power BI**.






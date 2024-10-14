# Bookstore Data Visualization With Tableau

This project involves analyzing data from a fictitious bookstore set in the future (January 1, 2194), using Tableau for exploratory data analysis. Data from two Excel files, **A6_Bookshop.xlsx** and **A6_BookshopLibraries.xlsx**, are connected in Tableau through a series of joins, unions, and relationships to create a comprehensive data model. The goal is to answer a set of 14 exploratory business questions regarding sales, checkouts, book ratings, author details, and more.

## Project Overview

### Data Model:
The data model connects various tables through:
- **Inner Join** between the `Book` and `Info` tables, with the condition `[BookID1] + [BookID2] = BookID`.
- **Union** between the `Sales Q1`, `Sales Q2`, `Sales Q3`, and `Sales Q4` tables for sales data.
- **Relationships** connecting other tables based on `BookID` and calculated fields, as needed.

This structure allows us to analyze trends and answer specific questions related to sales, ratings, authorship, and other bookstore-related metrics.

### Exploratory Analysis Questions:
1. **Book Popularity**: Identify the most and least popular books based on sales, checkouts, and ratings.
2. **Author Ages**: Determine the youngest debut author and the oldest.
3. **Publishing Specialization**: Do any publishing houses seem to specialize in specific genres or formats?
4. **Edition Gap**: What was the longest time between editions of the same book?
5. **Seasonal Sales Trends**: Are there any seasonal patterns for sales and checkouts?
6. **Correlations**: Explore correlations between checkouts, print run size, book ratings, and sales volume.
7. **Writing Time vs. Success**: Do authors who spend more time writing have more successful books or higher page counts?
8. **Publishing Trends**: When are most books published? Are there any anomalies?
9. **Genre, Format, and Price Trends**: Analyze trends related to book genre, format, and pricing.
10. **Rating Distributions**: Explore how book ratings are distributed and whether they vary by book or genre.
11. **Sales Price Calculation**: Create a calculated field to account for discounts on sales prices.
12. **Pareto Principle**: Do sales follow the 80/20 rule (Pareto Principle)?
13. **Discount Patterns**: Identify any patterns in the discounts provided.
14. **Data Quality**: Do any tables seem to have dirty data, especially in relation to authors?

## Key Visualizations
Each of the above questions is addressed through individual Tableau worksheets, where visualizations such as text tables, bar charts, calculated fields, and others help to answer the questions. Calculations and filters are applied where necessary to refine the data.

### Notable Calculations:
- **Author Age**: `Datediff(‘year’, date("01-01-2194"), [Birthday])`
- **Time Between Editions**: `DateDiff(Max(Publication Date), Min(Publication Date))`
- **Sales Price**: `Sales price = [Price] – IFNULL([Price]*[Discount],0)`

## Files in Repository
- **A6_Bookshop.xlsx**: Contains book details and quarterly sales data.
- **A6_BookshopLibraries.xlsx**: Provides additional information on books, including author and publication details.
- **HarshaanthKumar_ThiyagarajaKumar_Bookstore.twbx**: Tableau Workbook containing all visualizations answering the exploratory questions.
- **README.md**: This file.
- **Instructions.pdf**: Detailed instructions for the assignment, including how the data connections and visualizations were structured.

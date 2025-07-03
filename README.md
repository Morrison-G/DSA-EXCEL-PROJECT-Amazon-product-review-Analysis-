# DSA-EXCEL-PROJECT-Amazon-product-review-Analysis-
This Excel work on Amazon review case study aims to analyze Amazon product and customer review data to generate insights that can guide product improvement, marketing strategies, customer engagement, and potential revenue. Key features are: Clean Dashboard, Pivot tables, and Visual charts to support business decision making.

## Project Overview
This case study analyses Amazon product and customer review data to generate insights that can guide product improvement, marketing strategies, and customer engagement. Showing discount strategies, customer satisfaction and potential revenue across categories.

## Data Content
### Rows: were 1,465 in Total.
### Columns: were 16 in Total.
Product details: name, category, price, discount, and ratings.

### Customer engagement: user reviews, titles, and content.

## Tool Used
Microsoft Excel (Excel functions, Pivot Tables & charts).

## Data Cleaning Actions
Some data cleaning steps were applied to make the dataset proper for analysis without errors.

## Steps
### Product Name Column: cleaned using Proper & Left function (nesting), removing extra spacing in names.
### Category Column: cleaned using Left and Find function. The delimiter used was “|”.
### Helper columns: calculated columns and category columns were used in generating the Dashboard.
![Clean dashboard view](https://github.com/user-attachments/assets/9663ea4f-038f-47d4-9a89-d00db0fbc4a9)
## Key Business Questions Answered

1.	Average discount percentage by product category
Add a calculated column:
= (Actual Price - Discounted Price) / Actual Price * 100

Rows: Category
Values: Discount % → summarize by Average

2.	How many products are listed under each category?
   
Rows: Category
Values: Product Name → set to Count (Distinct)

3.	Total number of reviews per category
Use Rating Count column

Rows: Category
Values: Rating Count → Sum

4.	Which products have the highest average ratings
Sort your dataset by the Average Rating column (descending)
Pick top entries

5.	 Average actual price vs discounted price by category
   
Rows: Category
Values: Actual Price → Average
Discounted Price → Average

6.	Which products have the highest number of reviews
Sort Rating Count column in descending order

7.	How many products have a discount of 50% or more?
Add calculated column:
=IF (Discount % >= 50, "Yes", "No")
Then use filter in your Pivot table

8.	Distribution of product ratings
   
Rows: Rating (rounded if needed)
Values: Product Name → Count.

9.	Total potential revenue by category (Actual Price × Rating Count)
Add calculated column:
=Actual Price * Rating Count

Rows: Category
Values: Potential Revenue → Sum

10.	 Number of unique products per price range bucket
Create new column Price Bucket:
Excel formula=IF(Discounted Price < 200, "<₹200",
   IF(Discounted Price <= 500, "₹200–₹500", ">₹500")) (they should take note of the symbol for some systems)

Rows: Price Bucket
Values: Product Name → Count

11.	How does the rating relate to the level of discount?
Create a scatter chart:
X-axis: Discount %
Y-axis: Average Rating. (i am not sure if all excel version has scatter chat.).   alternative to scatter chat, this is a longer route thou. (take your time and you'll get it.) Line Chart (Grouped by Discount Ranges)
Steps:
Create a new column that groups Discount % into buckets like:
0–10%, 11–20%, ..., 91–100%
excel formula=IF([@Discount%]<=10, "0-10%",
  IF([@Discount%]<=20, "11-20%",
  IF([@Discount%]<=30, "21-30%", ...)))

Rows: Discount Bucket
Values: Average Rating → summarize as Average
Insert a line chart to show trend of average rating across discount buckets

12.	How many products have fewer than 1,000 reviews?
Filter Rating Count < 1000
Use COUNT or check the status bar, count is there.

13.	 Which categories have products with the highest discounts
Use the earlier Discount % column

Rows: Category
Values: Discount % → Max

14.	 Top 5 products by rating + number of reviews combined.

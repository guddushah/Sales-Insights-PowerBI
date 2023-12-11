# Sales Insights

## Problem Statement:
AtliQ Hardware is an Indian company specializing in production of computers and perepherals. The Sales Director of the company is facing challenges in tracking the sales in dynamically growing market across India. The Sales Director sees that the overall sales is declining but when communicated with the regional managers, they share vague insights verbally instead of showing the actual picture. Whenever the SD asks actual sales insights, the regional managers send him number of Excel files regarding sales which is simply hard to consume. Therefore, he decides to hire a data analyst to build the Dashboard for the company to know the business performance in different regions, weakest regions to consider for improving business and other business issues. This dashboard will inevetibly help the Sales Director in taking data-driven decisions.

## About AtliQ Hardware
- AtliQ Hardware is a computer and perepherals manufacturing company in India which manufactures PC, Laptops, Mouse, Keyboard, etc.
- AtliQ has regional offices in North India, Central India and South India headquarter in New Delhi.
- AtliQ's customers are companies like Excel Stores, Nomad Stores, Surge Stores, Electricalsara Stores across India.
- AtliQ's has customers on two Platforms
    - Brick and Mortar (Physical)
    - E-Commerce
- AtliQ sells products to their customers through two Channels
- Retailer (Both Physical and E-Commerce customers)
- Direct (AtliQ's own Physical and Ecommerce store i.e., AtliQ e-store and AtliQ executive)

## SQL Database dump file
- db_dump_version_2.sql
#### Tables in the Database
      - customers
      - dates
      - markets
      - products
      - transactions

## Data Analysis using SQL in MYSQL
1. **Show all customer records**                            
- SELECT * FROM customers;                    
2. **Show total number of customers**                                        
- SELECT count(*) FROM customers;
3. **Show transactions for Chennai market (market code for chennai is Mark001**
- SELECT * FROM transactions where market_code='Mark001';
4. **Show distrinct product codes that were sold in chennai**
- SELECT distinct product_code FROM transactions where market_code='Mark001';
5. **Show transactions where currency is US dollars**
- SELECT * from transactions where currency="USD"
6. **Show transactions in 2020 join by date table**
- SELECT transactions.*, date.*                                       
  FROM transactions
  INNER JOIN date ON transactions.order_date=date.date
  WHERE date.year=2020;                               
7. **Show total revenue in year 2020**
- SELECT SUM(transactions.sales_amount)                                              
  FROM transactions INNER JOIN date ON transactions.order_date=date.date
  WHERE date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";
8. **Show total revenue in year 2020, January Month**
- SELECT SUM(transactions.sales_amount)
  FROM transactions INNER JOIN date ON transactions.order_date=date.date
  WHERE date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");
9. **Show total revenue in year 2020 in Chennai**
- SELECT SUM(transactions.sales_amount)
  FROM transactions INNER JOIN date ON transactions.order_date=date.date
  WHERE date.year=2020 and transactions.market_code="Mark001";

## Dashboard Live here
https://app.powerbi.com/view?r=eyJrIjoiOGQ0NmZiY2MtNjI3Yy00MmNkLTgyN2YtNDkxNjJhYTZlODhhIiwidCI6Ijc5OWU3OTRjLTllYWMtNGUxZi05ZjY0LTE0ODhjYjMyMjRlNiJ9&pageName=ReportSection276c0ba0699bccdf4759

## Created Dashboard

### Revenue View
![revenue](https://github.com/guddushah/Sales-Insights-Data-Analysis-PowerBI/assets/40028193/1b1cc8a9-b160-478b-9660-72463734fb5f)

### Profit View
![profit](https://github.com/guddushah/Sales-Insights-Data-Analysis-PowerBI/assets/40028193/6634cedc-bdb8-46bf-8021-aa60a3c7f559)

### Customers View
![customers](https://github.com/guddushah/Sales-Insights-Data-Analysis-PowerBI/assets/40028193/7a73635b-578c-4c2e-a934-3a7bb179d1a1)

### Performance View
![performance](https://github.com/guddushah/Sales-Insights-Data-Analysis-PowerBI/assets/40028193/1294ef19-694e-4e90-9718-20973cc863a7)

## db_dump_version_2 database schema contails following tables
- customers
- dates
- markets
- products
- transactions

## The powerbi report contains 4 pages for generating several insights from the data
- Key Insights
- Profit Analysis
- Customer Analysis
- Performance Insights

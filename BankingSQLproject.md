# World Bank Loan Analysis

As someone who worked closely with banks in my job as the controller of a Ford dealership, I was really excited to learn how to use SQL to analyze loan data. We were constantly checking the loan rates and changes - paying special attention to outstanding loans and contracts in transit which affect the cash flow. In this project, I've been hired as a data analyst to look over the loans from the IDA and answer the following questions:

1. How many total transactions and how many from Nicaragua
2. How many total transactions per country
3. Maximum owed to IDA
4. Most recent payment
5. Who has the most loans
6. Find the average service charge rate

### 1. Findings

There were 1,109,994 rows of total data - which held 13,704 rows of data for Nicaragua. Bangladesh had the most transactions, which Cape Verde having the least. The maximum owed to IDA is 793,256,127.64 and the last payment recorded was on 12/31/14 from the borrower, Ministry of Finance. Bangladesh again came in first place with 1,885,305,576,348.22 in loans and the average service charge rate was 0.778.


### 2. The International Development Association (IDA) Data

The International Development Association (IDA) credits are public and publicly guaranteed debt extended by the World Bank Group. IDA provides development credits, grants and guarantees to its recipient member countries to help meet their development needs. Credits from IDA are at concessional rates. 

You can find the data set [HERE]
(https://finances.worldbank.org/Loans-and-Credits/IDA-Statement-Of-Credits-and-Grants-Historical-Dat/tdwh-3krx)

To look at this data, I uploaded the CSV file to bit.io, which is a PostgreSQL database that's free to use for 72 hours.


### 3. Analysis

By using the COUNT function, I was able to determine that there are 1,109,994 rows of data that need to be analyzed.
```SQL
SELECT COUNT (*) FROM "IDA_Statement_Of_Credits_and_Grants_-_Historical_Data.csv";
```
Then, I specifically wanted to know how much of the data was from Nicaragua. I used the following code to see that there were 13,704 rows. 
```SQL
SELECT COUNT (*) FROM "IDA_Statement_Of_Credits_and_Grants_-_Historical_Data.csv" WHERE country = 'Nicaragua';
```
To find the total transactions per country I counted and grouped the data by country. 
```SQL
SELECT "country", COUNT(*) FROM "IDA_Statement_Of_Credits_and_Grants_-_Historical_Data.csv" GROUP BY "country";
```
As you can see below, Bangladesh had the most transactions, with Cape Verde having the least. 

<img src="images/SQL Bank by country.jpg?raw=true"/>

The max owed to IDA, 793,256,127.64, was easily found with the MAX function.
```SQL
SELECT MAX ("Due to IDA") FROM "IDA_Statement_Of_Credits_and_Grants_-_Historical_Data.csv;
```
To find the most recent payment, I needed to investigate the last repayment date and the borrower. The last date was 12/31/14 with the Ministry of Finance
```SQL
SELECT "borrower" FROM "IDA_Statement_Of_Credits_and_Grants_-_Historical_Data" 
where "Last Repayment Date" =(SELECT MAX ("Last Repayment Date") 
FROM "IDA_Statement_Of_Credits_and_Grants_-_Historical_Data" ) LIMIT 1;
```
I looked at the country with the most loans next. It makes sense that Bangladesh is again at the top of the list. 
```SQL
SELECT "country", MAX ("Due to IDA") FROM "IDA_Statement_Of_Credits_and_Grants_-_Historical_Data" 
GROUP BY "country";
```

<img src="images/SQL Bank max by country.jpg?raw=true"/>


### 4. Conclusion

The IDA aims to reduce poverty by providing financing and policy advice for programs that boost economic growth, build resilience, and improve the lives of poor people around the world. There are 75 countries that are eligible to receive funds, with Bangladesh topping the group. With an average service charge rate of 0.778, people are able to get loans to help with building new businesses and improving their quality of life. To continue doing business, I would suggest watching all the outstanding loans and consider moving rates downward if people are still unable to pay them back.  
 

If you liked my analysis, please add me on [LinkedIn](https://www.linkedin.com/in/kim-gasgarth/)


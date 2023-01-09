# World Bank Loan Analysis

As someone who worked closely with banks in my job as the controller of a Ford dealership, I was really excited to learn how to use SQL to analyze loan data. We were constantly checking the loan rates and changes - paying special attention to outstanding loans and contracts in transit which affect the cash flow. In this project, I've been hired as a data analyst to look over the loans from the IDA and answer the following questions:

1. How many total transactions
2. How many total transactions per country
3. Maximum owed to IDA
4. Most recent payment
5. Who has the most loans

### 1. Findings

There were 1,109,994 rows of total data - which held 13,704 rows of data for Nicaragua. Bangladesh had the most transactions, which Cape Verde having the least. The maximum owed to IDA is 793,256,127.64 and the last payment recorded was on 12/31/14 from the borrower, Ministry of Finance. Bangladesh again came in first place with 1,885,305,576,348.22 in loans.


### 2. The International Development Association (IDA) Data

The International Development Association (IDA) credits are public and publicly guaranteed debt extended by the World Bank Group. IDA provides development credits, grants and guarantees to its recipient member countries to help meet their development needs. Credits from IDA are at concessional rates. 

You can find the data set [HERE]
(https://finances.worldbank.org/Loans-and-Credits/IDA-Statement-Of-Credits-and-Grants-Historical-Dat/tdwh-3krx)

To look at this data, I uploaded the CSV file to bit.io, which is a PostgreSQL database that's free to use for 72 hours.


### 3. Analysis

By using the COUNT function, I was able to determine that there are 1,109,994 rows of data that need to be analyzed.
```SQL
SELECT COUNT (*) FROM "IDA_Statement_Of_Credits_and_Grants_-_Historical_Data.csv";

<img src="images/MA low grad.jpg?raw=true"/>

I’ve always heard that the class size had a huge impact on student learning. By looking at the next visualization, you can see that economic disadvantage had more impact on their college attendance. 

<img src="images/MA class size.jpg?raw=true"/>

I also looked at 4th grade math levels and determined that there were only 4 schools that had a passing score. This was very surprising to me, and definitely something that needs to be investigated further, as shown below.

<img src="images/MA 4th grade math.jpg?raw=true"/>

### 4. Conclusion

 

If you liked my analysis, please add me on [LinkedIn](https://www.linkedin.com/in/kim-gasgarth/)


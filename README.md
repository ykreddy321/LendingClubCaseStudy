# Project Name: Lending Club Case Study
	
Lending Club is a Consumer Finance Company, which is specialised in lending the various types of loan to customers. Lending the loan to ‘Risky’ applicants causes the financial loss to the lenders.

The Objective of this case study to analyse the data given about past loan applicants and whether they ‘defaulted’ or not. We will identify the risky loan applicants using the Exploratory Data Analysis (EDA). Then we will recommend if the person is likely to default, which may be used for taking actions such as denying the loan, reducing the amount of loan, lending (risky applicants) at a higher interest rate, etc. This helps to cutting down the amount of credit loss.

We also need to identify the driving factors which causes for loan defaulters. This information company can utilise this for portfolio and risk assessment. 


## Table of Contents

## General Information
  To identify the risky applicants(defaulters), we have used the loan.csv file. Which contains about the past decisions taken by the company. 
  These are categorized as 'Fully Paid', 'Current' and 'Charged-off' applicants.
  
  Followed the below steps to identify the Risky applicants.
  1. Data Understanding: There are 39717 rows and 111 columns provided in the loand.csv file. 
	It contains about the applicants information how much is the loan amount, interest rate, dti, loan status, purpose of the loan taken, employment experience, annual income , grades,home ownership,terms, pub_rec_bankruptcies and location details.
	 
  2. Data Cleaning & Manipulation:
	a.Fixed the rows and columns: 
		Deleted the columns which only has NA values.
		Deleted the columns which has only 1 value throughout and these are not useful for analysis.
		Removed the free text columns which has too many values and are not useful for analysis - url, desc, title, emp_title
		Dropped few columns(next_pymnt_d,mths_since_last_record,mths_since_last_delinq)
		The columns recoveries,collection_recovery_fee,total_rec_late_fee,out_prncp_inv and out_prncp are 0 for Fully Paid and Current loan status. Hence, these columns can be deleted for the analysis as they have data only when the customer has Chanrged Off.
		
	b. Data Transformation:
		Fixed the missing values and replaced with mean values.
		Standardize values for term, int_rate and revol_util columns.
		Derived month and year column from issue_d column
		Derived charged off ratio for multiple parameters using the number of charged of loans/ total no. of loans in the category

	c. As part of Filtering rows and columns:
		Removed the outliers for salary (more than 99 percentile)
		
  3. Univariate Analysis: First we identify the numerical, categorical and other types of data.
     a. Drawn the count plot and pie chart for Categorical variables.
	 
		Observation from above plots.
		1. 73% of people opted for shorter loan term i.e. 36 months
		2. 75% loans are awarded with grade A. B and C.
		3. 23% loan customers are with 10+ years of exp.
		4. 92% of the loan customers have either rented or mortaged homes.
		5. 43% of the customers are Not Verified.
		6. The loan customers have constantly increased from 2007 to 2011.
		7. 83% have Fully Paid the loand and 14% have Charged off.
		8. 47% customers give debt consolidation as the purpose of loan.
		9. 18% customers are from CA and 10% from NY.
		10. For 89% of the customer delinq_2yrs = 0
		11. For 49% of the customer inq_last_6mnths = 0
		12. For 95% customer pub_rec is 0 and pub_rec_bankrupcies = 0
		13. Number of loans issued have increased every year from 2007 to 2011
		14. Highest number of customers are from CA and NY
		
 4. Bivariate Analysis:
	Created bins for numerical columns, to convert them into Categorical columns
	Drawn the box plot, hist plot between multiple variables to identify the relation between them.
		Home_ownership V Loan Status
		Grade vs Term
		int_rate_cat Vs Charged Off ratio
		dti vs Charged-off ratio
		Grade Vs Charged off ratio
		emp-length Vs loan status
		loan amount vs Charged Off ratio.
		
	 Observation from above plots:
		- With the increase in salary, the loan charge off has reduced.
		- More customers are with 10+ year of experience.
		- The charge off keeps increasing as we move from Grade A to G
		- Customers with annual income range 0 to 20000 are more likely to be Charged off.
		- Customers with Mortgaged homes Charge off less. Own and Rented house customers are charging off equally.
		- With the increase in interest rate, the charged off ration is increased.
		- With more dti value increased the Charged Off ratio.
		- With the increase in loan amount the Charged off ratio increased
		- Higher charge off with higher loan amount. Highest charge off ration is for the high loan amount 25,000+
		- Charge off increases with higher public record bankruptcies. Data for 2 bankruptcies is very less but we have enough data for 1 
          bankruptcies where charge off is higher than 0 bankruptcies.
		-Small businesses seem to have the highest charge off ratio

		
  5. Multivariate analysis
	 Created heat map to find the correlation between variables.
	 
	 Observation from HEATMAP :
		- loan_amt is having strong positive correlation with funded_amnt_inv, total_pymnt, installment
		- Loan_amt is having intermediate positive correlation with annual_inc , int_rate, revol_bal. 
		- Total_pymnt is having the strong positive correlation with total_pymt_inv.
		- Annual income is having the negative correlation with dti.
	
## Conclusions & Recommendations:
	
	Based on the above analysis below conclusions are made:
	
		- Customer with high experience have the more loan amount and interest rate.
		- Higher charge off with higher loan amount. Highest charge off ration is for the high loan amount 25,000+
		- 92% of the loan customers have either rented or mortgaged homes
		- 23% loan customers are with 10+ years of exp.
		- Loans with lesser funding are more prone to charge off.
		- 47% customers give debt consolidation as the purpose of loan
		
   Recommendations:
   
		- We see the owned and rented home customers are risky applicant and we should limit the loan amount based on the dti ratio.
		- Customers with lower salary shall not be given loan of higher amount. Also, the interest charged from them shall be lower.
		- We see small business loan customers are risky applicants and they charged off more, so we keep the investors less risked, and we can
     	  reduce the interest rate to avoid delay in payments.
		- Increase the interest for the customers which are in less loan amount for the in moving, vacation, wedding etc.
		- Customer with grade E,F and G are more charged off. These are risky applicants. We need the limit the loan amount.
		- Customers with less or no funding tend to charge off more so those customer shall be verified on parameters like dti, home ownership etc.
		  before giving the loan


## Technologies Used
		Python (Version 3.11.7)
		Numpy  (Version 1.26.4)
		Pandas (Version 2.1.4)
		Matplotlib (Version  3.8.0)
		Seaborn (version 0.13.2)

## Acknowledgements
	 This project is created based on the trainings provided by UpGrad Team.

## Contact
   Created by Kushalava Reddy Yanala and Trapti Agarwal  

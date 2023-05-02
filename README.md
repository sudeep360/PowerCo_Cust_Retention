This Project is a virtual Internship Project I have donw with BCG Gamma. So, the details of the project are discussed below as well as description of multiple stages of task.

PowerCo is a major gas and electricity utility that supplies to corporate, SME (Small & Medium Enterprise), and residential customers. The power-liberalization of the energy market in Europe has led to significant customer churn, especially in the SME segment. 
They have partnered with BCG to help diagnose the source of churning SME customers.
A fair hypothesis is that price changes affect customer churn. Therefore, it is helpful to know which customers are more (or less) likely to churn at their current price, for which a good predictive model could be useful.
Moreover, for those customers that are at risk of churning, a discount might incentivize them to stay with our client. 
The head of the SME division is considering a 20% discount that is considered large enough to dissuade almost anyone from churning (especially those for whom price is the primary concern).

Task 1: Basic Understanding of the Business and Problem Framing

Problem Clients are Facing:
Client (PowerCo) is a major gas and electricity utility,
•	supplies to corporate, SME and residential customers.
Significant churn problem:
•	driven by power-liberalization of the energy market in Europe, problem is largest in SME segment.
Clients Hypothesis:
•	Churn is driven by customer price sensitivity.

Clients Plan:
•	SME division head suggests that offering customers at high propensity to churn a 20% discount might be effective.

Questions for us?
•	Is it possible to predict customers likely to churn using a predictive model?
•	Is the churn driven by the customers’ price sensitivities? How should the team go about testing this hypothesis?
•	What data might be needed from the client to test our hypothesis?
•	What analytical models you would use to test such a hypothesis?

Possible Solution:
To test the hypothesis of whether the churn is driven by the customers’ price sensitivity, we would need to model churn probability of customer and derive the effect of prices on churn rate. For this purpose, we need following data sets:
•	Customer data – should include characteristics of each client, for eg, industry, historical electric consumption, date joined etc.
•	Churn data – should include the details of churned customer.
•	Historic price data – should include the prices of the client changes to each customer for both electricity and gas at granular time intervals.  
Once we have these datasets, we would need to engineer features based on the data that we obtain, and build a binary classification model (eg, Logistic Regression, Random Forest, Gradient Boosted Machine)
Based on the complexity, explanability, and the accuracy of the models, we can pick the correct model.
Once we pick our model, we would be able to understand the direction and magnitude of the impact of prices on churn rates, as well as relative importance of prices compared to other factors. 
Furthermore, the model would allow us to size the business impact of the client’s proposed discounting strategy. 


Task 2: Exploratory Data Analysis and Data Cleaning:

We have gathered the clients information dataset and price information dataset from the PowerCo clients, these datasets include important informations listed below:

client_data.csv

id = client company identifier
•	activity_new = category of the company’s activity
•	channel_sales = code of the sales channel
•	cons_12m = electricity consumption of the past 12 months
•	cons_gas_12m = gas consumption of the past 12 months
•	cons_last_month = electricity consumption of the last month
•	date_activ = date of activation of the contract
•	date_end = registered date of the end of the contract
•	date_modif_prod = date of the last modification of the product
•	date_renewal = date of the next contract renewal
•	forecast_cons_12m = forecasted electricity consumption for next 12 months
•	forecast_cons_year = forecasted electricity consumption for the next calendar year
•	forecast_discount_energy = forecasted value of current discount
•	forecast_meter_rent_12m = forecasted bill of meter rental for the next 2 months
•	forecast_price_energy_off_peak = forecasted energy price for 1st period (off peak)
•	forecast_price_energy_peak = forecasted energy price for 2nd period (peak)
•	forecast_price_pow_off_peak = forecasted power price for 1st period (off peak)
•	has_gas = indicated if client is also a gas client
•	imp_cons = current paid consumption
•	margin_gross_pow_ele = gross margin on power subscription
•	margin_net_pow_ele = net margin on power subscription
•	nb_prod_act = number of active products and services
•	net_margin = total net margin
•	num_years_antig = antiquity of the client (in number of years)
•	origin_up = code of the electricity campaign the customer first subscribed to
•	pow_max = subscribed power
•	churn = has the client churned over the next 3 months


price_data.csv

id = client company identifier
•	price_date = reference date
•	price_off_peak_var = price of energy for the 1st period (off peak)
•	price_peak_var = price of energy for the 2nd period (peak)
•	price_mid_peak_var = price of energy for the 3rd period (mid peak)
•	price_off_peak_fix = price of power for the 1st period (off peak)
•	price_peak_fix = price of power for the 2nd period (peak)
•	price_mid_peak_fix = price of power for the 3rd period (mid peak)

With the help of these data we have managed to perform the followings steps:
1. Calculate customer churning and visualize; demonstrated about 10% of customers churned over the past 3 months.
2. Visualized the sales channel and distribution over the different channel, as well as the possible relationship with churning.
3. Visualized the consumption in the last year and month, and visualized the outliers.
4. Visualized the forecast for the next 12 months, and another year.
5. Visualized the contract type, ie. with and without gas.
6. Visualized margins and outliers.
7. Visualized other different columns.
8. Finally we  moved into cleaning our dataframes, than proceeded towards testing the hypothesis; 'Price change affect custmer churn'.
 However, the correlation between the price sensitivity and the churn is very low. So we, couldn't conclude price is necessarily affecting the churning. So, we move onto further analysis onto Task 3 for the project.
 
 
 
Task 3: Feature Engineering and Modelling

Now as we have a good understanding of the data, and more confident with the dataset. We are digging deeper to the business problem.
We first seen the average price change across periods as well as max price change over periods and month.
Afterwards, we moved to calculationg churn for those periods, where we concluded:
" That companies who have only been a client for 4 or less months are much more likely to churn compared to companies that have been a client for longer. 
Interestingly, the difference between 4 and 5 months is about 4%, which represents a large jump in likelihood for a customer to churn compared to the other differences between ordered tenure values. 
Perhaps this reveals that getting a customer to over 4 months tenure is actually a large milestone with respect to keeping them as a long term customer. "





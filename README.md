# UK National Rail analysis
## Project Background
This project examines mock ticket sale data from the United Kingdom's National Rail network, a collective of train services operated across the country and a key part of the UK's public transport infrastructure.

The dataset includes detailed transaction records for ticket sales and train rides between January and April 2024, containing information that can be used to improve sales, marketing efforts, operational efficiency and loyalty programs.

The analysis is focused on these key areas:
  * **Sales Trends:** Evaluation of purchase patterns over time and across customer segments, including payment behavior and ticket preferences.
  * **Operational Efficiency:** Analysis of service reliability and identification of major causes of journey disruptions.
  * **Loyalty Program:** Asessment of the effectiveness and financial impact of the railcard discount program.

## Data Structure & Preparation
The dataset consists of a single table with 31.653 records. Each record represents a single ticket transaction, with details being kept for the purchase, journey and ticket characteristics. No duplicate transactions were found, and all entries were structurally valid. 

Below is a sample of the most important Data Fields. 👉 [Click here for full data dictionary (CSV)](railway_data_dictionary.csv)
| Field Name	| Description | 
| ----------- | ----------- | 
|Transaction ID |Unique identifier for an individual train ticket purchase|
|Date of Purchase|Date when the ticket was purchased|
|Time of Purchase|Time when the ticket was purchased|
|Purchase Type|Whether the ticket was purchased online or directly at a train station|
|Payment Method	|Payment method used to purchase the ticket(Contactless, Credit Card, or Debit Card)|
|Railcard|Whether the passenger was a National Railcard holder(Adult, Disabled, Senior) or not(None). Railcard holders get 1/3 off of their ticket purchases|
|Ticket Class|Seat class for the ticket(Standard or First Class)|
|Ticket Type|When the ticket was bought or can be used. Advance tickets are 1/2 off and must be purchased at least a day prior to departure. Off-Peak tickets are 1/4 off and must be used outside of peak hours(weekdays between 6-8 am and 4-6pm). Anytime tickets are full price|
|Price|Final cost of the ticket|
|Arrival Time|Time the train was scheduled to arrive at its destination|
|Actual Arrival Time|Time the train arrived at its destination|
|Journey Status|Whether the train was on time, delayed, or cancelled|


To further enhance the dataset for analysis, new columns were extracted based on the existing data. These include time delayed for disrupted journeys, ticket purchase day and hour, and journey departure/arrival hour.

## Summary of Findings
**Sales Trends**:
  * A total of **31.653** tickets were sold, generating **£741,921** in revenue. The average ticket price was **£23**.
  * Sales were evenly spread across the four months, with January and March slightly outperforming February and April. Sales also remained consistent across the week, but with increases on Fridays and Weekends, indicating consistent daily commuting and leisure use.
  * Hourly sales are high in the mornings at 06:00 - 09:00 and gradually decline afterwards. The sales hit their peak at **17:00** and **20:00**, which aligns with daily commute cycles. This pattern shows opportunities for dynamic pricing and staff planning.
  ![EXCEL_ObuqtYg7hf](https://github.com/user-attachments/assets/a4893bee-855b-45ed-b3f8-5f4d7969170a)
  * Standard tickets, with an average price of **£21** dominate with **90%** of all sales. First Class ticket sales, with an average price of **£49** were minimal, suggesting potential pricing issues.
  * Advance(**55%**) and Off-Peak(**28%**) were the most popular ticket types, likely due to their cost effectiveness, while Anytime tickets were least used. Customers buying tickets ahead of time is supported by differences in hourly sales & rides:
      - 06:00 high rides, low sales -> customers buying tickets the day before early morning rides.
      - 14:00 low rides, high sales -> customers buying tickets for peak departure hours at 17:00 and 18:00 to avoid long purchase queues.
  *  **59%** of tickets were bought online, signaling strong digital adoption. There may be room to further incentivize digital purchases and therefore lower congestions and rushes at stations for last-minute buys.
  * Payment methods were skewed towards Credit Cards(**61%**) and Contactless(**34%**) with Debit Cards trailing behind(**5%**). This suggests either limited support for debit cards, or user preference, which is hard to determine without further customer demographic analysis.
  ![EXCEL_dcWRMUhhxA](https://github.com/user-attachments/assets/dec3953d-4ba8-4531-8f9c-15799b292c58)

**Loyalty Program**:
  * Only **11.000** out of 31.653 tickets were bought by a railcard owner - a relatively low **35%** adoption rate. Given the popularity of budget-friendly ticket types, this is surprising and may indicate a lack of awareness or barriers in the application process.

**Operational Efficiency**:
  * **87%** of rides were on time, **7%** were delayed, and **6%** cancelled, indicating a generally reliable service.
  ![EXCEL_aJaOftcolT](https://github.com/user-attachments/assets/c9b4c531-302c-4cab-adc5-69337fc877ae)
  * Weather-related issues are the most common delay cause. Staff shortages, although less frequent, cause the longest delays(**75 min**), almost double the average delay time(**42 min**).
  * Signal failure was the leading cause of cancellations, followed by staffing problems and weather-related issues. Since common factors are present in both delays and cancellations, working on fixing these issues could dramatically lower the total amount of journey disruptions.
  * Delays and cancellations lead to **£38.702** lost in revenue, with over 1.100 refund requests. Refund patterns suggest higher levels of customer frustration with cancellations(1 refund per 3 cancelled rides) than with delays(1 per 4 rides).
  ![EXCEL_XIAujDQfQO](https://github.com/user-attachments/assets/debdec8a-eaf1-4e9f-8ecc-b9291376ef08)



## Recommendations:
  - **Expand Digital Sales Initiatives:** Promote online exclusive discounts to reduce congestion at stations and drive app usage further.
  - **Improve First Class Tickets:** Introduce a trial period with reduced prices or added benefits to increase demand.
  - **Optimize Staffing:** Address staff shortages with improved scheduling and training. Increase numbers of staff at peak sales and ride hours.
  - **Infrastructure Resilience:** Improve infrastructure, especially signalling systems, and add real-time weather response protocols to limit service disruptions.
  - **Promote the Railcard:** A more visible railcard campaign as well as targeted promotions(e.g pop-ups during checkout) could boost the uptake and long term loyalty.





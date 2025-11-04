**INSIGHTS & MODEL REPORT**
To forecast public transport ridership trends, several predictive models were considered — namely ARIMA, Random Forest Regressor, and Facebook Prophet. After comparative analysis, the ARIMA (AutoRegressive Integrated Moving Average) model was selected as the most suitable for this dataset due to its interpretability, time-dependence handling, and forecasting accuracy on the available data.
Why ARIMA Model Was Used (Compared to Prophet & Random Forest)
1.	Nature of Data – Time Series (Sequential & Continuous)
The dataset represents daily passenger counts for different transport services — Local Route, Light Rail, Peak, Rapid, and School — which are time-dependent and show temporal trends and seasonality.
ARIMA (AutoRegressive Integrated Moving Average) is specifically built to handle such continuous time series data, making it ideal for forecasting demand over days or weeks.
2.	ARIMA vs Prophet
•	Prophet (by Meta) performs well for strong seasonal or holiday patterns, but it assumes smooth long-term trends.
•	In your dataset, the passenger count changes sharply due to events like COVID lockdowns or school holidays, which are not purely periodic. Prophet may over-smooth these changes.
•	ARIMA, on the other hand, adapts better to short-term shocks and non-seasonal variability.
3.	ARIMA vs Random Forest
•	Random Forest is a machine learning model, not a time-series model. It does not natively consider time order or autocorrelation, which are critical in forecasting.
•	While it can capture complex non-linear patterns, it often fails to model temporal dependence directly unless we manually create lag features.
•	ARIMA inherently models autocorrelation through its AR (Auto-Regressive) and MA (Moving Average) components — making it more suitable for forecasting based on historical momentum.
4.	Simplicity & Interpretability
•	ARIMA offers a clear mathematical formulation, allowing parameters to be easily tuned and results interpreted (lags, differencing, and error smoothing).
•	Random Forest and Prophet are black-box models in comparison.
5.	Empirical Justification
•	From your evaluation section, ARIMA produced lower MAE, RMSE, and MAPE values for multiple service routes — showing superior short-term accuracy compared to Prophet and Random Forest.
 
 
ARIMA Parameters → (p, d, q) = (5, 1, 0)
Parameter	Meaning	Explanation in your model
p = 5	Auto-Regressive order	Uses past 5 lagged observations to predict the next value (captures short-term memory of passenger trends).
d = 1	Differencing order	The data is differenced once to remove trend and make the series stationary. This helps handle gradual increases/decreases in ridership.
q = 0	Moving Average order	No moving average term used — assumes the past forecast errors don’t significantly affect future predictions.


**INSIGHTS**
**Insight 1:** Impact of COVID-19 Lockdowns on Transport Usage
During Canberra’s COVID-19 lockdown (12 August – 15 October 2021), School and Peak services experienced a near-total drop in ridership, reflecting the immediate halt of educational and office commuting. However, Local Route and Light Rail services retained limited but steady passenger volumes — primarily essential workers and critical travel needs.
Recommendations:
Suspend School and Peak services during citywide lockdowns.
Maintain Local Routes and Light Rail at reduced frequency for essential connectivity.
Prevent empty fleet operations to save costs and fuel.
 

**Insight 2:** Weekday–Weekend Passenger Behavior and Light Rail’s Leisure Strength
Chart Interpretation:
Local Route, Rapid Route, and School services show very strong weekday demand (Monday–Friday) and a sharp decline on weekends (Saturday–Sunday). This means these services are commuting- and education-oriented, catering to workers and students.
Light Rail maintains consistently moderate ridership throughout the week, and while it dips slightly on weekends, it still retains a large proportion of its weekday passengers — much more than other routes. This shows Light Rail serves not only daily commuters but also leisure and tourism travelers.
Peak Service has very low counts overall — consistent with its function to supplement rush-hour demand only.
Recommendation: Maintain or slightly increase weekend service frequency, especially in leisure-heavy zones (malls, markets, event areas, and tourist spots).
Introduce weekend family/group passes and off-peak travel discounts to attract leisure travelers.
Partner with local tourism boards, event organizers, and shopping districts for co-branded promotions or “ride + event” packages.
 

**Insight 3:** Local Route Shows Strong Weekday Demand but Weak Weekend Activity
Chart Interpretation:
High Ridership (Monday–Friday): Local Route usage peaks on weekdays, especially from Tuesday to Friday, averaging around 13,000–14,000 passengers. This indicates that Local Routes are primarily commuter-oriented, serving office-goers and daily travelers.
Sharp Decline on Weekends: Ridership drops by nearly 70-75% on Saturday and Sunday, showing much lower demand. Suggests limited need for local commuting and minimal recreational or leisure use of these routes.
Recommendations: Maintain or increase frequency during weekday peak hours (7–10 AM and 4–7 PM) to handle high commuter flow.
Introduce express or short-turn services on busy corridors to reduce waiting time. Offer weekday passes or monthly discounts to encourage consistent usage among regular passengers
 

**Insight 4:** Weekend Ridership Recovery and Growth Over Time
Chart: Weekend Total Ridership Over Time
Interpretation:
The chart shows a sharp drop in 2020–2021, aligning with COVID-19 lockdowns and travel restrictions, where weekend leisure and non-essential trips nearly disappeared.
From mid-2021 onward, there is a steady recovery trend, with weekend ridership gradually climbing back — indicating a return of public confidence and increased leisure mobility.
Post-2022, weekend usage stabilizes and even slightly increases, suggesting that weekend transport demand is becoming a consistent part of Canberra’s travel behavior.
The occasional spikes in ridership likely correspond to major public events, festivals, or seasonal tourism periods.
**Recommendations: ** Maintain or increase Light Rail frequency on weekends.
Introduce special weekend passes or discounts to capture leisure demand.
Consider data-driven collaborations with tourism and event boards to synchronize service with major attractions.
 

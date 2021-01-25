## TEAM
Earth Rescuers is tackling the Sea Ice Challenge

## Inspiration
The loss of sea-ice has huge ramifications such as lowered global temperatures, and loss of species diversity in the Arctic ecosystem. This hackathon gives us an opportunity to understand more intimately the data that describes an aspect of this climate change issue and ultimately what we can do about it.

## What it does
Using x_EASE, y_EASE, u_ERA5, v_ERA5, sic_CDR, h_cs2smos, h_piomas, d2c, it predicts u_buoy, v_buoy. 
Our predictions on the test set can not be found here as the data were confidential.

## How we built it
We first read the guidelines and reformulated the problem. Then we visualized the data using heatmap to see the correlation between data. As Machine Learning Problems tend to perform better with normalized data, we performed MinMaxScaler normalization. We then trained a simple linear regression model without any tuning as a baseline. We got our first results with a high MSE (25). We performed some feature reduction using PCA and read some literature to see which models could perform better. We also asked the mentors and got help from different panelists. We tried KNN (with k = 19 after performing GridSearch, MSE =18), Ridge, Random Forest (with n_estimators = 50 and max_features = sqrt after performing a GridSearch, MSE = 15). We had low ressource so we could not increase n_estimators to get better results. We also tried an MLP without any tuning (MSE = 19). All these models were trained using CV=5.

## Challenges we ran into
Due to the mixed interests of our groups in terms of what approaches and topics we wanted to tackle. It took some time to be more unified as a team. We also faced challenges in what figuring out the most appropriate model we could use as some of us have not coded before.

## Accomplishments that we're proud of
We are proud of being able to contribute to the making a difference with climate change by suggesting strategies we could do to lessen the impact it has on surrounding wildlife. Namely predicting sea-ice flow so that Travel and transport to the Arctic could be safer for both humans and wildlife Oil spills and other toxic waste can be cleaned efficiently

## What we learned
The proposed features seem interesting at predicting sea-ice velocity! In addition, by building this machine learning model, we can obtain a more accurate depiction of the flow of sea-ice in upcoming hours as well. For the new machine learning students we also learned about workflows in data preparation, data exploration, and relevant machine learning techniques Through data, it is possible to understand environmental issues and what we could do about it. How crucial teamwork is in intensive collaborative projects.

## What's next for Sea Ice Challenge
This challenge gave us the opportunity to quickly compile a model that could predict sea-ice movement, however there could be other features such as sea-level of nearby countries, hourly/daily UV levels, amongst other features that could add accuracy to our model.

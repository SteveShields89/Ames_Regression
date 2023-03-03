## Problem Statement:
    As industries continue to grow, there will be a need for more housing options; not only the employees but the families that could potentially be displaced. Affordable housing is something that should be available to all despite their current circumstances. Here at Lotus Housing Solutions (LHS), we are currently in the development phase of building multiple communitites around the greater Atlanta area, to help fill that need. Through research and local surveys we have an idea of how these units should be priced but are looking for a more concrete way of determining housing prices for our prospective residents.

    After some weeks of combing through datasets, we have finally landed on the Ames, Iowa dataset to help us come up with a predictive model that can aid us in obtaining this goal. Through exploratory analysis, visiualizations, feature engineering and model tuning, we hope to come up with a model that will help us predict housing prices. This model will just be a starting point, as changes in legislature, population, and interests will have an overall impact on fianl pricing. We are just looking for a good starting point, based off of our own research.

## Data Dictionary and Description:
     The Ames dataset has over 80 features that we can select from which include 23 nominal, 23 ordinal, 14 discrete, and 20 continuous variables. Some of the variables we used for the final model are as follows: *(note these are not all of the ones used. Just the ones with the highest correlations)

    |Feature|Type|Description|
    |---|---|---|
    |Half Bath|int64|Number of half baths|
    |Lot Area|int64|Lot size in square feet|
    |Wood Deck SF|int64| Deck area in square feet|
    |Open Porch SF|int64| Porch area in square feet|
    |Bsmt Fin SF1|int64| Rating of basement finished area|
    |Fireplaces|int64| Number of fireplaces|
    |Totrooms AbvGR|int64| Total rooms above ground|
    |Garage YR built|float64| Year the garage was built|
    |Full bath|int64| Number of full baths|
    |Year Remod/Add|int64| Year of remodel or addition|
    |Year built|int64| Year the house was built|
    |1st flr SF|int64| First floor area in square feet|
    |Garage Cars|float64| Number of cars that can fit in garage|
    |Garage Area|float64| Area of garage in square feet|
    |Gr Liv Area|int64| Above ground living area in square feet|
    |Overal Qual|int64| Rates overall material and finish of house|
    |SalePrice|int64| Last sale price of house|
    
    The link to the full dictionary is [here](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt)

    Sale Dist.png

## Feature engineering and Model Selection:
    As previously stated, the Ames data set is extensive. After clearing the data of null values, I was finally able to visualize the data and begin to engineer some features. Below you can see a few visuals that I used to help me with my engineering. Most of the engineering completed were changing all of the ordinal values in to numbers. For insance, there was a column for garage quality that was rated from 'Poor' to 'Excellent'. I ended up plcaing them on a scale from 0 to 5. All ordinal features were changed to the same type of scale. 
    
    Next I delved into visualizing any outliers from the highest correlated features. I did not find many outliers and the ones that I did find were dropped, namely those in the 'Sale Price' feature. This helped out when it came to establishing a baseline for model selection. Speaking of baseline, I took the mean of the cleaned 'Sale Price' column which was $178,182.59.

    I tried 4 different models for my prediction but only 3 of them worked well against unseen data. Of the last 3 models, the final model was found to be the best. I used a combination of LassoCV and Standard Scaler. The mean of the predicted values was ~ $178,546.61 with an RMSE of $22,885.58  

    ModelLas.png

## Conclusion/Next Steps:
    In order to move forward with our final model, we will need to test the model on more unseen data, specifically related to the housing market here in Atlanta. This definitely a great starting point so we are hoping to get more investments to put more resources in to a production model that we will use to price our houses.    


## Sources: 
    De Cock, Dean. "Ames, Iowa: Alternative to the Boston housing data as an end of semester regression project." Journal of Statistics Education 19.3 (2011).



Pokemon Legendariness Classifier
================
Rayce Rossum, Jack Yang

## Intro

### Proposal Question

We are interested in what are the top strongest indicators that
determines whether a Pokemon is legendary.  
This question is **Predictive** as we are using existing Pokemon data to
assess the attributes that are most indicative of a legendary Pokemon

### Procedure

#### Data Retrieval

We used the following python script to retrieve the Pokemon dataset from
[Kaggle](https://www.kaggle.com/abcsds/pokemon)

#### Data Cleaning

We dropped “Generation” and “Total”

#### Exploratory Data Analysis

The following barplot explores the dataset and gives us some intuition
of what proportion of Pokemon is actually legendary. ![barplot]()

We are most curious in determining whether there is a relationship
between Pokemon attributes and the legendary status. ![boxplot]()

Lastly, we also want to see whether there is favoritism for legendary
Pokemon across different types. ![barplottype]()

#### Analysis

We used the decision tree classifier in Python’s sklearn. We fed in
stats of Pokemon including: type, attack, health… etc. as features.
After fitting the data, object attribute feature\_importances\_ returned
an array of the gini score reduction of each feature. The top features
with the highest values answer our question.

#### Results

![barplotimportance]()

From our analysis, we found “Sp. Atk”, “Attack”, “Speed” and “HP” to
have the greatest impact on determining the legendary status of Pokemon.
Types, as it turned out, have very little influence.

These top attributes, however, are greatly dependent on the set random
state. After many iterations, we found “Sp. Atk” and “Attack” to
consistently have high importance.

#### Limitations and Time Considerations

With our current knowledge level, between decision trees and KNN, we
were more comfortable with classifying categorical and numerical
variables using decision trees. However, we cannot say whether decision
trees is better than KNN. A problem we encountered using decision trees
is that it is dependent on random states for tie breaking. It is
difficult to conclusively state the exact combination of top predictors
as they vary at times. KNN does not have this error. These two may also
not be the best method for our question. Our views may change in a few
weeks from now with more techniques learned in 571.

Another limitation with this analysis is the psedo-legendaries where
Pokemon with high stats are still considered non-legendary. So in this
case, our classifier would wrongly classify a normal Pokemon as a
legendary, eg.

With more time avilable, we would test likely mis-classifications such
as the case mentioned above to better fine tune our classifier.
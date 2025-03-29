# Multinomial-Choice-Models
Multinomial choice models are used to model decisions where the outcome is a choice among more than two discrete alternatives.

Step 1: Understanding the Problem
We’re modeling commuter mode choice: Bike, Bus, or Car

Each person chooses one mode, based on:

time: travel time in minutes

cost: cost of using the mode

risk: chance of accident

These are the independent variables (x); the choice is the dependent variable (y)



Step 2: Why Use a Multinomial Logit Model
Standard linear regression doesn’t work for choices like bike/bus/car

MNL allows us to estimate probabilities for each choice

It’s based on utility theory: people choose the option with the highest perceived utility




Step 3: Data Preparation
You reshape the dataset to long format so each row represents an individual-alternative pair

You create a "chosen" column to indicate which option was actually selected

You generate dummy variables for the alternatives (bus/car), using bike as a reference



Step 4: Model Estimation (MLE)
The model estimates β coefficients using maximum likelihood estimation (MLE)

For each alternative (Bus and Car), you get:

β_time, β_cost, β_risk, and intercept terms

These coefficients show how each factor affects the log-odds of choosing that mode vs. the reference (bike)



Step 5: Interpretation of Results
From the output, you learn:

Coefficient : Meaning
Negative β_time	: Longer travel time decreases the chance of choosing that mode
Positive β_cost :	Higher cost increases likelihood (counterintuitive → may need deeper analysis)
Significant p-values (< 0.05) : Those variables significantly influence mode choice
Odds ratios :	Show how a 1-unit change affects the relative odds of choosing Bus/Car over Bike



Step 6: Predicting for an Average Commuter
You calculate the average values of time, cost, and risk

You plug these into the model for each mode

You get predicted probabilities of choosing:

Bike: X%

Bus: Y%

Car: Z%

These give real-world insight into how a typical person is likely to behave.



Step 7: Policy Implications / Applications
Transportation planners can use this to:

Predict behavior if costs or risks change (e.g. raise bus fares)

Simulate what happens if biking becomes safer (reduce risk → increase biking)

Marketers or urban planners can apply similar models to product choice, city planning, etc.



📌 Final Takeaways
MNL helps us move beyond binary or numeric outcomes into categorical decision-making

The model quantifies how sensitive choices are to different variables (like cost, time, or risk)

This is critical for prediction, simulation, and policy design

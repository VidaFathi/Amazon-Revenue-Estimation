# Amazon-Revenue-Estimation with Linear Regression algorithm
We want to predict quarterly revenue by using a Linear Regression model with Rstudio.
To estimate the model, we use the following path:

  Model --> Linear Regression --> estimate model --> RegressionModel1.png

when you estimate a Linear Regression model , six graphs will pop up in plot Dashboard. The most important ones would be  "Residual vs Fittered one" , "Residual vs row order" and "Residual vs normal density".

"Residual vs normal density": 
    For having a good Regression  model, the residuals must have a normal distribution, which means     that both must be close to each other

"Residual vs Fitted one":
   For Residual vs fitted one we don't want to see any special pattern. so we say that "NO PATTERN     IS GOOD PATTERN" ---> Graphs.png
  
The graphs.png shows that we have a pattern, so we don't like it.
We go back to :
    Data ---> Transform --> create new variable --> instead of looking at QR we create a LogQR variable
LogQR=Ln(QR) --> createnewvariable.png

Then we run another Regression model for LogQR ----> RegressionModel2.png
Graphs for Log QR --> Graphs2.png 
"RegressionModel2.png" shows a good sign that we don't have any pattern here. However, we can see that we have a different result in different quarters. This is a Time Series Analysis. We will add seasonality variables. 

We change the type of the Fiscal year to a category variable and run the model -->RegressionModel3.png
and the plot would be ---> Garphs3.png

We create four lag variables ---> Lagvariable.png
L1 looks at the  previous quarter's revenue, while L2 looks at the two previous quarters----> lagvariablesmodel.png

 We rerun the model with L1, L2, and so on. --> RegressionModel4.png
 graphs4.png --> shows us that we don't have any special pattern. No pattern is a good pattern.
 
 NOTE: if we have a time series analysis in which the revenue of the current month depends on the previous month, we should include lag variables in our analysis.
 for example, if we want to analyze sales by month, we should consider that sales in November are usually  high due to Thanksgiving. For these purposes, we need to define dummy variables.

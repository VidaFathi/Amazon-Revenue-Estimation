# Amazon-Revenue-Estimation
we want to predict quarterly revenue as a function of period
Model-->Linear Regression--> esrtimate model-->RegressionModel1.png

For Linear Regression when you estimate a model, go to plot and in Dashboards--> 6 graphs are going to pop up. most important one is "Residual vs Fitterd one" and then "Residual vs row order" and "Residual vs normal density".


"Residual vs normal density": 
  for having a good Regression model, these residulas have to have a normal distribution, it means that both have to close to each other.

"Residual vs Fitterd one"---> for this Graph we don't want to see any special pattern, sp we're saying "NO PATTERN IS GOOD PATTERN"----> Graphs.png

in this model, we have a pattern, so we don't like this model. we're going back to 'Data'---> 'Transform'--> create new variable--> instead of looking at QR we create a LogQR variable
LogQR=Ln(QR)--> createnewvariable.png
 and then run another Regression model for LogQR ----> RegressionModel2.png
 Graphs for Log QR --> Graphs2.png (you can see that we don't have any pattern here which is a good sign BUT we can see that we have a different result in different quarter)

 THis is a TIME SERIES ANALYSIS.---> we will add seasonality variables

 change the type of Fiscal year to category variable and run the model---->RegressionModel3.png
 and the plot would be ---> Garphs3.png

 create 4 lag variables ---> Lagvariable.png
 L1 look into previous quarter revenue. L2 will look into two previous quarters----> lagvariablesmodel.png

 rerun the model with L1,L2 , .... --> RegressionModel4.png
 graphs4.png --> we don't have any special pattern - no pattern is good pattern
 NOTE: agar masaleye ma "Time series" abshe va bedonim  masalan revenue in mah bemahe ghabl basyegi dare bayad lag ro biarim toye analysemon.
 masalan agar darim sales ro mahiyane negah mikonam, bayad dar nazar begiram ke masalan dar mahe november sales  kheili ziade, bekharere thanksgiving o ina. baraye in mavared bayad dumivariables tarif konim.
